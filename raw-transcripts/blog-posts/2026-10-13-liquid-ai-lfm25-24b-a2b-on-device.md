# Run fast, private agents on-device with LFM2.5-24B-A2B
# URL: https://huggingface.co/blog/LiquidAI/lfm25-24b-a2b
# Date: 2026-10-13
# Source: Liquid AI / Hugging Face

## Key points

- **Model:** LFM2.5-24B-A2B — 24B parameter reasoning model that activates only 2B parameters per token (MoE approach). Enables on-device agent inference.
- **Architecture:** Extends predecessor's architecture with 131K token context window and doubled vocabulary.
- **Training:** Multi-stage post-training pipeline including agentic reinforcement learning in harnesses (OpenClaw, Pi).
- **Performance:** Competes with models ~50% larger on tool-use and instruction-following benchmarks; trails larger models on knowledge-heavy and coding tasks.
- **Speed:** 184 tokens/s on Apple M5 Max; 21K+ output tokens/s on single NVIDIA B300 at high concurrency.
- **Availability:** Open-weight models on Hugging Face; supports Transformers and local OpenAI-compatible servers.
- **Signal:** Strong MoE efficiency play — enables privacy-preserving on-device agents without sacrificing much capability.
