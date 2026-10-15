# Preparing for the 2026 US midterms
# URL: https://www.anthropic.com/news/2026-us-midterms
# Date: 2026-10-14
# Source: Anthropic

Published: October 14, 2026
Category: Policy

## Summary

Anthropic outlines its approach to ensuring Claude is a trustworthy, politically neutral tool during the 2026 US midterm elections.

## Key Points

### Usage Patterns
- Analyzed ~250,000 US Claude.ai conversations from one week in September 2026
- ~5.75% touched on politics, policy, or social issues
- ~0.51% were about elections or voting
- ~0.01% asked whom to vote for
- ~0.002% violated election integrity policies

### Trusted Information Features
- Claude shows TurboVote banner for voter registration and polling questions
- Pulls official voting information from Democracy Works (state-specific)
- Shows official results on election night and after

### Political Even-handedness
- Opus, Sonnet, and Haiku 5.5 score 99% on political evenhandedness evaluation
- Three outside groups reviewed free-expression behavior
- Finding: Claude rarely refused requests but sometimes added unsolicited caveats; one group found uneven hedging in an earlier model
- Anthropic working on reducing unsolicited caveats and improving consistency

### Safeguards
- Usage Policy bars using Claude to deceive voters or disrupt elections
- Policy updated for 2026; published guide for campaigns on permitted/prohibited uses
- Partners ISD and McCain Institute tested defenses in the US, Israel, and Brazil
- Found: Claude reliably refused single harmful requests but could miss malicious campaigns split into harmless-looking pieces
- Response: new classifiers for multi-step misuse, better detection of foreign state actors, stronger cyber protections

### Observed Abuse
- Banned accounts running a fake news site producing midterm coverage favoring Russian, Iranian, and North Korean narratives
- Banned accounts seeking financial gain through fabricated election news

## Significance for AI Founders

Anthropic's mid-election transparency report is the most detailed public data released by a frontier lab on actual political AI use patterns. The 0.002% rate of election integrity violations, alongside the multi-step misuse detection gap, are important baseline signals for anyone building AI products in regulated or high-stakes social contexts.
