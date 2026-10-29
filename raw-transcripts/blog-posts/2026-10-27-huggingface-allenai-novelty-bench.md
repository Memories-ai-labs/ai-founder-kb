# Can we trust LLMs to judge whether a research idea is novel?
# URL: https://huggingface.co/blog/allenai/novelty-bench
# Date: 2026-10-27
# Source: Hugging Face Blog

Ai2 (Allen Institute for AI) study: "Old Ideas, Novel Problems" — finds that LLM novelty judges are unreliable, especially when evaluating AI-generated ideas.

**Key findings:**

- **Prompt wording matters most.** For GPT-5.4 on pairs of human and AI-generated ideas, accuracy fell from 93.5% to 40.9% when the prompt was simplified. Best prompt also varies by model.
- **Human-only tests look more stable.** Same prompt change shifted accuracy ~7 points on human-authored ideas (though one model still moved 21 points).
- **More search and reasoning don't reliably help.** An agentic judge with live arXiv search scored 0.78 macro-F1, below a simple prompted Claude Opus 4.6 baseline at 0.89 and at ~1/10th the cost.
- **Purpose-built evaluators underperform:**
  - Simple Opus 4.6 prompt + majority voting: 0.854 macro-F1 at $2.59
  - Idea Novelty Checker: 0.642 at $30.66
  - Sakana AI's AI Scientist evaluator: 0.772 at $82.05
- **Comparisons between idea generators are fragile.** Across prompt changes, ~25-33% of verdicts flipped when judging ideas from two AI generators.

**Benchmark:** Built from ICLR 2026 peer reviews, using reviewer comments on originality rather than acceptance decisions.

Ai2 says the work is a starting point and the problem remains open.
