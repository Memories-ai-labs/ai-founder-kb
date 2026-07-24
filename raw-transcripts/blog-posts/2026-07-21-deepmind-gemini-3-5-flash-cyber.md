# Introducing Gemini 3.5 Flash Cyber
# URL: https://deepmind.google/blog/introducing-gemini-3-5-flash-cyber/
# Date: 2026-07-21
# Source: Google DeepMind Blog

Authors: Raluca Ada Popa and Four Flynn

---

Google DeepMind released Gemini 3.5 Flash Cyber, a specialized lightweight model designed to identify and patch software vulnerabilities. Built on the 3.5 Flash foundation, this cybersecurity-focused model offers a more cost-effective alternative to larger models while maintaining competitive performance.

## Core Problem

The model addresses a critical challenge in security: exploring the vast search space of potential code paths. By enabling multiple invocations rather than relying on single expensive calls, the model can analyze significantly more code paths to discover and validate vulnerabilities.

## Key Capabilities

- Achieved competitive results on CyberGym, a benchmark evaluating real-world vulnerabilities
- Significantly outperformed mainline Flash and competitor models on Google's Big Sleep evaluation
- Discovered more unique vulnerabilities when tested on Chrome's V8 JavaScript Engine
- In real-world testing, uncovered remote code execution vulnerabilities in Google's systems within just 2 hours

## Deployment Approach

Currently available through a limited-access pilot program exclusively to governments and trusted partners via CodeMender. Plans to expand access over time. This cautious deployment approach aims to help defenders identify vulnerabilities before exploitation while minimizing misuse potential.

## Strategic Significance

Gemini 3.5 Flash Cyber was released alongside Gemini 3.6 Flash and 3.5 Flash-Lite as part of a broader efficiency-focused model release. The cybersecurity-specialized variant signals Google's move into vertically specialized AI models for high-stakes domains (cf. Claude Science for life sciences, Robostral Navigate for robotics).
