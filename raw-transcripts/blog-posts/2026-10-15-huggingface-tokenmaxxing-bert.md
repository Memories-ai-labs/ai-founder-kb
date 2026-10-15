# Tokenmaxxing BERT: 50x faster tokenization
# URL: https://huggingface.co/blog/huggingface/tokenmaxxing-bert
# Date: 2026-10-15
# Source: Hugging Face

Author: Simon Brandeis (sbrandeis), Hugging Face
Published: October 15, 2026

## Summary

Pre-release post covering work on the 🤗 tokenizers library, delivering up to 50× faster BERT-style tokenization ahead of a planned v1.0.0 release.

## Context

- BPE tokenizers (used by most LLMs) already encode up to 30× faster than in v0.23
- BERT-style models lagged at ~8.6× before this work
- BERT-style models remain widely used for embeddings, search, RAG, reranking, and classification
- The three most-downloaded Hub models all use BERT's normalizer

## Main Findings

- `bert-base-uncased` now up to 5.7× faster, ~50× faster than v0.23 in total
- ~88% of encoding time was going to Unicode accent-checking (binary search) — now optimized
- Token IDs identical to previous implementation across all benchmark corpora
- English text normalizer share: 88% → 13%; throughput: 23 MB/s → 151 MB/s

## Technical Highlights

- **ASCII skipping:** UTF-8 ASCII bytes have clear high bit; SIMD checks 16 bytes at once
- **Page cache:** Normalization decisions cached per 256-code-point block (text usually uses few scripts)
- **Avoiding allocations:** Unchanged input returned without copying
- **ModernBERT (NFC):** Smaller gains for NFC-normalized text; code/Arabic/Russian ~2× faster

## Caveats

- Very small inputs (≤32 bytes) can run slower
- CJK text gains little; cased BERT on Chinese 8–15% slower from 64 bytes up

## Significance

A 50× tokenization speedup for BERT-style models materially reduces latency and cost in high-volume RAG, reranking, and embedding pipelines. Important for teams running inference at scale.
