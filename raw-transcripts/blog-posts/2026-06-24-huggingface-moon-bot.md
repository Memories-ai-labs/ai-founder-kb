# Building Moon Bot: A Slack-Native Coding Agent Backed by HuggingFace Buckets
# URL: https://huggingface.co/blog/huggingface/moon-bot
# Date: 2026-06-24
# Source: HuggingFace Blog
# Authors: Eliott Coyac, Caleb Fahlgren, Franck Abgrall

HuggingFace developed Moon Bot, an AI agent that lives in Slack and serves as an internal engineering assistant. The tool consolidates access to multiple data sources—Elasticsearch logs, MongoDB, GitHub repositories, and analytics—into a single conversational interface.

## Key Problem Solved

Team members previously had to context-switch between different tools and authentication systems to answer questions. Moon Bot eliminates this friction by allowing engineers and support staff to query databases, pull metrics, browse codebases, and open pull requests directly from Slack threads.

## Architecture

Moon Bot runs as a Kubernetes pod using the Pi coding agent SDK. Each Slack thread receives its own independent agent session with full tool-call history. The bot responds to mentions in channels or direct messages.

## Persistent Memory with HuggingFace Buckets

The bot uses a private bucket (`huggingface/moon-bot-memory`) containing three file types:

- **Session files** (`sessions/<id>.jsonl`): Append-only records of each thread's complete conversation history, enabling resumption after pod restarts
- **Thread map** (`thread-map.json`): Links Slack timestamps to session filenames
- **Memory log** (`memory.json`): Rolling record of recent interactions across all threads, exposed to the LLM for context awareness

## Security Model

Three-tiered access control tied to Okta group membership:
- **Basic tier**: Code Q&A, read-only GitHub access
- **Elastic tier**: Adds Elasticsearch and storage query capabilities
- **Privileged tier**: Full database access

The bot runs tool calls under restricted Linux users with no access to root credentials. External services are accessed only through local HTTP proxies that inject credentials server-side, preventing token exfiltration.

## Notable Capabilities

- Opening pull requests without exposing write credentials to the sandboxed agent
- Running scheduled tasks like weekly operational reports and deploy regression monitoring
- Full auditability: each response links to a JSONL session trace rendered as an interactive agent trace viewer on HuggingFace

## Replicability

The underlying pattern is generalizable: an LLM agent plus file-based sessions in a bucket plus Markdown skill definitions. The infrastructure is relatively straightforward, though writing effective skills requires domain expertise.
