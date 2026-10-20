# AnyLanguageModel 1.0: One Year of Local Models on Apple Platforms
# URL: https://huggingface.co/blog/anylanguagemodel-1-0
# Date: 2026-10-20
# Source: Hugging Face Blog

Author: Mattt (Hugging Face)

## Summary

AnyLanguageModel 1.0 is a Swift library that acts as a drop-in replacement for Apple's Foundation Models framework, letting developers choose which AI model and provider their app uses — local or hosted. Companion releases: swift-huggingface 1.0 and swift-xet 1.0.

## Key Features

**Drop-in API:** Apps switch by changing import from `FoundationModels` to `AnyLanguageModel`. Same session code works with:
- System model (Apple's built-in)
- Local open-weight models (llama.cpp, MLX, Core ML)
- Hosted providers (OpenAI, Anthropic, Gemini, etc.)

**Feature parity across providers:**
- Tool calling and guided generation (including nested `@Generable` types)
- Image attachments
- OS 27: also works with models conforming to Foundation Models' `LanguageModel` protocol, including Core AI models

**Hosted providers supported:**
- OpenAI (Chat Completions and Responses API)
- Open Responses
- Anthropic
- Google Gemini
- Ollama
- Private Cloud Compute (OS 27)
- Hugging Face Inference Providers
- OpenAI-compatible endpoints (e.g., OpenRouter)

**Reasoning block handling:** Works correctly when switching providers. API keys can be supplied by closures to allow short-lived tokens. Runs on Linux.

**Notable open-weight models highlighted:**
- Gemma 4 E2B and LFM2.5 2.6B in GGUF format (small, on-device)
- Qwen3.8 27B in MLX (~16 GB at 4 bits, suits Macs with 32 GB+)
- GLM-5.3 (too large for local; accessed via Inference Providers)

## What's Next

Team plans to extend Swift-first approach to other model types: "models that decide" and "models that listen."

## Relevance for AI Founders

- Signals growing maturity of on-device AI infrastructure for Apple platform developers
- Demonstrates abstraction layer pattern for multi-provider AI integration (swap provider without rewriting app logic)
- Open-source community building critical developer tooling for local AI deployment
