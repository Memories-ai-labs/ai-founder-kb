---
Title: Holo3.1: Fast & Local Computer Use Agents
Source: HuggingFace Blog (H Company)
URL: https://huggingface.co/blog/Hcompany/holo31
Date: 2026-06-02
Publisher: H Company
---

## Overview

Holo3.1 is the next generation of H Company's computer-use model, building upon Holo3 released in March 2026. While Holo3 delivered state-of-the-art performance, real-world adoption revealed new requirements: users needed the same capabilities across desktop and mobile environments, compatibility with different agent frameworks, and deployment flexibility from cloud to fully local execution.

Holo3.1 addresses these challenges by improving robustness across three critical dimensions:
- **Environments**: Web, desktop, and mobile support
- **Agent frameworks**: Cross-harness compatibility  
- **Deployment targets**: From cloud inference to local consumer hardware

This is the first release to include quantized checkpoints (FP8, Q4 GGUF, and NVFP4) optimized for local inference.

## Model Variants

| Model | Use Case |
|-------|----------|
| Holo3.1-0.8B | Ultra-lightweight local agents |
| Holo3.1-4B | Cost-efficient deployment |
| Holo3.1-9B | Balanced performance and latency |
| Holo3.1-35B-A3B | State-of-the-art performance |

## Key Performance Improvements

### Mobile Automation (AndroidWorld benchmark)
- 35B-A3B model: 67% → **79.3%**
- 4B variant: 58% → **72%**
- 9B variant: 58% → **72%**

### Cross-Harness Performance
- Native function-calling protocol support added
- 25% improvement over Holo3 in Holotab product harness

### Quantization / Local Inference (DGX Spark)
- NVFP4 W4A16: **1.74× faster than BF16**
- Q4 GGUF: enables fully private local deployment on Windows/Mac
- End-to-end speedup: ~2× compound improvement (6.8s → 3.3s average step time)

## Architecture
- Based on the Qwen model family
- FP8, NVFP4, and Q4 GGUF quantized checkpoints available

## Significance for AI Founders
Holo3.1 represents the current frontier of computer-use / GUI-agent models with explicit multi-environment support. The local inference story (run entirely on private hardware) opens enterprise deployment where cloud-based computer control is a non-starter. Mobile automation benchmarks at 79%+ suggest production-viable mobile RPA.
