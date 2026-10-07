# One Model Family, Two Gold-Level Results: Fine-Tuning Nemotron for IOI and IMO
# URL: https://huggingface.co/blog/nvidia/fine-tuning-nemotron-ioi-imo
# Date: 2026-10-07
# Source: HuggingFace Blog / NVIDIA

NVIDIA's Nemotron model family achieved gold-medal-level results at both the International Mathematical Olympiad (IMO) 2026 and the International Olympiad in Informatics (IOI) benchmark using the same base architecture with targeted fine-tuning.

## IMO Results

A Nemotron-based system scored 30 out of 42 points at the International Mathematical Olympiad (IMO) 2026. The IMO team graded the solutions and certified the score was equivalent to a Gold Medal for a human participant. The final submission used an ensemble of three models, all based on the Nemotron-3-Ultra architecture.

## IOI Benchmark

Nemotron 3 Ultra scored 570 on the IOI benchmark (competitive programming).

## Open Source

NVIDIA plans to open-source the entire pipeline — releasing:
- The models
- All training data
- Software for training and inference
- The full recipe

## HuggingFace Distribution

Model weights are distributed on Hugging Face through the official NVIDIA-NeMo/Nemotron repository. The NVIDIA-NeMo/Nemotron repo exposes the full Pretrain → SFT → RL pipeline, with teams building domain-specific variants able to start with the SFT recipe.

## Significance

This result demonstrates that targeted fine-tuning from a strong open-weight base model can achieve frontier-level performance on hard reasoning tasks previously considered exclusive to proprietary systems.

[NOTE] Full blog post text not retrieved due to access restrictions; content reconstructed from search results.
