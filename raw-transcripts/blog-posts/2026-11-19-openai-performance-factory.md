# How OpenAI's Performance Factory keeps ChatGPT fast
# URL: https://openai.com/index/how-openai-performance-factory-keeps-chatgpt-fast/
# Date: 2026-11-19
# Source: openai-blog

## Summary

OpenAI's Performance Factory is a cloud-based system for finding and fixing performance regressions in ChatGPT, built on Codex and OpenAI's models. Engineers define recurring workflows; agents carry them out.

**Four components:**
1. **Task service:** Workflows defined in Markdown/config files with states, allowed transitions, and steps requiring human review
2. **Dispatch loop:** Assigns agents to tasks ready for next step
3. **Cloud Codex:** Runs agent work in internal environment with code and observability tools access
4. **Subscriptions:** Pause tasks while awaiting events (PR comments, deployments), wake agent when events fire

**First workflow — Regression Workflow:**
- Opens a task when a performance alert fires
- Agent 1: investigates cause
- Agent 2: adversarially challenges the diagnosis
- Agent 3: proposes a fix for engineer review
- Agent 4: checks recovery post-deployment

**Results:** 1,700+ investigations, 600+ root causes identified in 3 months. 70% accuracy in manual review of 100 root-cause suggestions.

**Key design principles:**
- Automate in stages (manual → reusable skills → cloud triggers → task factory)
- Adversarial review (separate "challenger" agent catches errors from anchoring on first explanation)
- Split work into focused turns (investigate / challenge / fix separately)
- Keep state outside the agent (tasks store findings; work can pause/resume)
- Protect engineer attention: group/rank related incidents by impact
- Fixes are harder than diagnoses: overcomplicated changes get adversarial review too
- Monitor the agents themselves: daily checks of agent logs
