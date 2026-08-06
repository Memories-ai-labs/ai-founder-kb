# Baseten on Hugging Face Inference Providers

**Title:** Baseten on Hugging Face Inference Providers
**Publisher:** Hugging Face
**URL:** https://huggingface.co/blog/baseten
**Date:** 2026-08-06
**Source:** Hugging Face Blog

---

Baseten has joined Hugging Face's ecosystem as a supported inference provider. The platform offers serverless AI infrastructure with a focus on making it simple for developers to integrate AI models into applications.

## Key Features

The integration enables access to popular open-weight language models including DeepSeek V4 Flash, Kimi K3, and GLM-5.2. Initially, Baseten supports conversational and text-generation tasks with plans to expand to additional model types.

## How to Use

Users can access Baseten models through:
- The Hugging Face website UI by setting API keys in account settings
- Python and JavaScript SDKs (huggingface_hub ≥ 1.26.1 and @huggingface/inference)
- Compatible agent frameworks

## Billing Options

Two billing approaches:
1. **Direct requests** using your own Baseten API key (billed to your Baseten account)
2. **Routed requests** authenticating via Hugging Face (standard provider rates with no markup)

PRO subscribers receive $2 monthly in inference credits across all providers.

## Significance

Baseten joining the HuggingFace inference provider ecosystem follows their $13B Series F. This gives developers a unified API surface to compare and switch between inference providers (including Together AI, Replicate, Groq, and others) — accelerating the commodity-inference trend where model access costs trend to zero.
