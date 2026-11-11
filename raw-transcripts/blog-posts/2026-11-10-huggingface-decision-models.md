# Decision Models in Hugging Face
# URL: https://huggingface.co/blog/decision
# Date: 2026-11-10
# Source: Hugging Face Blog

---

A decision model takes an input context (the "state"), evaluates a question with predefined answer options (the "primitives"), and returns a structured decision with probabilities. Instead of generating text token by token, it assigns probabilities to answers the application already understands.

Interface: **State + Questions + Allowed Answers → Decisions + Probabilities**

Previously called "System One models" (TypeSafe AI terminology).

## Three Question Primitives

- **Choice:** selects one of several options; softmax over per-option logits gives probability distribution
- **Score:** expected value of an ordered scale (e.g., low/medium/high mapped to 0/1/2)
- **Noul:** probability of a yes/no answer, modeled as a Bernoulli parameter

**Confidence:** normalized largest probability = (p_max − 1/K) / (1 − 1/K). Uniform distribution = 0, fully concentrated = 1.

## Advantages

**vs. LLM prompting:**
- Prompting an LLM for JSON can produce invalid/off-schema output
- Constrained decoding adds overhead
- Decision models avoid generating text altogether

**vs. classifiers:**
- Labels are supplied at inference time (not fixed at training)
- Unlike zero-shot classifiers, can take several typed questions about the same state

## Ecosystem

- Transformers provides `DecisionPipeline`, `AutoModelForDecision`, `DecisionConfig`
- `/v1/systemone` endpoint
- llama.cpp supports same API
- `decision-model` tag on Hugging Face Hub
- Training works with Trainer API; TRL support was an open PR at publication

## Signal for AI Founders

Decision models represent a shift from "generate text, then parse" to "emit structured probability distributions directly." For high-volume classification tasks (content moderation, routing, intent detection), this avoids JSON parsing failures and constrained decoding overhead. Worth watching as a potential paradigm for agentic decision-making components.
