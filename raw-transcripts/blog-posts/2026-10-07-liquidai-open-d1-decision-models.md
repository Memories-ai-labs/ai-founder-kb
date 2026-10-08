# Multimodal open d1 decision models for the edge
# URL: https://huggingface.co/blog/LiquidAI/open-d1
# Date: 2026-10-07
# Source: HuggingFace Blog / Liquid AI

Liquid AI released two open-weight decision models in its d1 family. Unlike generative models, they don't generate tokens — they produce answers in a single forward pass.

## Models

**d1-3B:**
- Built on LFM2.5-VL-3B, a decoder-only vision-language model
- Accepts text and image inputs
- Decision Index 0.2.1 score: 48.57 (best result under 10B parameters, ahead of 4B and 9B models, and Decider 35B-A3B at 47.11)
- Mean score across 7 public datasets: 82.9 (vs Decider 4B at 81.1)

**d1-omni-600M (experimental):**
- Built on LFM2.5-Encoder-350M, a bidirectional encoder
- Adds vision and audio encoders — accepts text plus images or audio
- Mean score across 7 datasets: 78.4 (vs Decider 2B at 77.1, with ~1/4 the parameters)

## Benchmark Datasets
Reading comprehension, toxicity detection, intent classification, medical QA, and cross-lingual understanding.

## Inference Speed (d1-3B)
- Jetson AGX Thor: ~16 ms
- Jetson AGX Orin 64 GB: ~26 ms
- Jetson Orin Nano: ~50 ms
- NVIDIA RTX 4090: <10 ms
- AMD MI325X: <10 ms

## Technical Notes
- Requires `transformers>=5.14`, loads with `trust_remote_code=True`
- Supports multiple named questions over one state, image inputs, and packed batch requests

## Availability
Weights on HuggingFace. Demos in the System One Arcade Space.
