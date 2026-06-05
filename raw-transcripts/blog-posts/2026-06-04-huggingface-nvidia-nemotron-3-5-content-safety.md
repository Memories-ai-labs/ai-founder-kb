# Nemotron 3.5 Content Safety: Customizable Multimodal Safety for Global Enterprise AI
# URL: https://huggingface.co/blog/nvidia/nemotron-3-5-content-safety
# Date: 2026-06-04
# Source: Hugging Face Blog (NVIDIA)

**Authors:** Varun Singh, Isabel Hulseman, Anuj Doshi, Shyamala Prayaga (NVIDIA)

## Overview

NVIDIA released Nemotron 3.5 Content Safety, an advancement that consolidates multimodal input processing, multilingual support, customizable enterprise policies, and explainable reasoning into a single 4-billion-parameter model. This represents a progression from earlier iterations that added capabilities incrementally.

## Key Capabilities

**Unified Multimodal Evaluation**

The model processes user prompts, optional images, and optional assistant responses simultaneously, generating one coherent safety determination. This unified approach captures policy violations that emerge only from interactions between text and image components—situations that separate scoring would miss.

**Multilingual Reach**

The system explicitly covers "12 languages including English, French, Spanish, German, Chinese, Japanese, Korean, Arabic, Hindi, Russian, Portuguese, and Italian" while leveraging its Gemma 3 foundation for zero-shot performance across approximately 140 additional languages through transfer learning.

**Custom Policy Integration**

Organizations can supply domain-specific safety rules as natural-language policies. The model reasons over these custom guidelines during inference rather than relying solely on built-in taxonomies, enabling healthcare platforms, financial services, and educational tools to enforce their distinct risk profiles.

**Reasoning Traces**

Optional "THINK mode" produces step-by-step reasoning before delivering safety verdicts. This provides audit trails for regulated industries and helps teams refine policies by observing how the model interprets edge cases.

**Published Dataset**

NVIDIA released their training and evaluation data, addressing a significant gap since "most OSS safety models don't generally provide the training or evaluation sets." The dataset emphasizes real photographs (99% of training images) rather than synthetic alternatives.

## Technical Foundation

Built on Google's Gemma 3 4B IT base with a LoRA adapter, the model maintains a compact footprint suitable for GPU deployment on 8GB+ VRAM. It supports three output modes: binary verdicts, verdicts with safety category labels, and reasoning-augmented classifications using the Aegis 2.0 framework encompassing 13 core safety categories.

## Performance Metrics

Testing across multilingual and multimodal benchmarks (VLGuard, MM-SafetyBench, PolyGuard, others) showed approximately 85% average harmful-content classification accuracy. On Multilingual Aegis, performance reached 96.5% across 12 languages, while RTP-LX testing averaged 88.8%.

The model achieved "3x lower end-to-end latency on a multimodal benchmark compared to an alternative multimodal safety model" and produced up to 50% fewer tokens when reasoning was enabled.

## Deployment

The model is available through Hugging Face under the NVIDIA Open Model License, supported by transformers, vLLM, and SGLang frameworks. It's accessible via NVIDIA NIM, plus inference platforms including Baseten, DeepInfra, OpenRouter, and others. NVIDIA provides policy-generation tools and implementation cookbooks for custom enterprise workflows.
