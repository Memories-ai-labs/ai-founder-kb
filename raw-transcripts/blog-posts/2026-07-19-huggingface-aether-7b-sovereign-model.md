---
Title: Aether-7B-5Attn: A 100% Open-Source Sovereign Foundation Model
Source: Hugging Face Blog
URL: https://huggingface.co/blog/FINAL-Bench/opensource-llm
Date: 2026-07-19
Publisher: Hugging Face (VIDRAFT / FINAL-Bench)
Authors: VIDRAFT (비드래프트)
---

# Aether-7B-5Attn: A 100% Open-Source Sovereign Foundation Model

**Publication Date:** July 19, 2026

**Authors/Organization:** VIDRAFT (비드래프트), published under FINAL-Bench on Hugging Face

**URL:** https://huggingface.co/blog/FINAL-Bench/opensource-llm

---

## Summary

Aether-7B-5Attn is a decoder-only transformer with 6.59B total parameters (~2.98B active per token) trained by a single Korean AI startup. Its distinctive design arranges five distinct attention mechanisms in a 7×7 Latin square pattern — ensuring each attention type appears exactly once per depth band.

---

## Architecture

- **Parameters**: 6.59B total, ~2.98B active per token
- **Layers**: 49
- **Attention innovation**: 5 attention mechanisms arranged on 7×7 Latin square (differential, native sparse, sliding window, and hybrid attention variants)
- **Context length**: 4,096 tokens with RoPE positional encoding
- **License**: Apache-2.0

---

## Training

- **Data**: 144.2B tokens
  - Math: 37.8%
  - Korean: 21.6%
  - English: 21.6%
  - Code: 13.5%
- **Hardware**: 16× NVIDIA B200 GPUs
- **Duration**: ~46 days

---

## Key Claims

- First fully-open foundation model built by a single AI startup (not a national lab or consortium)
- First Korean model to open both training data and training code
- Research contribution: controlled placement of existing attention mechanisms (the Latin square design), not a new attention mechanism per se

---

## Relevance for AI Founders

- Demonstrates a single small team can train a competitive 7B foundation model with B200 GPUs in ~46 days — signals compute accessibility for sovereign/specialized foundation models
- Apache-2.0 license on training code lowers barrier for others to replicate or adapt
- Korean/math/code training mix reflects sovereign model strategy: maximize capability in strategic domains + native language
