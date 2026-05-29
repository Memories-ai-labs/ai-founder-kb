# Introducing Claude Opus 4.8
# URL: https://www.anthropic.com/news/claude-opus-4-8
# Date: 2026-05-28
# source: Anthropic News

Anthropic has released Claude Opus 4.8, an upgraded version of its predecessor Opus 4.7. The new model delivers improvements across multiple benchmarks while maintaining the same pricing structure. It launches alongside several new platform features and capabilities.

## Core Capabilities

Opus 4.8 demonstrates performance gains in coding, agentic skills, reasoning, and knowledge work tasks. The model shows measurable improvements compared to Opus 4.7 and competitive models on standardized evaluations. A comprehensive capability assessment is available in the Claude Opus 4.8 System Card.

## Key Improvements: Honesty and Judgment

A significant advancement in Opus 4.8 involves its reliability in self-assessment. The model demonstrates stronger "honesty" by flagging uncertainties about its work and avoiding unsupported claims. According to the documentation, Opus 4.8 is "around four times less likely than its predecessor" to let code flaws pass without comment.

Early testers report the model demonstrates superior judgment in collaborative work, asking clarifying questions, catching mistakes, and questioning unsound plans before implementation.

## Safety and Alignment

Anthropic's Alignment team assessed the model before release. The evaluation found Opus 4.8 reaches "new highs on measures of prosocial traits" and shows substantially lower rates of misaligned behavior compared to Opus 4.7, with performance similar to Claude Mythos Preview.

## New Features

**Dynamic Workflows**: Claude Code now supports hundreds of parallel subagents within a single session, enabling large-scale tasks like codebase migrations across hundreds of thousands of lines of code.

**Effort Control**: Users can now select how much computational effort Claude applies to responses, with higher settings producing better results at higher token costs.

**Messages API Enhancement**: Developers can update system instructions mid-task without disrupting prompt caching.

## Pricing and Availability

Claude Opus 4.8 maintains Opus 4.7 pricing: $5 per million input tokens and $25 per million output tokens. Fast mode costs $10 and $50 respectively. The model is available immediately via claude.ai and the Claude API using the identifier `claude-opus-4-8`.

## Future Roadmap

Anthropic indicates development of lower-cost models with comparable capabilities to Opus, plus a forthcoming higher-intelligence class called Mythos. The company is currently deploying Mythos Preview with select organizations for cybersecurity applications while developing required safeguards for broader release.
