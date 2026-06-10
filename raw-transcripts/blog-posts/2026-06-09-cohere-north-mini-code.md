---
Title: Introducing North Mini Code: Cohere's First Model For Developers
Publisher: Cohere / Hugging Face
URL: https://huggingface.co/blog/CohereLabs/introducing-north-mini-code
Date: 2026-06-09
Source: Hugging Face Blog
---

# Introducing North Mini Code: Cohere's First Model For Developers

**Published:** June 9, 2026
**Source:** https://huggingface.co/blog/CohereLabs/introducing-north-mini-code

## Overview

Cohere introduced North Mini Code, a 30-billion parameter Mixture-of-Experts model featuring 3 billion active parameters. The model is specifically engineered for agentic software engineering tasks and released under the Apache 2.0 license on Hugging Face.

## Key Capabilities

North Mini Code excels at complex coding workflows. The model achieved a score of 33.4 on Artificial Analysis' Coding Index, outperforming several larger competitors including models with 120+ billion parameters. The system handles "terminal-based agentic tasks, and high-quality code generation."

## Architecture

The model uses a decoder-only Transformer with sparse Mixture-of-Experts design:
- 128 experts with 8 activated per token
- Interleaved sliding-window self-attention and full self-attention in a 3:1 ratio

## Training Approach

- Two supervised fine-tuning (SFT) stages followed by reinforcement learning with verifiable rewards (RLVR)
- Second SFT stage: 4.5 billion tokens from high-quality agentic and reasoning samples
- Code represents 61% of trainable tokens
- Training used over 70,000 verifiable tasks across ~5,000 unique repositories

## Performance Improvements from RLVR

- +7.9% absolute on Terminal-Bench v2 vs. SFT baseline
- +3.0% on SWE-Bench vs. SFT baseline

## Availability

- BF16 and FP8 quantized versions via Hugging Face, OpenCode, and Cohere's API
- Apache 2.0 license
