# Introducing harness adapters: adapt your favorite model to your harness to improve performance and cost
# URL: https://huggingface.co/blog/harness-adapters-at-scale
# Date: 2026-11-20
# Source: Hugging Face Blog

Authors: Younes B, ben burtenshaw, Nathan Habib, Lysandre, Amine Dirhoussi, Adithya S K, shaun smith, Sergio Paniego, Joel Niklaus, Lewis Tunstall

## Core insight

General-purpose models are not tuned for specific agent harnesses, leaving accuracy and efficiency gains on the table. Training a small LoRA adapter with reinforcement learning (RL) **inside the actual target harness** — while keeping base weights frozen — can substantially improve both.

Example result: Qwen3.8-27B under the pi harness improved from 39% to 55% pass@1 on Terminal-Bench 2.1, while average tokens per task fell from ~2.9K to ~1.5K.

## Method

- Adapters trained inside real harnesses (Pi, OpenCode, Hermes Agent) — not re-implemented loops
- Used TRL's `AsyncGRPOTrainer`, OpenEnv, and Harbor on Hugging Face
- Task pipeline: SWE-smith + SWE-Gym (via TaskTrove) + Tasksmith-generated tasks
- Difficulty filter: kept only tasks the base model solves sometimes (171 of 858 validated tasks)
- Final dataset: 871 tasks across 35 repositories
- LoRA on all linear layers, lr=2e-5; reward = correctness + small tool-efficiency bonus
- safeagents plugin blocked ~647 of ~1.3M tool calls during training

## Super-adapter

Three harness LoRAs concatenated into one rank-96 adapter applied at half weight. Runs unchanged under all three harnesses with the best cross-harness balance.

## Results

- Each specialist adapter beat the base model under its own harness
- Pi on SWE-bench Pro: ~39% → ~65%
- Super-adapter improved on base model across all 6 harness-benchmark pairs (no thinking mode)
- With thinking mode: improved 5 of 6 pairs
- Out-of-distribution (AutomationBench): no clear transfer; results near base model

## Significance for AI builders

This technique enables builders to cheaply customize commodity models to specific agent workflows without full fine-tuning or changing base weights. The RL-in-harness approach creates task-specialized agents that are both more accurate and dramatically more token-efficient — directly relevant to production agent cost and reliability.

Full recipe, datasets, adapters, and plugin released openly.
