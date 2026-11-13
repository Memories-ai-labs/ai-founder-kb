# Title: The Definitive Fine-Tuning Guide for 3D Generation Models
# URL: https://huggingface.co/blog/3d-lora-finetuning
# Date: 2026-11-12
# Source: Hugging Face Blog

## The Definitive Fine-Tuning Guide for 3D Generation Models

Published: November 12, 2026
Authors: Suvaditya Mukherjee, merve, and Pedro Cuenca (Hugging Face)

### Summary

A practical guide to fine-tuning TRELLIS.2, a 3D generation model, using LoRA adapters. The case study focuses on improving footwear generation quality.

### Key Points

**Goal:** Improve TRELLIS.2 on footwear. The pretrained model often produced shoes with incorrect soles.

**Data:** A 188-shoe subset of Google Scanned Objects. Nine objects held out for evaluation.

**What's fine-tuned:** LoRA adapters on:
- Sparse-structure flow DiT (controls shape/structure)
- Shape flow DiT (controls geometry)

The texture stage stays frozen because the dataset has diffuse color maps with baked-in lighting, not separate material maps.

**Pipeline:** 
- Preprocessing: renders 16 Blender views per object, encodes meshes into latents
- Training uses rectified flow matching
- Both steps run in Docker containers on Hugging Face Jobs or local GPU

**Results on 9 held-out objects:**
- Mean F-score: 0.276 → 0.803 (3x improvement)
- Chamfer distance: 0.174 → 0.033 (5x improvement)
- Normal consistency: 0.530 → 0.804

Adapter improved F-score on all 9 held-out objects.

**Future work:** Authors suggest applying to Pixal3D, UniLat3D, Gaussian-splat, and world-generation models.

### Source

Full text: https://github.com/huggingface/blog/blob/main/3d-lora-finetuning.md
