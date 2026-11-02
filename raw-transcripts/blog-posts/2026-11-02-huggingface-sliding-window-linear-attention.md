# Sliding window beats linear attention, but only on short answers
# URL: https://huggingface.co/blog/sirluk/sliding-window-beats-linear-attention
# Date: 2026-11-02
# Source: Hugging Face Community Blog
# Author: Lukas (sirluk)

## Summary

A distillation experiment comparing sliding window attention (SWA) with attention sinks vs. "Bifocal" (hybrid SWA + mLSTM linear mixer) at equal memory budgets. Key finding: SWA is the stronger baseline for short answers, but linear mixers help on long-generation tasks.

## Setup

- Base model: Qwen3-4B-Instruct
- Four student models distilled with equal memory per attention layer (576 cached tokens equivalent)
- Equal 4.1B-token training budgets
- SWA variants: learned sink vs. pinned sink tokens
- Bifocal: splits memory between a small sliding window and an mLSTM linear state, blended by a learned gate

## Results

**Short answers (GSM8K, IFEval, HumanEval):**
- SWA with learned sink wins by 0.7–1.5 points
- Conclusion: at equal memory, a larger window beats a linear state for short generations

**Long answers (AIME, HMMT math — ~7,600 token answers):**
- Bifocal: 15.5% average vs. SWA: 13.8%
- On the 96 longest-answer problems: Bifocal solved 4.4% vs. SWA 2.5% (~1.8x more)
- Gap is near edge of statistical significance (95% CI: 0.0 to 3.4 points, 120 problems)

**Ablation — linear state without enough window:**
- Bifocal variant with 64-token window + larger linear state → collapsed to 4.2% on math
- Conclusion: exact recent-token recall (the window) is still necessary; linear state alone insufficient

**Decoding speed:**
- Bifocal and SWA decode at same speed (~195 tokens/s) from 1K–128K prompt tokens
- Bifocal prefill is slower: 63%–83% of SWA speed

## Recommendations

1. SWA with attention sinks should be the reported baseline (often omitted in papers)
2. Comparisons should be at equal memory, not equal parameter count
3. Evaluate on long generations, not just short benchmarks
4. Combining a window with a linear mixer can help on long answers without hurting decode speed

## Significance

Practically relevant for anyone choosing architectures for long-horizon reasoning tasks (code generation, math, agent reasoning chains). Suggests hybrid SWA+linear models merit attention for agent use cases requiring long outputs.
