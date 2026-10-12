# Title: ColGrep-Agent: Cutting Frontier Coding Agents' Tokens by a Third
# URL: https://huggingface.co/blog/lightonai/colgrep-agent
# Date: 2026-10-12
# Source: huggingface

Authors: Maxence Lasbordes (MaxLSB), Raphael Sourty, Aarush Sinha, Amélie Chatelain — LightOn AI

---

## Summary

LightOn introduces ColGrep-Agent-2B, an open 2-billion-parameter code-search agent designed to run locally alongside a frontier coding agent. It acts as a delegated file-search tool, replacing grep-style searches with multi-vector semantic retrieval.

## How it works

- Uses ColGrep, LightOn's multi-vector semantic search tool, to find relevant files
- Follows code references and returns file paths, line ranges, and code snippets to the primary coding agent
- Runs fully locally; GGUF weights are approximately 2.5 GB

## Benchmark results

Tested with Claude Code (Sonnet 5.5) on 52 code-search questions across 13 unseen repositories:

- **Token reduction:** 34% fewer API tokens vs. baseline grep
- **Cache-aware cost reduction:** 40% lower
- **Accuracy:** 80.8% vs. 83.3% baseline — no statistically significant difference
- **Latency trade-off:** Average time per question rose from 13.0 to 21.6 seconds
- **"Balanced" setup:** 21% token savings while matching grep's observed accuracy

The model outperforms larger open models on several code-localization benchmarks.

## Training

- Base: MiniCPM5-2B
- Method: Supervised fine-tuning followed by GRPO (reinforcement learning)

## Availability

Weights available on Hugging Face under the lightonai organization. The GGUF quantized version is approximately 2.5 GB.

## Relevance for AI founders

- Demonstrates that small specialized agents can outperform raw frontier-model token spend on narrow tasks
- First public benchmark showing meaningful cost reduction for coding agents without accuracy degradation
- Points toward heterogeneous agent architectures: local small models handling retrieval, frontier models handling reasoning
