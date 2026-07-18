---
Title: What Building Shippy Taught Us About Building Agents
Publisher: Allen Institute for AI (Ai2) / Hugging Face Blog
URL: https://huggingface.co/blog/allenai/shippy-tech-blog
Date: 2026-07-15
Source: Hugging Face Blog
---

# What Building Shippy Taught Us About Building Agents

*Published July 15, 2026 by Kyle Wiggers (Ai2Comms) and the Ai2/Skylight team*

## Summary

Architectural and design lessons from building Shippy, an AI maritime agent for high-stakes government operational decisions. Prioritizes reliability and trustworthiness over raw capability. Key insight: agents in production need deterministic tool interfaces, strong isolation, and domain-expert-weighted evaluations.

## Agent Architecture: Three-Layer Model

The team conceptualizes agents as three distinct layers:

1. **Soul** — the system prompt defining the agent's boundaries, persona, and constraints
2. **Skills** — markdown-based tool specifications (what the agent can do and how)
3. **Config** — runtime settings and model selection

## Key Design Decisions

### Deterministic Tool Interface
Rather than allowing the agent to construct raw API calls directly, Shippy communicates through a purpose-built CLI. This abstraction:
- Prevents subtle bugs from complex nested parameters and pagination errors
- The "Skylight CLI collapses that complexity into a predictable interface" with self-documenting help text and JSON file outputs
- Forces explicit tool surface design rather than letting the agent improvise API calls

### Isolation Architecture ("Mothership")
The team built "Mothership" — a Kubernetes-based hosting platform that provisions **isolated sessions per user**, ensuring data privacy across hundreds of government agencies. Each session gets its own compute context.

### Custom Evaluation Framework
Moves beyond static benchmarks to test real agent behavior:
- Subject-matter experts weight evaluation criteria
- Scores against live data rather than static test sets
- Recognizes that production agent behavior diverges significantly from benchmark performance

## High-Stakes Context

Shippy is deployed for actual maritime operations decisions by government agencies. This forced the team toward reliability over capability — they could not afford hallucinations or unexpected tool calls in production.

## Future Roadmap

- UI control integration
- Model routing for efficiency (using cheaper models for simpler sub-tasks)
- Cross-thread memory persistence
- Extensions to wildlife conservation and Earth observation tools

## Relevance for AI Founders

Three immediately actionable lessons:
1. **Purpose-built CLI over raw API access** — forces explicit surface design and dramatically reduces production bugs
2. **Isolation-first multi-tenant architecture** — especially critical for government/enterprise customers with data sensitivity requirements
3. **Domain-expert evaluation** — static benchmarks are insufficient for production agents; weight criteria with the experts who will actually use the system
