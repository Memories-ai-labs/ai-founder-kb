# Building on Nemotron 3.5 Parse: Open Data, Fine-Tuning, and Faster Inference
# URL: https://huggingface.co/blog/nvidia/building-on-nemotron-35-parse-open-data-fine-tunin
# Date: 2026-11-26
# source: Hugging Face Blog (NVIDIA — Ryan Chesler, Marek Wawrzos, Steve Han)

Authors: Ryan Chesler, Marek Wawrzos, Steve Han (NVIDIA)

## Summary

Nemotron 3.5 Parse is a compact document model that turns page images into structured data for RAG and agents. Outputs reading-order content, content classes, bounding boxes, and structured tables and charts.

## Open Datasets Released

- Synthetic Charts V1: 9.98M examples
- Synthetic Tables V1: 1M examples
- OCR Synthetic Multilingual v2: 7.9M examples

## Training Method

1. Supervised fine-tuning (SFT)
2. Reinforcement learning with verifiable rewards (RLVR) via GRPO
   - Loop-flagged pages fell from 126 → 29
   - Overall score: 66.24 → 71.38

## Architecture Improvements

- Dynamic NaViT image inputs
- Grouped-query attention
- Multi-token prediction (DFlash2 speculator: proposes up to 32 tokens ahead)
- Throughput on H200 (concurrency 512): 20.44 pages/s (DFlash2) vs 2.98 pages/s (Parse 2.0)

## Multi-Pass Refinement

- Double pass: +2.18 ParseBench points over single-pass
- Triple pass: +2.46 ParseBench points
- Trade-off: some throughput reduction

## Fine-Tuning Recipe

- NeMo Automodel SFT + NeMo RL GRPO
- Synthetic dental-form example: base model 0.00% → SFT 95.85% → RLVR 96.58% first-attempt success

## Community

Existing community adaptations for Thai, Persian/Farsi, and Arabic.
