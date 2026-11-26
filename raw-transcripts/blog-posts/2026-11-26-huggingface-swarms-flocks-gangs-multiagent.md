# Swarms, Flocks, Gangs: How to build, train, and evaluate multi-agent systems
# URL: https://huggingface.co/blog/training-swarms
# Date: 2026-11-26
# source: Hugging Face Blog (Ben Burtenshaw, Kashif Rasul)

Authors: Ben Burtenshaw and Kashif Rasul (Hugging Face)

## Summary

Part 1 of a series on building, training, and evaluating small multi-agent systems, with reproducible examples on Hugging Face Jobs.

## Core Question

Does agent communication improve results, or does it just increase compute? Cites OpenAI's claim that a large agent swarm contributed to a Navier-Stokes result — but notes swarm size alone doesn't prove cooperation helped, since extra agents also means extra tokens. Anthropic's vulnerability-finding experiment also cited. Proposes comparing communicating vs independent agents at matched token budgets.

## Background

- Multi-agent reinforcement learning framing: changing teammates, credit assignment, and messages that shape what other agents observe
- Common approach: centralized training with decentralized execution (CTDE)

## Experiment

- 4 agents share one Qwen3-0.6B policy
- Task: pool private integers (1 to 99) into a sorted list; communicate through message and read tools
- Team reward: success minus penalty for generated tokens

## Results

- 75-update training run: success rose from ~6.6% to 82.3%
- Generated tokens per team fell ~37% over training
- Checkpoint 75: solved 26 of 32 held-out problems (81.25%)

## Technical Stack

- TRL training on Hugging Face Jobs
- Two H200 GPUs, ~5 hours, ~$50
- Steps: create bucket → run training → read results

## Next Steps

Future posts: evaluating and analyzing swarms, moving toward tasks a single agent can solve.
