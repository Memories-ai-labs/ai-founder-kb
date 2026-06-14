# Introducing Serge: GitHub-Native AI Code Review

**Source**: HuggingFace Blog
**Date**: 2026-06-12
**URL**: https://huggingface.co/blog/huggingface/serge
**Author**: Tarek Ziadé
**License**: Apache-2.0

---

## Full Article

Serge represents a GitHub-integrated approach to AI-powered code review that operates within existing development workflows. Rather than replacing human judgment, this tool aims to assist maintainers by catching issues early and reducing review bottlenecks.

### Core Philosophy

The project addresses a practical challenge: "The hard part for AI code review is not producing text about code. The hard part is fitting into that workflow without creating another place to check." Users summon Serge by commenting "@askserge please review" on pull requests, triggering an analysis process that respects repository-specific guidelines.

### Three Deployment Options

**GitHub Action:** The quickest setup path requires only an API key as a repository secret plus the workflow installation.

**GitHub App:** Functions as a hosted service receiving comment events, addressing permission challenges with forked pull requests where secrets remain inaccessible.

**Staged Web App:** Enables human reviewers to examine, modify, or reject AI-generated comments before publication, supporting multiple models and providers per repository.

### Repository-Owned Policy

Review guidelines live in `.ai/review-rules.md` on the default branch, preventing pull requests from manipulating their own review standards. This file can direct focus toward "correctness bugs, security issues, missing tests for behavior changes" while excluding "style-only comments" and "generated files."

### Flexible Model Integration

The system supports "OpenAI-compatible chat completion endpoints," including OpenAI, Hugging Face Router, vLLM, TGI, and LM Studio. This flexibility lets teams select models matching their specific code, policy, cost, and deployment needs.

### Security Considerations

The implementation incorporates multiple safeguards: treating pull request content as untrusted input, loading customization exclusively from default branches, restricting tools to read-only operations, and excluding sensitive environment variables from helper tool execution. Deployment choices reflect GitHub's permission model.

### Real-World Application

Serge operates within production open-source projects including Hugging Face's `diffusers` and `transformers` repositories. The infrastructure supports containerized deployment, database migration paths from SQLite to PostgreSQL, worker admission control, and operational monitoring.

### Getting Started

For quick evaluation: establish a repository secret called `LLM_API_KEY`, integrate the workflow, and comment "@askserge please review" on active pull requests.

The project remains open source, Apache-2.0 licensed, and contributions are welcome at github.com/huggingface/serge with documentation at huggingface.github.io/serge.
