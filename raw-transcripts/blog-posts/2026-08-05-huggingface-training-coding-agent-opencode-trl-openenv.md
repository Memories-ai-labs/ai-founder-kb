# Training a Coding Agent Using the OpenCode Harness in Remote HF Sandboxes with TRL and OpenEnv
# URL: https://huggingface.co/blog/sergiopaniego/trl-openenv-harness-training
# Date: 2026-08-05
# Source: Hugging Face Blog

## Overview

A novel approach to training coding agents by allowing the agent harness to maintain control of its own execution loop while TRL captures and learns from the exact tokens produced.

## Key Concepts

**Loop-Owning Architecture**

Rather than having the trainer drive the agent's decision loop, the system inverts this relationship: "The agent runs to completion on its own, and TRL trains on the exact tokens the harness produced." This approach trains the actual deployed harness rather than a simulation of it.

**Four Core Components**

- An isolated OpenEnv sandbox container running the harness
- A transparent proxy capturing token IDs and log probabilities
- A reward verifier inspecting workspace outputs against hidden test cases
- An AsyncGRPO trainer reconstructing samples from captured turns

## Remote Sandbox Execution

Each rollout executes within its own remote Hugging Face sandbox, enabling horizontal scaling. The implementation uses `HFSandboxBackend` with pre-baked Docker images containing the harness and proxy, eliminating per-rollout installation overhead.

**Critical Detail: Dual vLLM URLs**

The trainer and vLLM operate locally over NCCL, requiring an internal localhost URL. Remote sandboxes need a separate, externally-accessible endpoint ("sandbox-vllm-url") to reach the same model server.

## Deployment on Hugging Face Jobs

A launcher script coordinates three concurrent processes: vLLM serving, tunnel exposure, and trainer execution via a single command, keeping infrastructure costs manageable by running rollouts on inexpensive cpu-basic instances.

## Results

Testing with Qwen3-8B over 10 steps across 32 problems showed reward improvement from approximately 0.27 to 0.71, demonstrating that the training pipeline successfully learns from agent-produced tokens.

## Operational Considerations

Remote sandboxes require careful management regarding startup delays, mid-execution failures, and resource cleanup. Exposing vLLM via public tunnels works for demonstrations but requires proper access controls for production use.
