---
Title: LFM2.5 Q4_0 Checkpoints from Quantization-Aware Distillation
Author: Liquid AI (Aditya Tadimeti, Leonie Monigatti et al.)
URL: https://huggingface.co/blog/LiquidAI/qad
Date: 2026-08-19
Source: Hugging Face Blog
---

## Summary

Liquid AI releases quantized model checkpoints for four LFM2.5 variants using Quantization-Aware Distillation (QAD) — a technique that trains a high-precision teacher model to guide a quantized student model, enabling efficient edge deployment without the typical quality losses of post-training quantization.

## Models Released

- LFM2.5-230M, 350M, 1.2B-Instruct, and 2.6B (Q4_0 quantized)
- Evaluated across GPQA Diamond, MMLU-Pro, IFEval, GSM8K, AIME25

## Key Results

- Recovery rate: QAD recovers 97% of accuracy lost to quantization vs. BF16 baseline
- QAD Q4_0 matches higher-precision quantization formats while being 3-33% faster at decode
- Tested on MacBook Pro, NucBox, Samsung Galaxy S26 Ultra, Raspberry Pi 5

## Technical Approach

QAD trains a high-precision teacher model whose outputs guide the quantized student at training time. This is different from post-training quantization (PTQ) which quantizes after training and typically incurs larger quality losses.

## Significance

LiquidAI continues to advance edge-deployable AI for on-device agent workflows. Combined with their prior LFM2.5-VL edge vision model (Aug 12) and 2.6B local agent work (Aug 4), this represents a systematic push toward capable, locally-deployable AI agents — directly competing with Apple Intelligence and Google's on-device Gemini models.
