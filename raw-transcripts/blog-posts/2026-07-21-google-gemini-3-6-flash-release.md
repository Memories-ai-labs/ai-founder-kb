# Introducing Gemini 3.6 Flash, 3.5 Flash-Lite, and 3.5 Flash Cyber
# URL: https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-3-6-flash-3-5-flash-lite-3-5-flash-cyber/
# Date: 2026-07-21
# Source: Google DeepMind / Google Blog
# Author: Tulsee Doshi, Senior Director of Product Management

## Overview
Google released three new Gemini models designed for production AI agents requiring enhanced efficiency, lower latency, and improved reliability.

## Gemini 3.6 Flash

**Key specs:**
- Reduces output token usage by 17% vs 3.5 Flash
- Up to 65% improvements on some benchmarks (DeepSWE)
- Pricing: $1.50/1M input tokens, $7.50/1M output tokens

**Benchmark improvements:**
- DeepSWE: 49% vs 37% (3.5 Flash)
- MLE Bench: 63.9% vs 49.7%
- OSWorld-Verified: 83.0% vs 78.4%

**Notable:** Enhanced coding, document parsing, chart analysis, and computer use. Ships with Frontier Safety safeguards for CBRN and cyber offense misuse prevention.

## Gemini 3.5 Flash-Lite

**Key specs:**
- Fastest model in 3.5 series: 350 output tokens/second
- Pricing: $0.30/1M input tokens, $2.50/1M output tokens
- Designed for high-throughput and low-latency tasks

**Benchmark performance:**
- Terminal-Bench 2.1: 54% vs 31% (3.1 Flash-Lite)
- GDM-MRCR v2: 72.2% vs 60.1%
- SWE-Bench Pro: 54.2% vs 49.6% (3 Flash)

**Use cases:** Agentic search, document processing, e-commerce data extraction, receipt translation.

## Gemini 3.5 Flash Cyber (CodeMender)

- Fine-tuned on 3.5 Flash for cybersecurity vulnerability detection and remediation
- Available exclusively to governments and trusted partners via limited-access pilot
- Reaches competitive frontier performance on CyberGym benchmark through multi-agent orchestration

## Availability

- 3.6 Flash & 3.5 Flash-Lite: Gemini API (Google AI Studio, Android Studio), Gemini Enterprise Agent Platform
- 3.5 Flash-Lite rolling out in Google Search

## Context

Google has begun pre-training for Gemini 4. Gemini 3.5 Pro is testing with partners and will be released soon. These three releases focus on the efficiency/cost tier, not the frontier capability tier.
