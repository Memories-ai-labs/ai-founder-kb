Title: State of Open Models: Summer 2026 Observations
Publisher: Hugging Face
Authors: Adina Yakefu, Apolinário (multimodalart), Irene Solaiman
URL: https://huggingface.co/blog/state-of-open-models-summer-2026
Date: 2026-08-14
Source: Hugging Face Blog

---

## Key Findings

### 1. The Frontier is Moving Fast

Chinese laboratories are outpacing American counterparts in frontier model development. Throughout 2026, Chinese labs consistently released larger models than their U.S. equivalents, with monthly parameter ceilings ranging from 754 billion to 2.78 trillion compared to America's sub-130 billion ceiling in most months.

The report notes that "building large stopped being a differentiator." Companies like Xiaomi and Meituan surpassed trillion-parameter thresholds despite being relative newcomers to open weights. Community quantization tools enable large models to run on consumer hardware without official small model variants.

Hardware vendors — AMD and NVIDIA — emerged as the largest publishers of new models in 2026, releasing over 200 repositories each. This reflects a strategic shift: open models serve as hardware validation and sales tools.

### 2. Attention ≠ Adoption

Only one repository appeared in both the top 25 most-liked and most-downloaded models. Downloads concentrate on stable, small models from earlier years, while likes reflect recent frontier releases. The all-MiniLM-L6-v2 embedding model accumulated 1.55 billion downloads against 5,156 likes.

Chinese frontier labs show different patterns than American labs: most of MiniMax's downloads came from models above 70B parameters, while Google, Microsoft, and IBM Granite recorded essentially zero downloads above that threshold.

### 3. Open Weights Shift Where Value Accumulates

Surprisingly permissive licensing dominates frontier releases. Of 178 Chinese models above 20B parameters, 59% used Apache 2.0 and 22% used MIT licenses — with zero non-commercial restrictions. The monetization model centers on "API and cloud business, hardware and platform positioning" rather than licensing fees.

### 4. Qwen Became the Community's Base Model

Alibaba's Qwen achieved unprecedented ecosystem dominance with 151,448 derivative models on Hugging Face — 2.6 times Meta's footprint and 4.7 times Llama-specific repositories. The consistency of releases across model sizes, Apache 2.0 licensing, and comprehensive coverage attracted rapid adoption.

New Qwen-based repositories appeared at roughly 180-210 per day throughout early 2026, demonstrating sustained momentum beyond individual launches.

### 5. Small Models Remain the Practical Layer

Sub-1 billion parameter models captured 83% of all-time downloads, with models above 100B accounting for just 1%. This gap narrowed through llama.cpp — the ggml team joining Hugging Face in February extended local inference capabilities from laptop-scale (8B) to trillion-parameter mixtures-of-experts.

GGUF quantized versions drove adoption: Qwen GGUF repositories received 39.6 million monthly downloads compared to Gemma's 20.8 million and Llama's 7.5 million, despite comparable repository counts for Llama variants.

### 6. Agents Are the New User

An emerging agent-usage dataset revealed autonomous systems as significant Hub consumers. Claude Code dominated July agent traffic at 44.4%, but volatile monthly shares (ranging from 6.4% to 67.8%) indicated an unsettled market. Nearly 25% of July agent traffic came from unnamed harnesses, with over a dozen new identifiers appearing monthly.

The report documented "the first documented case of an autonomous agent running a sustained intrusion on its own initiative," analyzed using an open-source GLM-5.2 model after frontier closed-model safety guardrails declined the analysis work.

---

## Broader Implications

The analysis reveals a fundamental rebalancing in AI development geography. While U.S. participation in open-source remains active in embedding models and infrastructure, frontier-scale original development has shifted toward Chinese laboratories and hardware manufacturers. Community-driven workflows — quantization, fine-tuning, derivatives — now constitute the practical layer where adoption concentrates, increasingly decoupled from official releases.
