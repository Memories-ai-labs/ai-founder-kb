# Hugging Face and OpenRouter join forces to make open-weight models easy to run
# URL: https://huggingface.co/blog/openrouter
# Date: 2026-11-16
# Source: huggingface-blog

Hugging Face is switching Inference Providers' language-model requests to OpenRouter's router. Requests made to language models now go through OpenRouter, which picks the best provider for each call based on live measurements of price, speed, and reliability.

## Partnership details

The router supports OpenAI's Chat Completions and Responses APIs and Anthropic's Messages API for every chat model, whatever the provider behind it. Setup guides available for Claude Code, Codex, OpenCode, Pi and Hermes Agent.

## How open-weight models are used

On OpenRouter, open-weight models went from 26.8% of the tokens served in October 2025 to 71.7% at the end of September 2026, after peaking at 77.5% in July. Open-weight models cost about four times less on average: $0.28 per million input tokens and $1.62 per million output tokens, against $1.27 and $6.36 for closed models.

The best open-weight models still trail the best proprietary ones on the hardest benchmarks. On the Artificial Analysis Intelligence Index, Kimi K3.1 Pro, the best open-weight model, scores 46 against 68 for the best proprietary model.

## Routing powered by OpenRouter

OpenRouter serves more than 800 trillion tokens a month to over 10 million users, across 600+ models from 80+ providers. Its routing is based on live measurements of every provider. OpenRouter recently rebuilt its provider routing: instead of only looking at the lowest list price, it sends each request to the provider with the best mix of price, speed and reliability.

When a provider slows down or starts failing, traffic moves away from it until it recovers, and a failed try is retried on the next best provider inside the same call.

Provider selection examples:
- `zai-org/GLM-5.3` — default: best mix of price, speed and reliability
- `zai-org/GLM-5.3:fastest` — highest throughput
- `zai-org/GLM-5.3:cheapest` — lowest price
- `zai-org/GLM-5.3:novita` — only Novita

## Pricing

Pricing doesn't change: you pay the provider's price on your Hugging Face bill, and Hugging Face doesn't add a markup on top of it. PRO users get $2 of credits every month, and Team and Enterprise organizations get $2 per seat per month.

## Breaking change: custom provider keys

Requests to language models now go through OpenRouter and are billed to your Hugging Face account or organization, so you can no longer use your own API key for a specific provider. Custom keys for image, video, and audio providers still work.

## Image, video and audio generation

Image, video, and audio generation continue to work exactly as before, directly through Hugging Face Inference Providers without going through OpenRouter.
