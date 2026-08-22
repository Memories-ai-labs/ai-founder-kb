# LFM2.5-DSpark: Up to 3.2x Faster Inference
# Publisher: Hugging Face / Liquid AI
# URL: https://huggingface.co/blog/LiquidAI/lfm25-dspark
# Date: 2026-08-20
# Source: Hugging Face Blog

## Overview

Liquid AI released DSpark draft model checkpoints for three LFM2.5 models, introducing speculative decoding capabilities that substantially accelerate inference while maintaining output quality.

## Key Achievements

The release delivers notable performance gains: "up to 3.18x throughput improvement on a GPU and up to 2.87x on-device" speed increases. For function-calling tasks, the technology "cuts function-calling latency by 57% on average for LFM2.5-2.6B."

## How DSpark Functions

The approach addresses the memory-bound nature of LLM decoding by using "a lightweight draft model to produce candidate tokens, then having the target model verify them all in a single forward pass." The implementation combines three components:
- A parallel backbone architecture
- A sequential head modeling token dependencies
- A confidence-scheduled verifier for pruning low-confidence predictions

## Technical Details

Draft models contain approximately 300M parameters each. The architecture uses five-layer attention-only designs trained on diverse data spanning instruction-following, chat, code, and function-calling domains.

## Deployment Support

The models ship with immediate compatibility for llama.cpp and SGLang frameworks, enabling deployment across both cloud GPUs (H100s) and edge devices (M4 Max MacBooks).

## Availability

All checkpoint variants are available on Hugging Face in Safetensors and GGUF formats for immediate use.
