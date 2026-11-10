# Introducing AlphaProof Code: a breakthrough in verifying complex software at depth
# URL: https://deepmind.google/blog/introducing-alphaproof-code/
# Date: 2026-11-10
# Source: Google DeepMind

Authors: Pushmeet Kohli and Swarat Chaudhuri

## Summary

Google DeepMind used AI agents to formally verify Signal's cryptographic protocol implementation, the system protecting private messages in Signal and Google Messages. AlphaProof Code is a multi-LLM agentic framework pairing human experts with AI agents for formal verification.

## Key Details

- **Architecture:** Multi-LLM agentic system; humans decide what needs to be proven, AI agents carry out proofs.
- **Scale:** Agents powered by Gemini Carbon produced over 6 million lines of Lean (formal proof language).
- **Speed:** Verification took ~4 weeks (vs. years for expert teams).
- **Coverage:** Proofs cover compiled code running on devices — not just protocol design — closing the gap where real-world vulnerabilities often hide.
- **Auditing:** ~1% of codebase flagged for human review; Lean auto-checked the rest.
- **Bug detection:** Reintroduced two previously fixed bugs into isolated Signal code — system proved the buggy versions were insecure.
- **Open source:** Verification artifacts open-sourced.
- **Future scope:** Positioned for medical device firmware, power grid software.

## Significance for AI Founders

Landmark demonstration of agentic AI applied to critical infrastructure security. 6M lines of machine-verified Lean code in 4 weeks shows the scale unlock from AI-human collaboration in formal methods. Signals that formal verification — previously a niche academic tool — could become standard practice for high-stakes software.
