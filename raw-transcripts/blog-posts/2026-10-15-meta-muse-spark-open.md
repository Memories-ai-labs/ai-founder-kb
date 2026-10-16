# Welcome Muse Spark Open: open-weight frontier multimodal mixture-of-experts model from Meta
# URL: https://huggingface.co/blog/meta-muse-spark-open
# Date: 2026-10-15
# Source: Hugging Face Blog

**Publisher:** Hugging Face (meta-muse-spark team)

Meta's Muse Spark Open is a large open-weight model with about 816 billion total parameters, roughly 42 billion active per token. It accepts text, images, audio, and video, and outputs text with a context window up to 1 million tokens.

**Key capabilities:**
- Multimodal: text, images, audio, video input
- 816B total parameters, ~42B active per token (MoE)
- 1M token context window
- Optimized for agentic coding (cross-codebase work, debugging, tool calling)
- Compatible with: Transformers, llama.cpp, SGLang, vLLM, MLX
- Fine-tuning via TRL
- Deployable via Hugging Face Inference Endpoints

**Significance:** Meta releases its frontier multimodal model as open-weight, continuing its strategy of open-sourcing at the frontier. Muse Spark Open positions Meta to compete with Anthropic/OpenAI/Google for enterprise agentic workflows while building developer ecosystem loyalty through openness.
