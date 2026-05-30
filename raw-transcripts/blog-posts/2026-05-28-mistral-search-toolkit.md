# Introducing Search Toolkit
# URL: https://mistral.ai/news/search-toolkit
# Date: 2026-05-28
# source: Mistral AI News

Mistral has released Search Toolkit in public preview, a composable framework designed to simplify building production search pipelines for AI applications. The toolkit addresses a longstanding challenge: teams typically invest excessive engineering effort assembling separate tools for ingestion, retrieval, and evaluation, each with distinct interfaces and data assumptions.

Search Toolkit consolidates these three components into a unified framework with consistent interfaces, enabling teams to prioritize improving search quality over maintaining integrations. The open-source solution runs across cloud, on-premises, and edge infrastructure.

## The Problem

Development teams report spending weeks on integration work before querying their own data. Search infrastructure presents particular challenges for enterprises managing multiple information sources—internal wikis, support tickets, document repositories, and codebases—each requiring different processing and indexing strategies.

## Key Use Cases

**Enterprise Search:** Organizations face numerous distinct search problems across different data sources. Search Toolkit provides consistent processing patterns across source types within a single framework, eliminating the need to rebuild pipelines for each new data source.

**RAG and Retrieval Quality:** Teams typically struggle isolating whether poor retrieval-augmented generation results stem from retrieval or generation failures. Search Toolkit includes built-in evaluation metrics—recall, precision, MRR, and NDCG—enabling comparison of retriever configurations independently.

**Domain-Specific Retrieval:** Specialized domains like legal, medical, and financial documents often underperform with general-purpose retrievers. The toolkit supports customization for domain-specific terminology and relevance criteria.

## Architecture Components

The toolkit includes three primary modules:

- **Ingestion:** Configurable pipelines handling document parsing, chunking, and embedding generation with custom adapter support
- **Retrieval:** BM25 sparse retrieval, dense embedding-based retrieval, and hybrid configurations
- **Evaluation:** Performance measurement against custom test sets with side-by-side configuration comparisons

## Agentic Applications

In an AI agent context, Search Toolkit provides indexed search capabilities alongside live data retrieval through Connectors, enabling agents to access both historical indexed content and current system state.

## Getting Started

Mistral provides a starter app template requiring Docker and the uv package manager. The template includes pre-configured Vespa indexing, hybrid retrieval capabilities, and sample data for immediate experimentation.

For comprehensive details, users can access the full documentation covering ingestion pipeline tuning, Vespa schema optimization, and advanced retrieval features like LLM query rewriting and reranking.
