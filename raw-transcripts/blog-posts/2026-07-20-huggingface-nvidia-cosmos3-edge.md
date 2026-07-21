---
Title: Introducing Cosmos 3 Edge
Source: Hugging Face Blog
URL: https://huggingface.co/blog/nvidia/cosmos3edge
Date: 2026-07-20
Publisher: Hugging Face (NVIDIA guest post)
Authors: Pranjali Joshi, Saeed Babamohamadi, NVIDIA team
---

# Introducing Cosmos 3 Edge

**Published:** July 20, 2026

## Overview

NVIDIA released Cosmos 3 Edge, a **4-billion-parameter open world model** designed for robotics and vision AI on **edge devices**. Enables real-time reasoning and action generation on memory-constrained systems: NVIDIA Jetson, RTX GPUs, DGX hardware.

## Architecture

Combines two transformer architectures:
- **Autoregressive tower**: understanding and reasoning
- **Diffusion tower**: prediction and generation

Shared multimodal attention layers align information across language, video, audio, and action modalities.

## Performance

- Ranked #1 on VANTAGE-Bench for vision analytics among 4B parameter models
- Real-time control at 15 Hz on NVIDIA Jetson Thor
- Generates 32 actions per inference at 640x360 resolution
- Super 4-Step distilled checkpoint: up to 25x faster inference

## Action Representation

Encodes actions as compact geometric vectors capturing translation, rotation, and manipulation state — direct connections between visual changes and physical motion.

## Resources
- Model: `nvidia/Cosmos3-Edge` on Hugging Face
- Policy variant: Cosmos 3 Edge Policy (DROID) for pick-and-place tasks
