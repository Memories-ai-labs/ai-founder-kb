# Towards Speed-of-Light Text Generation with Nemotron-Labs Diffusion Language Models
# URL: https://huggingface.co/blog/nvidia/nemotron-labs-diffusion
# Date: 2026-05-23
# source: Hugging Face Blog / NVIDIA

Authors: Mehran Maghoumi, Yonggan Fu, Pavlo Molchanov, and others (NVIDIA)

## Core Innovation

Nemotron-Labs Diffusion introduces diffusion language models (DLMs) that generate multiple tokens in parallel and iteratively refine them, addressing limitations of traditional autoregressive (AR) models that generate one token at a time.

## Model Lineup

- Text models: 3B, 8B, and 14B scales
- Vision-language model: 8B scale
- Both base and instruction-tuned chat variants available
- Open under commercially-friendly licenses

## Three Generation Modes

1. **Autoregressive Mode** — Standard left-to-right generation for compatibility
2. **Diffusion Mode** — Generates blocks of 32 tokens, iteratively refining via denoising
3. **Self-Speculation Mode** — Drafts tokens bidirectionally using diffusion, then verifies causally

## Performance

- 1.2% improved accuracy vs. Qwen3 8B
- 2.6× higher tokens-per-forward-pass (TPF) in diffusion mode
- 6–6.4× speedup with self-speculation
- ~865 tokens/sec on NVIDIA B200 GPUs

## Training Approach

- Pre-trained on 1.3T tokens from NVIDIA Nemotron datasets
- Fine-tuned with 45B tokens from post-training datasets
- Built on Efficient-DLM architecture with block-wise attention for KV-cache compatibility

## Deployment

Supported through SGLang with simple configuration switches for different generation modes.
