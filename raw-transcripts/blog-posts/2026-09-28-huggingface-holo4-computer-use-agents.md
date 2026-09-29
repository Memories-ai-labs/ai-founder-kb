# Holo4: Powering Generalist Computer-Use Agents
# URL: https://huggingface.co/blog/Hcompany/holo4
# Date: 2026-09-28
# Source: Hugging Face Blog / H Company

## Overview

H Company introduced Holo4, a new series of agentic models in two sizes: 27B dense and 35B-A3B Mixture of Experts. Designed to interact with software through multiple interfaces: GUI, code execution, MCP (Model Context Protocol), and APIs.

## Key Capabilities

- Agents "click and type on a screen, write and run their own code, and call MCP or API tools"
- Adapts to whatever interface suits the task (no single-interface specialization)
- Works across: desktops, web applications, Android devices, code sandboxes, business APIs

## Performance

- OSWorld 2.0: Holo4-27B achieves 61.7% (vs Qwen3.8 27B baseline)
- Competitive with frontier systems at substantially lower cost

## Training

- Supervised fine-tuning on 127 billion tokens + reinforcement learning
- ~10,000 tasks generated via H Company's internal Agentic Task Factory
- Task Factory creates interactive environments and verifiable tasks from documentation and screenshots

## Availability

- H Models API
- Hugging Face (BF16, FP8, NVFP4, 4-bit GGUF formats)

## Significance for AI Founders

Holo4 represents a major step in open-weights computer-use agents — frontier-competitive performance at a fraction of closed-model costs. The Agentic Task Factory approach (generating verifiable tasks from docs/screenshots) is a novel training data strategy applicable to other agentic systems.
