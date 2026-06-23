Title: Build Real Agentic Apps Using CUGA: Two Dozen Working Examples on a Lightweight Harness
Publisher: HuggingFace (IBM Research)
URL: https://huggingface.co/blog/ibm-research/cuga-apps
Date: 2026-06-23
Source: Hugging Face Blog

---

# Build Real Agentic Apps Using CUGA

This article introduces CUGA (Configurable Generalist Agent), an open-source agent harness from IBM that simplifies building production agentic applications. Rather than requiring weeks of infrastructure work, CUGA handles orchestration, planning, tool execution, and state management—leaving developers to focus on defining tools and prompts.

## Key Contributions

**Simplified Development Model**
The framework reduces boilerplate significantly. According to the authors, "Building an agent is mostly plumbing: tools, state, guardrails, scaling from one agent to many." CUGA abstracts this away, letting developers specify tools and instructions: "The API you touch is small — build a `CugaAgent` with a tool list and a prompt, then `await agent.invoke(...)`."

**Two Dozen Example Applications**
The cuga-apps repository provides 24 production-ready single-file applications demonstrating the framework in action, from movie recommenders to IBM Cloud architecture advisors. These serve as templates rather than sealed demonstrations.

**Built-in Governance**
Unlike bolting controls onto existing systems, governance is foundational. The harness includes six policy types—Intent Guards, Tool Approval, Tool Guides, Playbooks, Output Formatters, and CustomPolicy—enabling teams to enforce safety constraints declaratively.

**Multi-Agent Architecture**
For complex tasks, a `CugaSupervisor` coordinates specialist `CugaAgent` instances, each with isolated context and tools, preventing context bloat while maintaining modularity.

**Production Deployment**
The same agent code runs unchanged in locked-down enterprise environments through IBM Sovereign Core, which provides data isolation, air-gapped execution, per-tool approval, and full observability—without requiring code rewrites.

## Technical Highlights

- **Model Flexibility:** Swappable LLM providers (OpenAI, Anthropic, watsonx, Ollama) via environment variables
- **Tool Integration:** Supports OpenAPI, MCP (Model Context Protocol), and LangChain functions with consistent interfaces
- **Shared Capabilities:** 7 hosted MCP servers (36 tools) for common tasks like web search, geocoding, and finance data
- **Error Handling:** Convention-based response envelopes enable graceful failure recovery instead of derailment
- **Reflection & Self-Correction:** Built-in planning reflection catches and corrects bad decisions mid-execution

## Resources

- [cuga-apps repository](https://github.com/cuga-project/cuga-apps)
- [cuga-agent runtime](https://github.com/cuga-project/cuga-agent)
- [cuga.dev](https://cuga.dev) project home
- [Live app gallery](https://huggingface.co/spaces/ibm-research/cuga-apps)
