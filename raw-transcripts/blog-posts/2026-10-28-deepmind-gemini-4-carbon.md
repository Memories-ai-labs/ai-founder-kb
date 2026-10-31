# Gemini 4 Carbon: our next frontier model
# URL: https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-carbon/
# Date: 2026-10-28
# source: deepmind

Author: Koray Kavukcuoglu, SVP Google DeepMind and Chief AI Architect, Google
Published: October 28, 2026

## Overview
Google's next frontier model, described as its strongest to date. Builds on Gemini 4 Argon (released ~2 weeks earlier). Strong cybersecurity and long-horizon task capabilities.

## Key Capabilities

**Benchmarks:** Ranks #1 on Artificial Analysis Intelligence Index v5.0 with score of 59.

**Coding and agentic work:** Designed for long, multi-step engineering tasks. Internal teams have seen it run for days, working through dead ends to root-cause and patch bugs in large codebases.

**Web development:** Gained 89 Elo points on WebDev Arena, reaching #4 with score of 1768.

**Cybersecurity (state-of-the-art results):**
- SEC-bench Pro (finding vulnerabilities): 88.2%
- ExploitGym (exploitation): 54.8%
- CWE-bench (patching): 71.0%
- Over 2x improvement in generating secure code versus Argon
- Chrome team reported better patch quality than another lab's large model

## Safety and Alignment
- Reduced successful cheating on Terminal-Bench 4.0 to 0.0%, cheating attempts to 0.4%
- Internal high-severity misalignment alerts in live coding environments dropped ~80%
- Unsupported claims roughly halved vs Argon
- Overreach fell 26%, under-service fell 29%
- Scored 0.0% attack success on Gray Swan prompt-injection benchmark (vs Argon's 0.7%)

## Rollout and Pricing
**Phased release:** First to subset of cyber defenders, then trusted partners via Fairwind Program. Participating in U.S. government voluntary pre-release model testing.

**Pricing:**
- Introductory: $2/M input tokens, $10/M output tokens (cached input 95% off)
- After intro period: $4/M input, $20/M output

## Significance
Strongest frontier model yet from Google. Focus on cybersecurity and long-horizon agentic tasks signals Google's differentiation strategy. Safety improvements (especially misalignment alerts -80%) represent meaningful trust-building investment ahead of broader deployment.
