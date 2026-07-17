---
Title: Welcome Inkling by Thinking Machines
Publisher: Hugging Face / Thinking Machines
URL: https://huggingface.co/blog/thinkingmachines-inkling
Date: 2026-07-15
Source: Hugging Face Blog
---

# Welcome Inkling by Thinking Machines

*Published July 15, 2026 — Authors: Ben Burtenshaw, Merve, Pedro Cuenca, Aritra Roy Gosthipaty, and 67 others from Thinking Machines*

## Summary

Thinking Machines (Philippines) releases Inkling, a 1-trillion parameter open-weights multimodal large language model. The model natively accepts image, text, and audio inputs with a 1-million token context window, trained on 45 trillion tokens across multiple modalities.

## Architecture

- **Design**: Decoder-only Mixture-of-Experts (975B total parameters, 41B active)
- **Positional encoding**: Relative attention instead of RoPE
- **Attention**: Hybrid — alternates global and sliding-window mechanisms
- **Local representation**: Short convolution (SConv) layers
- **MoE**: Top-6 expert selection plus 2 always-active shared experts
- **Vision**: Simple hierarchical MLP patchifiers
- **Audio**: Discretized mel spectrograms

## Deployment Options

- Transformers via `AutoModelForMultimodalLM` with reasoning effort parameters
- SGLang and vLLM for production (tensor parallelism support)
- Hugging Face Inference Providers (OpenAI-compatible APIs)
- llama.cpp local inference with 1-bit GGUF quantizations (95% VRAM reduction)

## Benchmark Position

Competes with Gemini, Claude, and DeepSeek across reasoning, agentic, factuality, vision, and audio evaluation suites.

## Use Cases Highlighted

- Agentic coding with Pi
- Multi-token prediction drafters for speculative decoding
- Vision reasoning on exam questions
- Audio understanding tasks
- Post-training via Tinker and OpenEnv

## Why It Matters for AI Founders

Thinking Machines is a Southeast Asian AI lab releasing a frontier-class open model — challenging the assumption that frontier-scale open-weights models come only from US/Chinese labs. The bet on domain specialization (fine-tuning on proprietary data) as the differentiation layer above open-weights is a signal that the "build on open, specialize on proprietary" pattern is solidifying.
