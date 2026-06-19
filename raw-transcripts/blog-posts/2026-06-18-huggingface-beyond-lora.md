# Beyond LoRA: Can You Beat the Most Popular Fine-Tuning Technique?

Title: Beyond LoRA: Can You Beat the Most Popular Fine-Tuning Technique?
Publisher: Hugging Face
Authors: Benjamin Bossan, Sayak Paul, Marian (hubnemo), and Kashif Rasul
URL: https://huggingface.co/blog/peft-beyond-lora
Date: 2026-06-18
Source: Hugging Face Blog

---

## Article Summary

This Hugging Face blog post challenges the assumption that LoRA (Low-Rank Adaptation) is the optimal choice for parameter-efficient fine-tuning (PEFT). While LoRA dominates the landscape — accounting for roughly 98% of fine-tuning mentions on Hugging Face Hub — the authors argue this dominance stems partly from visibility and self-reinforcing popularity rather than proven superiority.

## Key Findings

The authors conducted systematic benchmarks comparing multiple PEFT techniques across different tasks:

**Math Fine-Tuning (MetaMathQA):** While LoRA achieved 53.2% test accuracy using 22.6 GB VRAM, other techniques like BEFT and Lily offered better performance-memory tradeoffs depending on priorities.

**Image Generation:** Most strikingly, OFT outperformed LoRA on the cat plushy learning task, achieving "0.708 similarity versus LoRA's 0.697" while requiring less memory (9.01 GB vs 9.97 GB).

## Critical Insights

The authors highlight that comparing PEFT techniques through published research is problematic because researchers face pressure to demonstrate their methods outperform existing benchmarks. They note that "LoRA can match supposedly better PEFT techniques by tuning the learning rate."

## Practical Solutions

The team created interactive benchmarking tools and made switching between techniques straightforward using the PEFT library's unified API. They also developed conversion capabilities allowing non-LoRA adapters to be converted to LoRA format for compatibility with downstream tools like vLLM.

## Main Conclusion

While LoRA remains effective, practitioners should evaluate alternatives through systematic testing rather than assuming LoRA is universally optimal.
