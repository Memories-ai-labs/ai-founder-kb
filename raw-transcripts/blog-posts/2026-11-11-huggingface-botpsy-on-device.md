# BotPsy: On-Device Personal Assistant with a Sub-Billion-Parameter Agentic Language Model
# URL: https://huggingface.co/blog/qvac/botpsy
# Date: 2026-11-11
# Source: Hugging Face Blog (Tether AI Research / QVAC)

---

BotPsy is a 0.8B-parameter model from Tether AI Research (QVAC), built on Qwen3.5-0.8B. Designed for function calling and agentic workflows that can run on-device, keeping user data local. Best suited to "tasks of low to medium difficulty."

## Key Capabilities

**Tool use and agents:**
- Personal assistant for web search, travel, commerce, device control, files, calendar, messaging
- Designed for function calling in agentic loops

**Performance vs. base model (Qwen3.5-0.8B):**
- BFCL v4: 23.4 → 44.0
- τ-bench: 23.2 → 51.5
- ACEBench: 30.1 → 58.7
- BFCL v4 multi-turn: 7.5 → 46.1
- Leads all models at ≤1.2B parameters; beats Qwen3.5-2B-Think on 5/6 agentic benchmarks

**Reliability:**
- BFCL hallucination test (know when not to call tools): 86.1
- IFEval: 59.7 → 90.8
- IFBench: 22.0 → 55.9
- General knowledge: GPQA Diamond 33.2 → 38.1, MMLU-Pro 41.6 → 48.9

**Safety:**
- Automated red-teaming unsafe response rate: 36% (base) → 21% (BotPsy)

**Efficiency:**
- Substantially fewer reasoning tokens than base on several benchmarks
- Less looping behavior

## Training Method

1. Supervised fine-tuning on tool-use conversations
2. Multi-teacher on-policy distillation from three specialist 4B teachers (tool use, reasoning, instruction following)
3. Two RL rounds using rule-based and verifiable rewards

## Availability and Limitations

- Open weights planned under Apache 2.0 (research/education use)
- Formats: bf16, Q8, Q4, GGUF for llama.cpp and QVAC SDK
- Primarily English; weaker in Hindi and Russian
- Degrades as instructions accumulate in multi-turn settings
- Weak at multi-step information retrieval
- Not for safety-critical decisions or money/health/personal data applications

## Signal for AI Founders

Sub-1B agentic models reaching strong performance (~2x base on agentic benchmarks) through targeted fine-tuning + distillation + RL validates that on-device capable agents are becoming practical. The training recipe (SFT → distillation → RL) is a reproducible pattern for small-model agentic capability.
