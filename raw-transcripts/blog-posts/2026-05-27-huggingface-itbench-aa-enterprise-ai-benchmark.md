# ITBench-AA: Frontier Models Score Below 50% on Enterprise IT Agentic Tasks
# URL: https://huggingface.co/blog/ibm-research/itbench-aa
# Date: 2026-05-27
# source: Hugging Face Blog (Artificial Analysis + IBM Research)

## Overview

ITBench-AA is a new benchmark developed jointly by Artificial Analysis and IBM Software Innovation Lab that evaluates frontier AI models on agentic enterprise IT tasks. It's the first benchmark specifically designed for Site Reliability Engineering (SRE) operations — assessing how well AI agents diagnose Kubernetes incidents in real-world enterprise environments.

## Key Findings

**Model Performance (all below 50%):**
1. Claude Opus 4.7 (Adaptive Reasoning, Max Effort) — **47%** (leads)
2. GPT-5.5 (xhigh) — **46%**
3. Qwen3.7 Max — **42%**
4. GLM-5.1 (Reasoning) — 40%
5. Gemini 3.5 Flash (high) — 40%
6. DeepSeek V4 Pro (Reasoning, Max Effort) — 38%
7. Gemma 4 31B (Reasoning) — 37%

All frontier models score below 50%, making ITBench-AA SRE one of the least saturated agentic benchmarks currently available.

## What It Tests

- **59 total SRE tasks**: 40 public + 19 held-out tasks
- **Focus**: Kubernetes incident diagnosis and root-cause analysis
- **Task Format**: Models receive incident snapshots containing alerts, events, traces, metrics, application logs, and system topology

**Failure Modes Covered:**
- Infrastructure failures, service rollout failures, connection pool exhaustion
- Network partitions, resource quota exhaustion, chaos-injected incidents

## Cost-Performance Analysis

| Model | Accuracy | Cost/task |
|-------|----------|-----------|
| Gemma 4 31B | 37% | $0.14 (best value) |
| GLM-5.1 | 40% | $1.23 |
| Claude Opus 4.7 | 47% | $5.38 |

## Important Insights

1. **More turns ≠ better results**: Turn counts vary nearly 3x (31 to 83 turns) with no accuracy benefit from more turns
2. **Scoring**: Strict — any missed ground-truth root cause scores 0.0; precision penalized for false positives

## Resources

- ITBench Paper: https://arxiv.org/abs/2502.05352
- GitHub: https://github.com/itbench-hub/ITBench
- Leaderboard: https://artificialanalysis.ai/evaluations/itbench-aa
