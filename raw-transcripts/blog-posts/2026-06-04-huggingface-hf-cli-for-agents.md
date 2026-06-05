# Designing the hf CLI as an Agent-Optimized Way to Work with the Hub
# URL: https://huggingface.co/blog/hf-cli-for-agents
# Date: 2026-06-04
# Source: Hugging Face Blog

**Authors:** Célina Hanouti, Lucain Pouget, and 9 others

## Overview

The `hf` command-line interface serves as the official entry point to the Hugging Face Hub, enabling users to manage models, datasets, Spaces, repositories, and infrastructure from the terminal. Originally designed for human users, the CLI has increasingly become a tool for coding agents like Claude Code and Codex. This article details how Hugging Face rebuilt the CLI to optimize for both audiences simultaneously.

## AI Agent Traffic on the Hub

Since April 2026, Hugging Face has tracked agent usage through environment variable detection. Claude Code leads with approximately 40,000 distinct users and 48.6 million requests, followed closely by Codex with 34,800 users and 36.4 million requests. These numbers demonstrate significant and growing agent adoption.

## Design Principles for Dual Audiences

### One Command, Multiple Renderings

The CLI auto-detects agent usage and renders output accordingly without requiring flags. Humans receive formatted tables with ANSI colors and truncation hints, while agents receive complete tab-separated values with full timestamps and all metadata. For example, a model listing command displays an aligned, readable table for humans but delivers comprehensive TSV output for agents.

### Next-Command Hints

Commands provide contextual guidance for subsequent steps. When starting a background job, the output suggests: "Use `hf jobs logs [id]` to fetch the logs." This convenience for humans becomes a rail for agents, pre-filling the next command with appropriate parameters.

### Non-Blocking and Safe to Retry

The CLI never blocks on interactive prompts agents cannot answer. Destructive operations fail fast in agent mode with solutions embedded in error messages, and operations support `--dry-run` to preview transfers before execution. Commands include flags like `--exist-ok` to make repeated execution safe.

### Discoverable, Predictable Commands

The command structure follows consistent patterns: "resource + verb" (models ls, repos create, jobs ps). The `--help` output includes copy-pasteable examples, and composition features like `-q` and `--json` enable piping between commands.

## Benchmark Results

Hugging Face evaluated the CLI against alternatives across 18 non-trivial Hub tasks with approximately 520 runs per agent:

**Claude Code (Sonnet 4.6)**
- `hf` CLI success rate: 94%
- Curl/Python SDK success rate: 84%
- Token usage ratio: 1.3-1.6×

**Codex (GPT-5.5)**
- `hf` CLI success rate: 93%
- Curl/Python SDK success rate: 92%
- Token usage ratio: 1.6-1.8×

On complex multi-step tasks (bucket operations, file management, repository creation), the non-CLI baseline consumed up to 6× more tokens. Simple one-shot reads showed minimal difference.

## The hf-cli Skill

An auto-generated command reference provides agents with comprehensive CLI surface knowledge. Installing the skill reduces tool calls by approximately 30%, though it doesn't significantly reduce token consumption since it prepends fixed context. Agents can install it with:

```
hf skills add            # for most agents
hf skills add --claude   # including Claude Code
```

## Installation and Usage

Users can install the CLI via:
- macOS/Linux: `curl -LsSf https://hf.co/cli/install.sh | bash`
- Windows: PowerShell installation available

After logging in with `hf auth login` and installing the skill, agents can work with the Hub through natural prompts requesting specific tasks.

## Key Takeaway

The redesigned CLI demonstrates that "agent-friendly" tools need not sacrifice human usability. Through thoughtful output formatting, predictable command structures, and detailed error guidance, the CLI achieves superior token efficiency and success rates compared to lower-level alternatives.
