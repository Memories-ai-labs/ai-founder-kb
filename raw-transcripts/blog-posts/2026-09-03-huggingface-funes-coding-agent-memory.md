# Give Your Coding Agents a Memory You Own
# URL: https://huggingface.co/blog/funes
# Date: 2026-09-03
# Source: Hugging Face Blog
# Author: David Corvoysier (dacorvo)

## Overview

Introduces **funes**, a durable memory layer for coding agents that transforms session logs into searchable, retrievable knowledge. The fundamental problem: developers working across multiple machines with different coding agents experience repeated context loss as each agent "starts from zero" in new sessions.

## Core Concepts

**The Memory Problem:**
Previous work established that agent traces are valuable records, yet they remain archived and unusable during active work. As the author notes, "you cannot `grep` your way to _'why did we move off the streaming parser?'_ across ten thousand turns."

**The Solution:**
Funes indexes agent sessions with "embedding, reranking happen _on your machine_" by default, requiring no external service. Installation involves a single command, then adding the tool to any supported agent (Claude Code, Codex, pi, Hermes).

## Key Features

**Local-First Architecture:** Memory indexing occurs locally using Lance datasets without ML runtime dependencies. Users can bind memories to Hugging Face datasets when sharing is desired, keeping them private by default.

**Cross-Agent Continuity:** Multiple agents accessing shared memory can recall earlier reasoning. A developer starting a task in Claude Code can continue it in Codex while maintaining complete context.

**Cost Efficiency:** Benchmarking showed recall-based context management costs approximately "8x cheaper than a written handoff on one...4x on the other."

**Security:** Credentials undergo redaction before indexing and remote publication, with transparent documentation of scanning capabilities.

## Practical Workflow

The `recall` tool lets agents independently access relevant past sessions with source attribution. The `ask` command enables one-time queries without permanent agent integration, supporting public memory exploration.
