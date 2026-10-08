# Introducing Claude Haiku 5.5
# URL: https://www.anthropic.com/claude-haiku-5-5
# Date: 2026-10-07
# Source: Anthropic News

Anthropic announces Claude Haiku 5.5 (model ID `claude-haiku-5-5`), its cheapest, fastest, and most capable small model yet.

## Use Cases
Built for high-volume, cost-sensitive work: summarization, compaction, database queries, and classification. Can serve as a subagent alongside Opus 5.5 and Sonnet 5.5 on coding tasks, and suits speed-sensitive work like live customer support and browser use.

## Pricing
Costs ~75% less to run on average than Haiku 4.5:
- Input: $0.10 per million tokens (≤100K context), vs Haiku 4.5's $1.00
- Output: $0.50 per million tokens, vs Haiku 4.5's $5.00

## Benchmark Performance (vs Haiku 4.5)
- OSWorld 2.1 (offline): 72.4% vs 15.7%
- Terminal-Bench 4.0: 39.2% vs 0.0%
- Humanity's Last Exam (no tools): 45.9% vs 10.2%

## Key Features
- First Haiku-class model with adjustable effort level (cost vs. intelligence tradeoff)
- Far fewer misaligned behaviors than Haiku 4.5
- Cybersecurity safeguards stricter than Haiku 4.5 but looser than Sonnet 5.5
- Biology safeguards match Sonnet 5, Sonnet 5.5, and Opus 5

## Early Customer Feedback
Companies including Asana, HubSpot, AlphaSense, Box, Rogo, and Cognition reported lower latency, higher accuracy, and better cost efficiency than Haiku 4.5.

## Availability
Available on AWS, Google Cloud, Microsoft Azure, and the Claude Platform.

## Related Updates
- Sonnet 5.5 cache-read price halved to $0.10/M tokens (cutting agentic task costs ~20%)
- Max and Team subscribers receive monthly API credits: $100 (Max 5x), $200 (Max 20x), up to $500 pooled (Team)
- Python and TypeScript SDKs add beta support for computer use and browser use
