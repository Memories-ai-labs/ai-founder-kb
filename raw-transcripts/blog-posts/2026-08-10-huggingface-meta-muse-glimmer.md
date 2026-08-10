# Meta is back with Muse Glimmer: local, agentic, multimodal, and open source
# URL: https://huggingface.co/blog/muse-glimmer
# Date: 2026-08-10
# source: Hugging Face Blog
# Authors: Pedro Cuenca, merve, ben burtenshaw, Aritra Roy Gosthipaty, and others (Meta)

## Summary

Meta releases Muse Glimmer, a 30B parameter multimodal model optimized for local, agentic deployment. Distilled from Muse to 30B parameters under Apache 2.0 license.

## Key Architecture

- **Total:** 30B parameters
- **Vision encoder:** 2B ViT-style model (processes images and videos up to 96 frames at 2 fps)
- **Language decoder:** 28B with hybrid attention (alternating sliding window + full attention)
- **Gated grouped-query attention** for memory efficiency

## Performance Highlights

Strong on agentic coding tasks: SWE-Bench Pro 51.2%. Competitive across multimodal reasoning and safety metrics.

## Integration & Deployment

- Transformers: `AutoModelForMultimodalLM`
- llama.cpp: native GGUF support with quantized variants
- vLLM: Transformers backend
- Inference Endpoints: managed deployment

## Advanced Features

**Speculative Decoding:** DFlash drafter model accelerates generation especially for code.

**Multimodal:** text-only, image+text, video understanding, tool calling, open-ended object detection.

**Fine-tuning:** TRL integration for SFT through RL-based training approaches.

## Hardware Requirements

- Inference: single 80GB GPU
- LoRA fine-tuning: 80GB GPU with optimizations
- Full fine-tuning: 8 GPUs with distributed training

## Agentic Demonstrations

Muse Glimmer demonstrated autonomously:
- Quantizing and optimizing itself for local deployment
- Deploying itself to Hugging Face Inference Endpoints
- Optimizing its own inference engine for specific hardware
- Researching Hub repositories as an autonomous agent

## Relevance

Most capable open-weight multimodal agentic model at the time of release. Apache 2.0 license lowers barrier for startups building local/privacy-first agentic products. Strong competitive response to OpenAI Codex and Anthropic Claude Code in agentic coding.
