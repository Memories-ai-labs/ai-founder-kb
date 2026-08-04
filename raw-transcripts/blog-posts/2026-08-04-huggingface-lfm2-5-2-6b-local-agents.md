# Deploy local agents everywhere with LFM2.5-2.6B
# URL: https://huggingface.co/blog/LiquidAI/lfm2-5-2-6b
# Date: 2026-08-04
# Source: Hugging Face Blog / Liquid AI

Authors: Liquid AI (Leonie Monigatti, Sergei Tilga, Sinoué GAD, Song Duong, Tim Seyde, Maxime Labonne)

## Summary

LFM2.5-2.6B is a breakthrough on-device AI agent model from Liquid AI. It enables developers to deploy capable agents directly on consumer hardware — laptops to smartphones — while maintaining data privacy and eliminating cloud inference costs.

## Key Capabilities

- Competitive performance with language models 4x its size on tool use, instruction following, and multi-step agentic tasks
- Underwent agentic reinforcement learning training within popular agentic frameworks
- 220 tokens/sec on Apple M5 Max; 113 tokens/sec on AMD Ryzen AI Max+ 395
- Under 2.5 GB memory footprint

## Development Approach

Training pipeline — four stages:

1. **Pre-training** on ~34 trillion tokens
2. **Mid-training** context extension to 128K tokens
3. **Post-training** via supervised fine-tuning (two rounds) emphasizing agentic data including tool use and web search
4. **Agentic RL** within actual agent harnesses across different tools, system prompts, and multi-turn environments

The team trained specialist teacher models for specific domains (math, code, tool use) then distilled into a single student model via multi-domain on-policy distillation.

RL architecture separated concerns: training engine (policy optimization) + rollout engine (action generation) + RL framework (orchestration) + sandbox service (agentic harness execution).

## Performance Benchmarks

**Instruction following:**
- IFBench: 59.17
- Multi-IF: 80.07
- IFStruct: 85.49

**Tool use:**
- ToolSandbox: 77.83
- BFCLv4: 56.88

**Agentic tasks:**
- Claw-Eval avg (English): 62.85
- PinchBench: 68.22

Tops all instruction-following benchmarks tested. Leads most tool-use benchmarks. Coding is the primary weakness vs. larger models.

## Inference Performance

**CPU:**
- M5 Max: 220 tok/s decode
- Ryzen AI Max+ 395: 113 tok/s

**GPU (single H100):**
- Near 15,000 output tok/s at high concurrency
- ~1.3 billion tokens/day capacity

## Access

- Model: `LiquidAI/LFM2.5-2.6B` on Hugging Face
- Browser demo on Hugging Face Spaces
- Integration guides for OpenClaw, Hermes Agent, Pi frameworks
