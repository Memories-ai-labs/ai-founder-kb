---
Title: Introducing Agentic Search
Publisher: Mistral AI
URL: https://mistral.ai/news/agentic-search/
Date: 2026-08-20
Source: Mistral AI News
---

# Introducing Agentic Search | Mistral AI

**Date:** August 20, 2026

## Overview

Mistral has unveiled Agentic Search, a retrieval system that enhances AI search capabilities through iterative navigation rather than one-shot retrieval. The technology enables models to "search and navigate their organization's most complex data and documents" through multiple steps.

## Key Performance Improvements

The system demonstrates substantial gains on industry benchmarks:

- **FinanceBench:** Accuracy improved to 86% on financial filings, representing "a ~3x improvement" when adding the search loop
- **OfficeQA Pro:** Accuracy reached 51.9% for complex table-heavy documents, showing a "+45.6 point gain"
- **Efficiency:** Token usage reduced by up to one-third, with latency dropping from 255 seconds to 154 seconds (p90)

## How It Works

Agentic Search provides five operational tools: `search`, `open`, `navigate`, `read`, and `grep`. These function similarly to file-system operations, allowing models to iteratively inspect documents, refine searches, and verify answers rather than relying solely on initial retrieval results.

## Use Cases

The technology suits scenarios involving:
- Long documents
- Multi-source research
- Verifiable answers
- Structured data like financial statements and government records
