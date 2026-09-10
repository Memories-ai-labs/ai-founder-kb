# Inside the megakernel serving engine for North Mini Code
# URL: https://cohere.com/blog/megakernels
# Date: 2026-09-08
# Source: Cohere Blog
# Authors: Xiaochun Tong, Conway Zhu, Donglu Wang

A technical deep dive into how Cohere's approach to megakernels delivers 1.25×–1.58× faster LLM serving on H100 devices.

## Summary

Cohere presents a serving engine for North Mini Code built around a decode megakernel that achieves "1.25× - 1.41× faster than vLLM end-to-end" on H100 devices. The implementation represents the first fully-fledged production serving system centered on this architecture approach.

## Key Technical Insights

**The Core Problem:**
Traditional LLM serving stacks execute each forward pass as sequential operations with synchronization between them. This creates idle GPU time at lower batch sizes. North Mini Code streams 6.6GB of weights per decode step, with H100 theoretical throughput of approximately 470 tokens/second, yet vLLM achieves only 185 tok/s—merely 39% efficiency.

**The Megakernel Solution:**
Instead of launching separate kernels for QKV, attention, MoE, and normalization operations, one persistent kernel runs the entire decode step. This reduces scheduling overhead and enables three major optimizations:

1. **Wave Quantization Reduction** - Tasks launch on available SMs without rounding to full waves
2. **False Dependency Elimination** - Fine-grained barriers allow downstream operations to start when their specific inputs arrive
3. **Weight Prefetching** - Immutable weights begin streaming before activation dependencies resolve

**The ABI Approach:**
Rather than inventing new abstractions, the implementation uses a unified calling convention where every operation follows the same threadblock shape (12 warps organized as 3 warp groups) and descriptor format. This keeps individual operations manageable while they compose into a complex system.

## Performance Results

- **Batch size 1:** 292 tok/s (62% of theoretical speed of light)
- **Consistent gains:** 1.58× faster than vLLM at batch 1, margins hold across batch sizes and up to 256K context
- **End-to-end serving:** 1.25× - 1.41× improvement on real workloads (AIME 2025, GPQA, LiveCodeBench benchmarks)
- **Accuracy preserved:** Near-identical benchmark scores compared to vLLM baseline

## Architecture Highlights

The system uses deterministic static task scheduling for most operations, with local work stealing for variable-length attention and MoE routing. Python and C++ threads coordinate through a park/resume pattern—Python manages batch changes while C++ owns the continuous decode loop, preventing race conditions on mutable batch state.

The implementation prioritizes engineering simplicity: "one CUDA file: no compiler, no new programming paradigm" — just restructured GEMM and attention operations within a single calling convention.
