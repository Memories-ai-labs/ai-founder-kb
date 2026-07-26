---
Title: The New Rules of Context Engineering for Claude 5 Generation Models
Publisher: Anthropic (claude.com/blog)
Author: Thariq Shihipar, Member of Technical Staff, Anthropic
Date: 2026-07-24
URL: https://claude.com/blog/the-new-rules-of-context-engineering-for-claude-5-generation-models
Categories: Claude Code, Agents
Source: Crawled 2026-07-26
---

# The New Rules of Context Engineering for Claude 5 Generation Models

## Overview

Anthropic removed over 80% of Claude Code's system prompt for advanced Claude 5 models without measurable performance loss. The article outlines evolving best practices for context engineering when building with Claude.

## Key Findings

**Unhobbling Claude**

The team discovered they were overconstraining the model through conflicting messages in system prompts, CLAUDE.md files, and skills. Newer Claude models can interpret user intent better and don't require as many explicit rules.

## Six Major Shifts in Best Practices

| Previous Approach | Current Approach |
|---|---|
| Give Claude rules | Let Claude use judgment |
| Provide tool usage examples | Design better interfaces |
| Include all context upfront | Use progressive disclosure |
| Repeat instructions | Simple tool descriptions |
| Manual memory in CLAUDE.md | Auto-memory systems |
| Simple markdown specs | Rich references (code/HTML/artifacts) |

## Context Assembly Best Practices

- **System Prompt:** Define product context and core behavior
- **CLAUDE.md:** Keep lightweight; emphasize gotchas over obvious details
- **Skills:** Encode team-specific knowledge; use progressive disclosure for long content
- **References:** Link to code-based specs, mockups, or detailed information

## New Tools

New `claude doctor` command automatically helps optimize context engineering by suggesting simplifications across prompts and skills.

## Recommendation

Simplify existing system prompts, skills, and CLAUDE.md files to match newer model capabilities rather than maintaining legacy constraints.
