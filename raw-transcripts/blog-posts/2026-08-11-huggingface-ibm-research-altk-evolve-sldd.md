# Thinking of ACE? We Can Do It with Fewer Tokens
# URL: https://huggingface.co/blog/ibm-research/altk-evolve-sldd
# Date: 2026-08-11
# source: Hugging Face Blog
# Authors: Vatche Isahagian, Jayaram Radhakrishnan, Vinod Muthusamy, Gaodan Fang, Punleuk Oum, G Thomas, Ashwath Vaithinathan Aravindan, Evelyn Duesterwald, Merve Unuvar (IBM Research)

## Summary

IBM Research compares ACE (Agentic Context Engineering) and ALTK-Evolve — both agentic memory systems that help LLM agents learn from task histories without weight updates. ALTK-Evolve delivers equal or better accuracy at 7–40% of ACE's token cost by calibrating context delivery to model capacity.

## Core Finding

Both systems preserve rich, itemized learning records. Divergence: ACE injects its complete playbook at every inference step; ALTK-Evolve delivers only as much context as the model can effectively use.

## Benchmark Results (AppWorld)

- **DeepSeek-V3.2:** ALTK-Evolve 89.3% vs ACE 80.4% Task Goal Completion at ~40% of token cost
- **gpt-oss-120b:** ALTK-Evolve matched ACE accuracy at ~1/7 the tokens

## Key Insight

Calibrating context delivery based on model capacity outperforms uniform comprehensive prompting. "However much of the guideline set a given model can actually use" — not the full playbook every time.

## Relevance

For startups deploying agentic systems at scale, token efficiency directly maps to inference cost. This technique enables sophisticated agent memory with dramatically lower operating costs, especially on weaker/cheaper models.
