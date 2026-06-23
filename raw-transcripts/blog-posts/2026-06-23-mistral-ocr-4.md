Title: Introducing Mistral OCR 4
Publisher: Mistral AI
URL: https://mistral.ai/news/ocr-4/
Date: 2026-06-23
Source: Mistral AI News

---

# Introducing Mistral OCR 4: State-of-the-Art Document Intelligence

Mistral AI has released OCR 4, described as a breakthrough in optical character recognition and document intelligence. The model introduces several key advancements beyond traditional text extraction.

## Core Features

The new system delivers structured document understanding through multiple dimensions:
- **Bounding boxes** that localize text content
- **Typed block classification** identifying elements like titles and tables
- **Inline confidence scoring** for each extracted segment
- Support across **170 languages** spanning 10 language groups, with particular strength in rare and low-resource languages

## Performance Highlights

- Independent human evaluators preferred OCR 4 over competing systems in the majority of test cases, with an average preference rate of 72%
- Top score of **85.20 on OlmOCRBench** public evaluation
- **93.07 on OmniDocBench**

The developers acknowledge significant limitations in automated benchmarks, noting that scoring artifacts often penalize correct outputs. As they explain, "ground-truth errors" and notation differences frequently cause mismatches unrelated to actual model performance.

## Deployment Options

- **Mistral API:** $4 per 1,000 pages
- **Batch API:** $2 per 1,000 pages
- **Document AI in Studio:** $5 per 1,000 pages
- **Self-hosted enterprise deployments** for data-sensitive environments

## Use Cases

Primary applications include:
- RAG systems requiring citation-ready content
- Agentic workflows for invoice processing
- Enterprise search implementations

The technology integrates with Mistral's newly announced Search Toolkit framework.
