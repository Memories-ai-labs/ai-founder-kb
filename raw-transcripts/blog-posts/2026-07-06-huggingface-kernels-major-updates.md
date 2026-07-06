Title: 🤗 Kernels: Major Updates
Publisher: Hugging Face
Authors: Sayak Paul, Daniël de Kok, David Holtz, and contributors
URL: https://huggingface.co/blog/revamped-kernels
Date: 2026-07-06
Source: Hugging Face Official Blog

---

## Overview

Hugging Face announced substantial redesigns to its Kernels project, which standardizes how custom GPU kernels are packaged and distributed across the AI ecosystem. The goal: make kernel development "frictionless and secure, while making it as Hub-friendly as possible."

## Key Updates

### New Repository Type
A dedicated kernel repository category now exists on Hugging Face Hub, allowing developers to showcase:
- Accelerator support (CUDA, ROCm, etc.)
- Operating system compatibility
- Backend compatibility information

Kernels are now first-class citizens on the Hub, discoverable alongside models and datasets.

### Enhanced Security Features
- **Trusted publisher verification**: Explicit opt-in system for untrusted kernel sources
- **Code signing**: Using Sigstore's cosign with ephemeral keys
- **GitHub workflow verification**: Cryptographic verification of kernel authenticity
- Addresses supply chain security concerns for GPU kernel distribution

### Refined CLI Tools
The `kernels` and `kernel-builder` CLIs were reorganized for cleaner separation:
- Loading functionality (using kernels in production)
- Building functionality (developing and compiling kernels)

### Framework Expansion
Support now includes:
- **Torch Stable ABI**: Enables PyTorch-compatible kernels across versions
- **Apache TVM FFI**: Cross-framework kernel compatibility
- Broader ecosystem reach beyond pure CUDA/PyTorch workflows

### Agentic Development Support
Infrastructure improvements enable AI agents to:
- Scaffold new kernels automatically
- Build and compile through automated workflows
- Benchmark performance
- Iteratively optimize kernel implementations

This positions Kernels as infrastructure for AI-generated GPU optimization — a signal that kernel engineering itself is becoming an agentic/automated discipline.

### Technical Improvements
- Simplified environment setup with installation scripts
- System cards documenting kernel interfaces and usage
- Dynamic `libstdc++` linking with manylinux_2_28 toolchain for cross-distro stability

## Significance for AI Founders

Custom GPU kernels are a primary lever for inference cost reduction and throughput optimization. By making kernel development more accessible and secure:
1. Smaller teams can now publish and consume optimized kernels previously only accessible to large labs
2. Agentic kernel optimization could dramatically accelerate the inference cost-performance curve
3. Hub-native kernels reduce the ops burden of deploying custom hardware optimizations
