# Welcome Le Chonk: Mistral Large 4 on Hugging Face
# URL: https://huggingface.co/blog/mistral-large4
# Date: 2026-10-29
# Source: Hugging Face Blog

**Model overview:** Mistral Large 4 is a multimodal, multilingual Mixture-of-Experts model. ~1T total parameters, 49B active, 1M-token context window. Available in FP8 and NVFP4 variants, with GGUF quants. Licensed under Mistral Ecosystem Open-Weight License.

**Architecture:** Sparse attention + Pixtral vision encoder. Each token is routed to a small group of experts; an attention indexer selects which earlier positions to attend to. 1.6B-parameter vision encoder.

**Benchmarks:**
- 61.7% on DeepSWE v1.1
- 93% on Cybench
- 93.3% on Lakera's B3 prompt-injection benchmark
- Ranks 5th among open-weight models on Artificial Analysis Intelligence Index
- 82% on reproduce-then-patch task in Artificial Analysis Cyber Index (positioned for defensive security)

**Deployment:** Day-0 support in Transformers, vLLM, and llama.cpp. Fine-tuning with TRL. Inference Endpoints recipe on 8x H200 GPUs. Available through Dell Enterprise Hub. Reasoning effort can be set to low, medium, or high (cannot be turned off).
