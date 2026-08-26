# Granite 4.2 LLMs: How They're Built
# URL: https://huggingface.co/blog/ibm-granite/granite-4-2
# Date: 2026-08-25
# Source: Hugging Face Blog / IBM Granite Team

Authors: Yousaf Shah, Swanand Kadhe, Riddhiman Moulick, Ashish Sunil Agrawal, and the Granite Team at IBM.

## Summary

IBM released Granite 4.2, a family of reasoning-focused language models in three sizes: 3B, 8B, and 30B parameters. The models feature a decoder-only transformer architecture trained on approximately 15 trillion tokens using a five-phase pre-training strategy.

Key capabilities include:
- **Reasoning modes**: Full thinking, non-thinking, and low-effort modes
- **Extended context**: 512K token context window
- **Tool integration**: Native OpenAI-compatible function calling
- **Agentic capabilities** (8B/30B): Can operate as AI agents in real environments including software engineering, terminal operations, and web search

## Training Pipeline

The development follows four main stages:

1. **Pre-training** on 15T tokens with progressive data quality improvements
2. **Supervised fine-tuning** on 7.2M samples combining agentic and non-agentic data
3. **Reinforcement learning**: A multi-stage curriculum including foundational RL and agentic RL
4. **Alignment**: RLHF for preference and safety

The RL pipeline uses asynchronous GRPO with "group-relative advantages" and "leave-one-out baseline" techniques, processing "256 prompts with 16 sampled responses apiece for 4,096-example batches."

## Performance

The models demonstrate strong results across reasoning, coding, and agentic tasks:
- 30B model: 41.89% on SWE-Bench Multilingual
- 30B model: 89.17% on HMMT Feb25 math competitions

## Availability

All models are released under Apache 2.0 license with quantized variants (FP8, FP4, GGUF) and integration support for popular agentic frameworks.
