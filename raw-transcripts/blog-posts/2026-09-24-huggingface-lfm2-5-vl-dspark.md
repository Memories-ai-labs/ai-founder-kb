# Accelerating vision-language models with LFM2.5-VL-DSpark
# URL: https://huggingface.co/blog/LiquidAI/lfm2-5-vl-dspark
# Date: 2026-09-24
# Source: Hugging Face Blog

**Published:** September 24, 2026
**Authors:** Liquid AI team (Johnny Nuñez Cano, Asier Arranz, Rishabh Chadha, Ben Oliveri, and others)

---

Liquid AI introduced an experimental DSpark draft model for their LFM2.5-VL-3B vision-language model. This release focuses on speculative decoding—a technique that accelerates inference by trading modest memory increases for substantial speed improvements without affecting output quality.

## Key Performance Metrics

The implementation delivers impressive speed gains: "decode speedups up to 3.13x on device and 2.66x on an H100, with end-to-end gains up to 2.62x and 2.27x." The memory overhead remains minimal, as the drafter incorporates only 280 million parameters, representing "8.9% on top of the 3B target."

## Technical Approach

The vision drafter architecture mirrors the text-based DSpark models. It captures hidden states from specific layers and uses them to propose candidate tokens. Since "image patches and text tokens are projected into a shared representation before those layers," the inference process remains consistent across modalities.

The model uses a simplified attention-only drafter with 4 layers and a block size of 9, trained across "10 epochs on the final mixture" before reaching performance plateaus.

## Practical Limitations

The team acknowledged that speculative decoding shows reduced benefits for vision workloads compared to text models. Since "speculative decoding speeds up only decode, not vision encoding or prefill," and prefill stages consume substantial time in vision tasks, overall end-to-end improvements are constrained by Amdahl's law.

## Implementation Support

Day-one support exists for three major frameworks: llama.cpp, MLX-VLM, and SGLang, with specific configuration examples provided for each platform.
