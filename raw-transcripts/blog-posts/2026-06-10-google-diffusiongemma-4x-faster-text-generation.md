---
Title: DiffusionGemma: 4x faster text generation
Publisher: Google
URL: https://blog.google/innovation-and-ai/technology/developers-tools/diffusion-gemma-faster-text-generation/
Date: 2026-06-10
Source: Google Blog
---

# DiffusionGemma: 4x faster text generation

**Published:** June 10, 2026
**Source:** https://blog.google/innovation-and-ai/technology/developers-tools/diffusion-gemma-faster-text-generation/

## Overview

Google introduced DiffusionGemma, an experimental open-source model leveraging text diffusion technology to accelerate text generation. The 26B Mixture of Experts model generates "entire blocks of text simultaneously, delivering up to 4x faster text generation on GPUs."

## Key Features

**Speed Performance:**
- 1000+ tokens per second on a single NVIDIA H100
- 700+ tokens per second on NVIDIA GeForce RTX 5090

**Architecture:** Rather than processing tokens sequentially like traditional language models, DiffusionGemma drafts 256-token paragraphs in parallel, maximizing GPU utilization for local inference tasks.

**Bi-directional Attention:** Enables advantages in in-line editing, code infilling, amino acid sequences, and mathematical graphs.

**Hardware Efficiency:** Activates only 3.8B of its 26B parameters; fits within 18GB VRAM limits of high-end consumer GPUs when quantized.

## Design Trade-offs

"DiffusionGemma's overall output quality is lower than standard Gemma 4. For applications that demand maximum quality, we recommend deploying standard Gemma 4."

## Availability

Released under Apache 2.0 license; accessible on Hugging Face with support from MLX, vLLM, Transformers, and other developer tools.
