---
Title: Introducing Mellum2: A 12B Mixture-of-Experts Model by JetBrains
Source: HuggingFace Blog (JetBrains)
URL: https://huggingface.co/blog/JetBrains/mellum2-launch
Date: 2026-06-01
Publisher: JetBrains
Technical Report: https://arxiv.org/pdf/2605.31268
---

## Overview

Mellum2 is an open-source Mixture-of-Experts (MoE) model released by JetBrains under the Apache 2.0 license, designed for efficient, low-latency text and code workloads.

## Key Specifications

| Attribute | Details |
|-----------|---------|
| Total Parameters | 12B |
| Active Parameters per Token | 2.5B |
| Modality | Text and code |
| License | Apache 2.0 |
| Architecture | Mixture-of-Experts |

## Performance

- **Inference Speed**: More than 2× faster than similarly-sized dense models
- Competitive with similar-sized open models across code generation, reasoning, and science/math tasks
- Well-suited for high-throughput, low-latency production workloads

## Primary Use Cases

1. **Routing and Orchestration** — Prompt classification, tool selection, control-flow steps
2. **RAG Pipelines** — Context compression, summarization, retrieval post-processing
3. **Sub-agents** — Planning, validation, transformation, context preparation
4. **Private Deployment** — Self-hosted environments with proprietary code or internal data

## Design Philosophy ("Focal Model" Strategy)

Mellum2 is designed as a "focal" model — a fast, well-scoped component optimized for high-frequency tasks within larger AI systems, rather than attempting to replace frontier models. This positions it as an infrastructure component in multi-model agent architectures rather than a standalone assistant.

## Resources
- Model Collection: https://huggingface.co/collections/JetBrains/mellum-2
- Technical Report: https://arxiv.org/pdf/2605.31268
