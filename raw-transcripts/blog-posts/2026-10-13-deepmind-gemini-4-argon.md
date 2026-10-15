# Gemini 4 Argon: Built to solve your hardest problems
# URL: https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-argon/
# Date: 2026-10-13
# Source: Google DeepMind

Author: Koray Kavukcuoglu, SVP Google DeepMind and Chief AI Architect, Google
Published: October 13, 2026

## Overview

Google releases Gemini 4 Argon, its latest frontier model, targeting developers, enterprises, scientists, and consumers. Built for multi-step complex work in coding, finance, legal, cybersecurity, and science.

## Key Capabilities

**Engineering:**
- Agentic code submissions +35% in Google's Antigravity platform
- Code rollbacks cut by nearly a third
- Use cases: refactoring Chrome code, optimizing Agent Development Kit, speeding up xTB and Gemma inference

**Professional Work:**
- Multimodal document analysis, longitudinal data, structured writing
- Follows style instructions better than earlier Gemini models; hedges less

**Research:**
- Quantum error-correction work
- Counterexample to Grad's conjecture in stellarator research
- Rare-disease genome analysis and enzyme design

**Robotics:**
- Turned a video of a cornhole game into simulation code transferred to a humanoid robot

**Context:**
- 1M-token unified input-output limit in the Gemini API

## Benchmarks

- #1 on Vals Index (finance, coding, legal, tax)
- 87% on Embodied Reasoning (ERQA) benchmark
- 57% on RareBench (rare-disease diagnosis)
- 52.2% on LabBench (wet-lab reasoning) — Gamow Labs private evals
- 2.3× faster xTB molecular structure prediction
- 2.85× end-to-end inference speedup for Gemma 4 E2B on A100 via vLLM
- #1 on Gray Swan Indirect Prompt Injection benchmark; attack success cut to 0.7% across 15 adaptive attempts
- Cursor CursorBench: ~52.8% (per Latent Space AINews)

## Pricing

- Introductory (through Nov 30, 2026): $2/M input tokens, $10/M output tokens; cached input 95% cheaper
- After Nov 30, 2026: $4/M input, $20/M output

## Availability

- Developers/enterprises: Google AI Studio and Gemini API, rolling out globally
- Google AI Ultra subscribers: Antigravity platform
- Scientists: Free access applications open (6 months, highest usage tier, eligibility-gated)
- Cybersecurity defenders: Fairwind Program (expanding to hundreds more partners)

## Safety

- Multi-layer defense stack against misuse and jailbreaks
- Automated monitor for agent misalignment
- Prompt-injection resistance (#1 Gray Swan benchmark)
- Full Gemini 4 Argon Model Card published

## Significance for AI Founders

Gemini 4 Argon's $2/$10/M introductory pricing at near-parity with GPT-6 Astra quality is the most significant competitive pricing development since GPT-4o mini. The 35% agentic code improvement and multi-step reasoning capabilities signal Google catching up in coding-agent quality. The November 30 pricing doubling creates a 6-week adoption window for teams to evaluate and commit.
