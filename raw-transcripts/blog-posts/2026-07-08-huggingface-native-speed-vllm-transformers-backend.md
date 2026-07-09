# Native-speed vLLM transformers modeling backend

**Publisher:** Hugging Face
**Authors:** Harry Mellor, Lysandre, and 17 contributors
**Date:** 2026-07-08
**URL:** https://huggingface.co/blog/native-speed-vllm-transformers-backend
**Category:** Engineering / LLM Inference

---

## Overview

The transformers vLLM backend has achieved performance parity with hand-written vLLM implementations across multiple architectures.

**Key claim:** "The transformers modeling backend is now as fast (or faster) than custom vLLM implementations for many LLM architectures."

## Benchmark Results

Three Qwen3 models tested:
- 4B dense model on single GPU
- 32B dense model using tensor parallelism
- 235B FP8 Mixture-of-Experts model with data and expert parallelism on 8×H100

Results: transformers backend "meets or beats native throughput on every one of them."

## Technical Implementation

Uses `torch.fx` to perform static analysis on the model's graph to identify optimization patterns. Applies `ast` (abstract syntax tree) to manipulate source code and rewrite operations.

Key optimizations:
- Fused operations for Expert Parallelization in MoE models
- vLLM's parallel linear layers
- Optimized models remain fully torch compilable and compatible with training workflows

## Usage

```bash
vllm serve <model> --model-impl transformers
```

## Significance

This closes the performance gap between the general-purpose transformers library and hand-optimized vLLM implementations, meaning teams no longer need to maintain separate code paths for training and inference.
