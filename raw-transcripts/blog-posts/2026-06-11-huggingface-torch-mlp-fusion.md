# Profiling in PyTorch (Part 2): From nn.Linear to a Fused MLP

**Title**: Profiling in PyTorch (Part 2): From nn.Linear to a Fused MLP
**Publisher**: Hugging Face
**URL**: https://huggingface.co/blog/torch-mlp-fusion
**Date**: 2026-06-11
**Source**: Hugging Face Blog

---

This technical article examines GPU kernel optimization through PyTorch profiling. Building on Part 1's foundations, the post demonstrates how "the bias addition has been folded into the matrix multiplication kernel" using epilogues to avoid redundant memory access.

The authors trace three implementations of a multi-layer perceptron:

1. **Eager execution** — Five separate GPU kernels handling matrix operations and activations
2. **torch.compile** — Fuses the GeLU activation and multiplication into one Triton kernel, eliminating intermediate memory traffic
3. **Hand-tuned Liger kernels** — Achieves similar fusion without compilation overhead or shape-specific specialization

A central insight: "torch.compile specializes for a static shape," requiring recompilation when dimensions change, whereas hand-written kernels maintain consistent launch parameters across varying inputs.

The post emphasizes practical profiling methodology: forming expectations before examining traces helps identify optimization opportunities. The authors demonstrate concrete performance analysis using NVIDIA A100 GPUs and provide reproducible scripts for readers.
