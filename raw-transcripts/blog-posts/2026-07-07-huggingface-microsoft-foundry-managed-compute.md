# Hugging Face Models on Foundry Managed Compute

**Publisher:** Hugging Face / Microsoft
**Date:** 2026-07-07
**URL:** https://huggingface.co/blog/microsoft/foundry-managed-compute
**Authors:** Manoj Bableshwar, Osi (ositanachi), lysandre, jeffboudier, abidlabs, alvarobartt, Violette, tomaarsen

---

Microsoft announced a partnership enabling deployment of curated open-weight models from Hugging Face directly onto Microsoft Foundry's managed GPU infrastructure.

## Core features

- Weekly-refreshed catalog of trending models across all modalities (text, vision, audio, multimodal)
- Security-screened models in SafeTensors format only
- Pre-staged weights in Azure storage with no external dependencies
- Enterprise-grade infrastructure including identity, networking, and observability

**Supported runtimes:** vLLM, SGLang, TensorRT-LLM, NIM, Text Embeddings Inference, and llama.cpp

## Key benefit

Provides "the breadth of the open-source ecosystem, with the operational layer Microsoft runs underneath" — handling discovery, licensing, security screening, and runtime management.

Models deploy via Python SDK and score using OpenAI SDK through a unified endpoint, integrating seamlessly with Foundry Agents.

**Status:** Available in preview.
