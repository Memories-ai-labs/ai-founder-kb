---
Title: Fine-tune video and image models at scale with NVIDIA NeMo Automodel and 🤗 Diffusers
Source: Hugging Face Blog
URL: https://huggingface.co/blog/nvidia/scale-diffusers-finetuning-nemo-automodel
Date: 2026-07-17
Publisher: Hugging Face (NVIDIA collaboration)
Authors: Sayak Paul + NVIDIA team
---

# Fine-tune video and image models at scale with NVIDIA NeMo Automodel and 🤗 Diffusers

**Publication Date:** July 17, 2026

**Authors:** Collaborative effort between NVIDIA and Hugging Face, including Sayak Paul and multiple team members from both organizations.

**URL:** https://huggingface.co/blog/nvidia/scale-diffusers-finetuning-nemo-automodel

---

## Summary

NVIDIA NeMo Automodel is an open-source PyTorch library for fine-tuning large diffusion models at scale, designed around two principles:

1. **Hugging Face native**: Point directly at any Diffusers model ID on the Hub to begin training — no checkpoint conversion needed.
2. **One program, any scale**: Configuration-driven parallelism (not code rewrites) to scale from single GPU to multi-node clusters.

---

## Core Technical Points

### What NeMo Automodel Does

- Eliminates checkpoint conversion barriers: pretrained weights from the Hub work out of the box
- Supports both full fine-tuning and LoRA-style parameter-efficient adaptation
- Incorporates FSDP2 sharding, latent caching via pre-encoded VAE outputs, and multiresolution bucketed dataloading

### Supported Models

- **Text-to-image**: FLUX.1-dev, FLUX.2-dev (flow-matching diffusion)
- **Video/multimodal**: Wan 2.1/2.2, HunyuanVideo, Qwen-Image

### Performance (8× H100 GPUs)

- FLUX.1-dev full fine-tuning: ~35.51 images/second
- FLUX.1-dev LoRA: ~53.73 images/second

### Integration with Diffusers

Fine-tuned models load directly into standard Diffusers inference pipelines — no conversion step required at inference time.

---

## Relevance for AI Founders

- Shows the emerging "Hugging Face native" pattern for enterprise ML tooling: hub as source of truth, not a separate training checkpoint ecosystem
- FSDP2 + latent caching = infrastructure primitives that allow fine-tuning warehouse-scale video models without proprietary cloud tooling
- Open-source fine-tuning pipeline for video models signals commoditization of a previously very expensive capability

---

## Future Development

Team plans to surface recipes through a fully typed Pythonic API in upcoming releases, complementing existing YAML-based quick-start approach.
