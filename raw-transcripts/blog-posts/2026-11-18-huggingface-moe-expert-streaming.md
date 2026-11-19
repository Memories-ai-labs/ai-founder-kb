# 180B Parameters, 32GB of RAM: Pushing MoE Inference to the Limit with Transformers
# URL: https://huggingface.co/blog/moe-expert-streaming
# Date: 2026-11-18
# Source: Hugging Face Blog

**Author:** Tarek Ziadé (Hugging Face)

## Summary

Running Qwen3.8-Flash-Next, a 180B-parameter Mixture-of-Experts model, on a 32 GB MacBook M5 via expert streaming from SSD — achieving within 6% of Strata's performance.

## Key Technical Points

**Goal:** Demonstrate that streaming MoE experts directly from SSD gets within 6% of Strata on token generation on consumer hardware.

**Background:** Strata is an inference engine that keeps frequently used experts in GPU memory and streams the rest from RAM/disk. The post compares llama.cpp, vLLM, and HuggingFace Transformers with Accelerate.

**Approach:** Added `experts_offload` option to Transformers (PR #50717) featuring:
- Bounded expert cache with slot pool
- `grouped_mm` kernel compatibility
- Parallel SSD reads with prefetching of likely next-layer experts
- 121 GB of experts quantized to 3 bits
- N-gram embedding table read from disk

**Optimizations:** Earlier GPU work commitment, custom Metal kernels, Strata's GGUF weights, larger prefill chunks, efficient long-context attention and KV caching.

**Results on M5 MacBook:**
- Decoding: ~13.9 tok/s vs Strata's 14.8 (6% behind)
- Prefill: slightly faster than Strata

**Takeaway:** Expert streaming from consumer hardware makes 180B MoE models viable. Remaining gap is host-GPU synchronization not currently exposed by PyTorch.
