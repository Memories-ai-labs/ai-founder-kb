# Fine-tuning a 350M Model for Better Structured Outputs in 100 GRPO Steps
# URL: https://huggingface.co/blog/grpo-with-trl-ifstruct
# Date: 2026-09-03
# Source: Hugging Face Blog

**Authors:** Leonie Monigatti, ben burtenshaw, Sergio Paniego, and contributors from Liquid AI

The authors demonstrate that lightweight task-specific fine-tuning using Group Relative Policy Optimization (GRPO) can substantially improve structured output compliance in small language models. By training the 350M parameter LFM2.5 model on approximately 500 samples over just 100 steps — feasible on free-tier GPUs — they achieved a 7.1 percentage point improvement on the IFStruct benchmark, rising from 22.6% to 29.7%.

## Technical Approach

The approach employs three reward functions targeting:
1. JSON format validity
2. Field count accuracy
3. Schema compliance

Gains are concentrated in JSON output generation rather than YAML, suggesting the training effectively targets its intended objectives while remaining computationally affordable.

## Key Insight

A 350M model can be meaningfully improved for production structured-output tasks (JSON schema compliance) using only ~500 labeled examples and 100 optimization steps on commodity compute. This makes task-specific alignment economical for startups building on small/efficient models.
