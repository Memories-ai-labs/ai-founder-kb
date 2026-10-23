# Turning Database Grading into RL Rewards: Post-Training Agents with ThinkingBox
# URL: https://huggingface.co/blog/microsoft/thinkingbox-training
# Date: 2026-10-22
# Source: Hugging Face Blog (Microsoft x Hugging Face)

Author: Tuhin Kundu (Microsoft)

ThinkingBox grades agents by comparing final database state to the expected outcome. The authors reused this 1-or-0 signal as a reinforcement learning reward for training tasks outside the benchmark.

**Key findings:**
- Executable checks as rewards: ThinkingBox's 1-or-0 success signal (did the DB state match expected outcome?) used directly as RL reward
- Task selection: Tasks always solved or never solved give no learning signal in GRPO. Authors estimated success probability on base model and kept middle-difficulty tasks ("offline policy-relative difficulty")
- Training: Qwen3.8-27B fine-tuned with GRPO for 50 steps on 187-task pool, on 24 H100 GPUs
- Results on 507-task benchmark:
  - Average pass@1 rose from 51.70% to 60.78%
  - Tasks passed on all 20 attempts rose from 38 to 107
  - Cost per dependable task fell from $24.36 to $8.00

**Resources:** Training code at github.com/microsoft/thinkingbox-training, benchmark at huggingface.co/datasets/microsoft/ThinkingBox-Bench, paper arXiv:2608.19741.
