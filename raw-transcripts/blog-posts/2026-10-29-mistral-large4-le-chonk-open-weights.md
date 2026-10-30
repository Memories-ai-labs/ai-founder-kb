# Mistral Large 4 (Le Chonk) is now open weight
# URL: https://mistral.ai/news/mistral-large-4-oss/
# Date: 2026-10-29
# Source: Mistral AI

## Summary

Mistral releases open weights for Mistral Large 4 ("Le Chonk"), a 1-trillion-parameter natively multimodal hybrid instruct-and-reasoning mixture-of-experts model. Approx 52B active parameters (Mistral-Large-4-1T-A52B). Trained from scratch on European infrastructure.

## Key Technical Details

- **Architecture:** Hybrid instruct-and-reasoning MoE, ~1T total / ~52B active parameters
- **Multimodal:** Natively multimodal
- **Context:** Not specified in post (preview had 1M)
- **Reasoning modes:** Low (simple tasks), Medium (everyday tasks), High (default, hardest tasks)
- **Training:** European infrastructure, full technical report "coming soon"

## Benchmark Performance

- **FrontierCode 2.0:** 19.7% (leads open-weight models)
- **Terminal-Bench 4.0:** 41% (+13 points from preview)
- **Artificial Analysis Coding Agent Index:** 48% (roughly tied with GLM-5.3, using 47% fewer tokens/task)
- **Artificial Analysis Cyber Index:** 51%
- **Cyber safety:** 96.6% average refusal rate on malicious cyber requests; 97.1% attack resistance on B3 Agent Security Benchmark
- **FinWorkBench (Finch):** 73.3%
- **BrowseComp:** 84.5%

## Pricing (API)

- Input: $0.70/M tokens
- Cached input: $0.07/M tokens
- Output: $2.10/M tokens

## License

Modified MIT license: "Mistral Ecosystem Open-Weight license." Businesses offering it as Model-as-a-Service must obtain a separate commercial license.

## Availability

Mistral Studio, Mistral API, OpenRouter, Hugging Face (vLLM/SGLang), NVIDIA-hosted endpoints and NIM containers, Microsoft Foundry.

Cybersecurity variant in preview for vetted enterprise partners (e.g., Orange Cyberdefense). Note: one partner observed potential for uplift in real attacks; Mistral updating guardrails.
