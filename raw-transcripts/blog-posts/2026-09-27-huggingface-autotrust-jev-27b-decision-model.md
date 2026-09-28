# autotrust/JEV-27B: Fast, Calibrated Decisions and Full Reasoning from One Open Model
# URL: https://huggingface.co/blog/autotrust/autotrustjev-27b-fast-calibrated-decisions-and-ful
# Date: 2026-09-27
# Source: Hugging Face Blog

**Authors:** Josh Liu, Hai Yu, Daniel Tang, and team at AutoTrust AI Lab

## Overview

AutoTrust AI introduced an open-weights decision model designed for rapid, calibrated judgments on categorization tasks. The model achieves performance metrics comparable to TypeSafe's proprietary Jev 1.13 while maintaining the ability to perform step-by-step reasoning.

## Key Capabilities

The model handles three question types:
- **Boolean assessments** returning probability distributions
- **Multiple-choice selections** with per-option probabilities
- **Scale ratings** (0-5) with expected score calculations

Each decision completes in a single forward pass without decoding or parsing requirements.

## Performance Highlights

- Averages 84.07 on six public benchmarks vs. closed model's 83.85
- Distribution-level alignment: mean KL ≈ 0.017 on held-out questions
- Achieves approximately 100 decisions per second on an H100 GPU
- Preserves base model capabilities: HumanEval 78.0% before and after

## Technical Architecture

Uses a "Blocks of Experts" approach: a frozen Qwen backbone paired with a lightweight trainable component (108.9M parameters) rather than full fine-tuning. This separation prevents degrading the model's general reasoning capabilities while adding decision-making expertise.

## Availability

Available under Apache 2.0 licensing at `autotrust/JEV-27B` on Hugging Face.
