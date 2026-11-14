# XYBench: Helping with the problem behind the question
# URL: https://huggingface.co/blog/allenai/xybench
# Date: 2026-11-13
# Source: Hugging Face Blog (Allen AI / Ai2)

Ai2 introduces XYBench, a benchmark of 8,000+ questions designed to test whether AI assistants recognize when a user's request rests on a misconception and redirect them toward their actual goal — not just the stated question. Questions are drawn from Stack Overflow, Stack Exchange, manually curated examples, and WikiHow-based generation, covering programming and everyday domains (cooking, home repair, etc.).

**Key findings:** Claude Sonnet 4.6, GPT-5, and Gemini 3.1 Pro often suggested fixes for the underlying goal but kept responses centered on the flawed approach; they steered users away from the misconception less often than human reference answers did.

**Significance for AI product builders:**
- Current frontier models optimize for answering the stated question, not identifying X (the stated goal) vs. Y (the real underlying goal).
- Building AI products that act like a skilled advisor — reframing the problem — requires deliberate fine-tuning or prompting work beyond base capabilities.
- XYBench provides a measurable proxy for "advisor quality" beyond raw accuracy.
