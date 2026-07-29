# LFM2.5-Encoders for Fast Long-Context Inference on CPU
# URL: https://huggingface.co/blog/LiquidAI/lfm2-5-encoders
# Date: 2026-07-28
# source: Hugging Face Blog (Liquid AI)
# Author: Liquid AI team

## Overview

Liquid AI released two new encoder models designed for efficient document-scale processing on standard hardware, including CPUs.

## Key Models

- **LFM2.5-Encoder-230M** and **LFM2.5-Encoder-350M**
- Optimized for extended input sequences with strong performance/efficiency tradeoff

## Technical Architecture

Adapted from decoder models through three primary modifications:

1. **Attention mechanism**: Changed from unidirectional to bidirectional, allowing tokens to attend to context on both sides
2. **Convolution adjustments**: Modified short convolutions to symmetric padding for balanced context mixing
3. **Training approach**: Applied masked language modeling with 30% token masking

Training: Two phases — initial masked-language work at 1,024-token context, then extension to 8,192 tokens across diverse data.

## Performance Results

- 350M model ranked 4th among 14 tested encoders on combined GLUE, SuperGLUE, and multilingual benchmarks
- 230M variant "beat ModernBERT-base and every EuroBERT model, while being smaller than most" competitors

## Speed Advantages

On CPU at maximum context length (8,192 tokens):
- LFM2.5-Encoder-230M is ~3.7× faster than ModernBERT-base
- Completes 8,192-token inference in ~28 seconds vs. 90+ seconds for comparison models

## Practical Applications

- Intent routing
- Policy linting
- PII detection
- Spell-checking
- Text classification
- All executable on consumer-grade hardware at production scale
