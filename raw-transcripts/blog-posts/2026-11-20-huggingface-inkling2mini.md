# Welcome Inkling 2 Mini, Cutting-edge Performance for your Local Setup
# URL: https://huggingface.co/blog/inkling2mini
# Date: 2026-11-20
# Source: huggingface-blog

Authors: merve, Pedro Cuenca, Aritra Roy Gosthipaty, Guarin Flück

## Summary

Inkling 2 Mini is a multimodal Mixture-of-Experts model from Thinking Machines Lab: ~26B total parameters, 3B active per token. Accepts text and images; supports 1M-token context.

**Architecture:**
- "Looped transformer" — 12 middle layers run 3 times (48 effective layer visits from 24 physical layers)
- Cross-pass messages and gating let each pass refine the previous
- Mixed-precision NVFP4 and MXFP8 expert weights + DSpark drafter for speculative decoding

**Variants:** Research checkpoint allows 1, 2, or 3 loop passes

**Benchmarks:**
- Leads its class on Artificial Analysis Intelligence Index v5
- Wins 32 of 48 benchmarks vs. comparable models (Gemma 4 31B, Qwen3.8-27B)
- Trails Qwen on one agentic benchmark

**Inference support:** Transformers, Llama App, llama.cpp (4-bit and 8-bit GGUF), SGLang (B300 GPU day-zero), MLX

**HN:** 1136 points (https://thinkingmachines.ai/news/inkling-2-mini/)
