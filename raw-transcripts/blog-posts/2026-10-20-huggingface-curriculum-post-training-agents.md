# A curriculum for post-training agents
# URL: https://huggingface.co/blog/huggingface/train-agents
# Date: 2026-10-20
# Source: Hugging Face Blog
# Authors: ben burtenshaw, Sergio Paniego, merve

[NOTE] Technical blog post — no podcast audio.

---

Overview: Post-training stages that make a model follow instructions, use tools, or solve specific tasks. Agentic post-training applies these stages to agents that work over many turns, requiring training to consider the whole sequence of actions rather than a single answer.

Five steps (using a coding agent as running example):

1. **Supervised Fine-Tuning (SFT):** Model learns from agent traces produced by a stronger model. Cheap and stable, but only sees correct traces so never learns to recover from its own mistakes. Trainer: `SFTTrainer`.

2. **Distillation:** Teacher model guides student, either through its written data or token probabilities. Dense signal; needs fewer samples than RL. Limited by teacher's knowledge; on-policy distillation requires running the teacher during training. Trainer: `DistillationTrainer`.

3. **Reinforcement Learning (RL):** Model learns from a score on its own answers, using GRPO (Group Relative Policy Optimization). Samples several answers per prompt and favors those scoring above the group average. Signal is weaker; each answer is a single scored turn. Trainer: `GRPOTrainer`.

4. **RL Environments:** Rewards come from acting in an environment that keeps state, exposes tools, and responds over several turns (e.g., runs coding task's tests). Episodes are longer, so generating rollouts becomes the bottleneck. Trainer: `GRPOTrainer` with OpenEnv.

5. **Harnesses and Scale:** Each rollout is a full run of an existing agent harness in a remote sandbox, so model trains in the setting where it will actually run. Generation and training run on separate GPUs; updated weights sent back to vLLM. Trainer: `AsyncGRPOTrainer`.
