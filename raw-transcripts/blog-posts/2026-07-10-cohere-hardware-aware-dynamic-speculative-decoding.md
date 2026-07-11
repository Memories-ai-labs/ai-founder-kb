# Hardware-aware dynamic speculative decoding
# URL: https://cohere.com/blog/hardware-aware-dynamic-speculative-decoding
# Date: 2026-07-10
# Source: Cohere
# Author: Ekagra Ranjan, Member of Technical Staff, Foundations

## Overview

Cohere optimized language model inference through dynamic speculative decoding (DSD), a technique that adapts token prediction based on hardware constraints.

## Key Concepts

**Speculative Decoding Fundamentals:**
The technology uses smaller draft models to propose multiple tokens simultaneously, which a larger target model verifies in a single step. This accelerates generation by exploiting the gap between GPU compute speed and memory bandwidth availability.

**The Core Challenge:**
"Speculative decoding achieves speedup by exploiting the tradeoff between compute and memory bandwidth" of GPUs. However, performance degrades when batch sizes increase and inference becomes compute-bound rather than memory bandwidth-bound.

## Dynamic Speculative Decoding Solution

Rather than fixing the number of draft tokens, DSD adapts dynamically:

- At **low batch sizes**: inference prioritizes higher token predictions
- At **high batch sizes**: the system reduces draft tokens to prevent performance regression

The approach uses "goodput = Acceptance Length / Inter-Token Latency" as its optimization metric, calculating the tradeoff between token acceptance and computational cost.

## Performance Results

Testing on Command A (dense model) showed:
- 23% faster performance than fixed-K speculative decoding at batch sizes 128-256
- 7.5% improvement over baseline at batch size 128
- Graceful fallback behavior preventing regression at high batch sizes

## Implementation Integration

Cohere contributed this optimization to vLLM, ensuring compatibility with production systems through:

1. **Asynchronous scheduling support**: Managing variable draft tokens across timesteps without breaking CPU-GPU parallelization
2. **Full CUDA Graph compatibility**: Capturing multiple K variations to maintain kernel launch efficiency

The implementation demonstrates how theoretical improvements translate to practical production systems.
