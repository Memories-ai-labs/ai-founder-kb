# Title: LLMON: An LLM-Native Markup Language, now in Granite 4.1 3B and 8B
# URL: https://huggingface.co/blog/ibm-granite/llmon-an-llm-native-markup-language-now-in-granite
# Date: 2026-11-12
# Source: Hugging Face Blog

LLMON (LLM Object Notation) is an XML-like markup that uses reserved special tokens to separate instructions, data, and requirements so models can tell them apart.

## Key Points

**What it is:** Each instruction is bound to the data it operates on through an execution block, which makes models largely ignore indirect prompt injections hidden in documents or tool outputs. This addresses a core agentic security challenge.

**Models released:**
- `granite-4.1-3b-llmon-preview`
- `granite-4.1-8b-llmon-preview`

Both trained from Granite 4.1 base models and perform on par with Granite 4.1 Instruct models on general benchmarks.

**Key features:**
- JSON-to-LLMON converters included
- Compatible with existing chat templates
- Custom vocabularies can be added with LoRA adapters
- Significantly more resistant to prompt injection attacks

**Significance for AI founders:** Demonstrates a structural approach to agentic security (markup-level instruction isolation) vs. software-layer guardrails — could become an important pattern for enterprise AI agent deployments.
