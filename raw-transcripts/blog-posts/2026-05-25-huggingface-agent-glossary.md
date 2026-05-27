# Harness, Scaffold, and the AI Agent Terms Worth Getting Right
# URL: https://huggingface.co/blog/agent-glossary
# Date: 2026-05-25
# source: Hugging Face Blog

Authors: Sergio Paniego, Aritra Roy Gosthipaty

## Introduction

When a field evolves quickly, its vocabulary often evolves faster than its shared understanding. Terms start to blur, get reused in different contexts, or become shorthand for ideas that are never fully explained. This is happening in AI Agents, where concepts are getting mixed together, some renamed, and others widely used before quietly disappearing.

This glossary grounds the terms that keep coming up without clear, consistent explanations — focusing on concepts often mixed up or reused differently.

## Key Definitions

### Model
The LLM: takes text in and produces text out (Claude, Qwen, GPT, Kimi, DeepSeek, etc.). On its own: no memory between calls, no loop. Can express intent to call a tool but needs a harness to execute it. Wrap it in scaffolding and a harness and it becomes an agent.

### Scaffolding
The behavior-defining layer around the model:
- System prompt
- Tool descriptions
- How the model's responses get parsed
- What it remembers across steps (context management)

Shapes how the model sees the world and acts in it, whether during training or at inference.

### Harness
The execution layer inside the agent:
- Calls the model
- Handles its tool calls
- Decides when to stop

The harness is what makes the agent run. Scaffolding is what the model works from.

**Harness Engineering:** Designing this layer well — when to stop, how errors get handled, what guardrails exist. Applies at both training and inference.

**Eval Harness:** At evaluation time, runs a fixed set of scenarios at a model checkpoint and records metrics rather than updating weights.

**Orchestrator:** A higher-level controller that coordinates work across multiple agents (manages agents as units, unlike a harness which drives a model).

### Agent
Agent = Model + Harness

Takes in information, decides what to do, acts in a loop. Turns raw text generation into something that can act.

> Two products using the same underlying model can feel completely different because their harnesses make different choices.

### Context Engineering
Designing what goes into the agent's context window:
- System prompt, tool descriptions, conversation history, retrieved knowledge

**Short-term Memory:** What stays in context during a single run.
**Long-term Memory:** Persists across sessions, stored externally, retrieved and injected back when relevant.

### Policy
The behavior an agent follows. In LLM systems, part is learned in model weights, but also depends on scaffolding and harness. A policy is NOT an agent — the policy defines behavior; the agent is the full system that acts.

### Tool Use
How agents reach outside themselves (APIs, code interpreters, databases, web search, file systems). Model expresses intent to use a tool in structured format; harness routes it to the right function; result fed back into context.

### Skills
Reusable, structured packages of knowledge that enable multi-step tasks. Unlike a tool (an action), a skill bundles everything to accomplish a goal. Portable across agents, loaded on demand.

### Sub-agents
An agent called by another agent to handle a specific subtask. Has its own model and scaffold, reasons independently, returns a result. Can itself use tools and call further sub-agents.

## Training-Specific Terms

### RL Environment
Stateful object: takes action as input, updates internal state, returns observation.

### Trainer
What makes the agent better: runs many agent episodes, scores results, uses scores to update model weights. Example: TRL's GRPOTrainer.

### Rollout
One full agent run from start to finish — what the agent saw, what it did, what reward it got. Also called trajectory or trace. Raw data RL algorithms learn from.

### Reward
**Types:**
- Verifiable: tests pass/fail, answer matches
- Learned: human preferences, LLM-as-judge
- Sparse: one score at end of episode
- Dense: a score at each step

**Rubrics:** Break reward into explicit dimensions with weights rather than a single number.
