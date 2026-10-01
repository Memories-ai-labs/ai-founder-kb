# Gemini 4 Argon: our next era of frontier intelligence
# URL: https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-4-argon/
# Date: 2026-09-30
# Source: Google DeepMind / Google Blog

Author: Koray Kavukcuoglu, SVP of Google DeepMind and Chief AI Architect

## Overview

Gemini 4 Argon is Google's new frontier model designed for complex professional workflows. The system features an industry-leading context window of 1 million tokens for output, enabling extended reasoning across multi-step problems.

## Performance Benchmarks

- **DeepSWE v1.1:** 77.9% (real-world software engineering tasks)
- **Vals Index:** Leading performance across finance, coding, legal, and tax sectors
- **AutomationBench:** 51.3% (ranked #1)
- **LVBench:** 91.7% (long video understanding)
- **CWE-bench v1:** 68% (vulnerability remediation, tied for first)

## Real-World Applications

Internal Google deployments demonstrate impact in:
- Quantum optimization (40% improvement over baselines)
- Memory efficiency (300+ TiB freed across data centers)
- Large-scale codebase migrations including C/C++ to Rust conversions up to 800K+ lines

## Cybersecurity Focus

Argon excels at identifying and patching vulnerabilities. Wiz's "Scan for Good" initiative uncovered a critical healthcare vulnerability previously undetected by competing models. Google states it can "autonomously find, validate, and patch critical software vulnerabilities."

## Safety Measures

Before broader release, Google implements:
- Misuse prevention
- Prompt injection robustness
- Misalignment monitoring through chain-of-thought analysis
- Hardened sandboxed environments

## Pricing and Availability

**Introductory pricing:** $2 per million input tokens, $10 per million output tokens (cached inputs at 95% discount). Rolling out initially through the Fairwind Program to cyber defenders, with broader availability to follow. Currently limited to a select group.

## Competitive Context

Google's Gemini app has reached one billion monthly active users. According to Vals benchmarking, Argon outperforms OpenAI's GPT-6 Astra and Anthropic's Fable and Opus offerings on their AI model index.
