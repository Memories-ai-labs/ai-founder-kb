# LFM2.5-VL-3B: Better and Faster Vision Capabilities for the Edge
# URL: https://huggingface.co/blog/LiquidAI/lfm2-5-vl-3b
# Date: 2026-08-12
# Source: HuggingFace Blog / Liquid AI

Publisher: Liquid AI via Hugging Face
Topic: Multimodal AI, edge inference, vision-language models

---

## Overview

Liquid AI has released LFM2.5-VL-3B, a 3.1-billion parameter vision-language model optimized for on-device deployment. The model combines strong visual understanding with efficient inference capabilities suitable for consumer hardware.

## Key Improvements

The model introduces four major enhancements over previous iterations:

1. **Screen and UI Understanding** — Enhanced capability to interpret digital interfaces across various devices
2. **Grounding Capabilities** — Improved object detection and localization using natural language queries
3. **Multi-Image Processing** — Better reasoning across multiple image inputs
4. **Function Calling** — Substantially stronger performance in both text-only and vision-augmented function calling tasks

## Training Architecture

LFM2.5-VL-3B combines a SigLIP2 400M NaFlex vision encoder with a pre-trained 2.6B text backbone. The model underwent pre-training on approximately 34 trillion tokens, incorporating 4x more vision training data than its predecessor. The training pipeline included:

- Supervised fine-tuning with knowledge distillation from larger teacher models
- Antidoom training methodology
- Multi-reward reinforcement learning optimization
- Tokenizer expansion to 128K vocabulary for non-Latin script support

## Benchmark Performance

**Vision Tasks:**
- MMBench (dev): 81.0%
- RefCOCO (grounding): 87.9%
- ScreenSpot-v2 (Desktop): 78.7%
- DocVQA: 91.1%
- ChartQA: 81.3%

**Text-Only Tasks:**
- IFEval: 82.3%
- ToolSandbox: 59.5%
- BFCL V4: 32.5%

## Inference Performance

**On-Device:**
- M5 Max decoding: 228 tokens/second
- Ryzen AI Max+ 395: 116 tokens/second
- Galaxy S26 Ultra: 20 tokens/second
- Memory footprint: ~3GB

**GPU:**
- Output throughput: ~11,000 tokens/second at high concurrency
- ~1 billion output tokens/day on single H100 GPU

Supported deployment: llama.cpp, MLX, vLLM, SGLang, ONNX

## Use Cases

- High-volume on-device processing
- Screen and document understanding
- Real-time multimodal analysis
- Edge deployment with minimal latency

## Significance

Strong benchmark numbers at 3B parameters, particularly ScreenSpot-v2 (78.7%) and DocVQA (91.1%), make this competitive with larger models for agentic on-device workflows. The function calling improvements are notable for agent use cases.
