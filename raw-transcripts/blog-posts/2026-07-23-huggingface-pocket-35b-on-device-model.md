---
Title: POCKET: a 35-billion-parameter model that runs on your iPhone — and on your PC with no GPU
Publisher: Hugging Face (FINAL-Bench / SeaWolf-AI)
URL: https://huggingface.co/blog/FINAL-Bench/pocket
Date: 2026-07-23
Source: Hugging Face Blog
---

POCKET is a family of quantized models derived from Darwin-36B-Opus that enables running a 34.66-billion-parameter sparse Mixture-of-Experts model on consumer devices without sacrificing quality.

## Key Characteristics

- Activates ~3 billion parameters per token despite large total size
- 2.7× faster on CPU and 2.2× faster on GPU than competing 1-bit quantized 27B models

## Hardware Variants

- **Q4_K_M (21 GB)**: Workstations with 32GB RAM; highest quality
- **Q2_K (13 GB)**: Mini-PCs without GPU; recommended general-purpose option  
- **IQ1_M (8.2 GB)**: Systems with 16GB RAM; smallest full model
- **Language-specific variants**: Korean and English phones can run 5-8GB versions

## Technical Innovation

1. **Darwin Lineage**: Built from Darwin-36B-Opus through iterative training improvements
2. **Domain Expert Pruning**: Language-specific expert selection reduces size without speed loss
3. **Mixed Precision**: High precision for shared layers; sub-2-bit compression for routing experts

## Performance

Testing on Xeon CPU (16 threads): 27.0 tokens/second vs competitor's 10.1. On H100 GPUs: 197 tokens/second vs 89 — a 2.22× advantage.

## Limitations

On datacenter GPUs, competitors process long prompts faster (prefill phase). Extreme quantization affects Korean ~2.8× more severely than English.

Available under Apache-2.0 on Hugging Face.
