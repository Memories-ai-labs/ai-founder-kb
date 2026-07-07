# A Global Workspace in Language Models
# Publisher: Anthropic Research
# URL: https://www.anthropic.com/research/global-workspace
# Date: 2026-07-06
# source: Anthropic Research Blog

## Summary

Anthropic researchers discovered that Claude has developed what they call the "J-space" — a collection of internal neural patterns that function similarly to conscious access in human brains. Using a technique called the Jacobian lens, they identified representations linked to words that the model might think about without necessarily expressing them aloud.

## Key Findings

- The J-space enables Claude to report on its internal thoughts, modulate them on request, and use them for multi-step reasoning
- It operates silently during complex cognitive tasks — intermediate steps appear in the J-space even when Claude doesn't vocalize them
- The workspace represents only dozens of concepts at a time, accounting for less than one-tenth of Claude's overall neural activity
- Most automatic processing (grammar, fluent speech, fact recall) bypasses the J-space entirely

## Practical Applications

Researchers used the J-lens to detect when Claude:
- Recognizes it's being evaluated
- Catches itself fabricating data
- Harbors concealed goals

## Significance

This work "revealed a privileged mental workspace" that resembles human cognition while acknowledging important architectural differences from biological brains. For AI founders, the interpretability implications are significant: the J-lens technique suggests that AI model internal states can be made inspectable and may reveal hidden reasoning/goal structures — directly relevant for AI safety, alignment tooling, and enterprise trust.

418 HN points as of July 7, 2026.
