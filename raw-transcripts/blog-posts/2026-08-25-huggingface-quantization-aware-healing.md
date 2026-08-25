# Quantization-Aware Healing: a compressed, 4-bit model that outperforms its full-precision original
# URL: https://huggingface.co/blog/MultiverseComputingCAI/quantization-aware-healing
# Date: 2026-08-25
# Source: HuggingFace Blog

Authors: Antonio Tiene, Iker García-Ferrero, Ali Hashemi, Bakbergen Ryskulov (Multiverse Computing)

Multiverse Computing introduces Quantization-Aware Healing (QAH), a recovery method that allows heavily compressed 4-bit models to exceed the accuracy of their full-precision counterparts. Applied to GPT-OSS 120B compressed to 60B parameters and quantized to MXFP4, the resulting model outperformed its bfloat16 version on 7 of 9 benchmarks.

## Core Innovation

The approach diverges from standard quantization methods by distilling "directly from the original, pre-compression model rather than from the recovered one." This eliminates the performance ceiling imposed by using degraded intermediate checkpoints as teachers.

## Performance Gains

- Long-context reasoning: +7.4 points on AA-LCR
- Mathematics: +5.6 points on AIME 2025
- Code generation: +2.7 points on Aider

## Training Stability

QAH demonstrates superior stability compared to Quantization-Aware Training (QAT): reaches peak performance in ~100 steps versus 700, while remaining stable rather than degrading.

## Practical Implications

Method reduces weight memory usage by approximately 75% while maintaining or improving accuracy, making deployment more efficient and cost-effective. Founders building inference infrastructure can achieve significant cost reductions without sacrificing model quality.
