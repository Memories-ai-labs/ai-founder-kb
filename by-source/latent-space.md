# Source: Latent Space

**Entries**: 11

**Local raw transcripts**: 240 posts in [`raw-transcripts/latent-space/`](../raw-transcripts/latent-space/) — RSS-derived from `latent.space`. Long-form transcripts with AI engineers (NotebookLM team, Cursor, OpenAI Realtime, Devday, Drew Houston, etc.) plus shorter announcements. See folder [README](../raw-transcripts/latent-space/README.md) for index.

---

## Sherwin Wu / Christina Huang (OpenAI) — 2025-10

**★★★** [Product]: help.openai.com runs on AgentKit itself — internal dogfooding determines whether the public product can succeed.

**Memories.ai implication**: Memories.ai implication: our own internal customer support / sales tools should run on the public API (not internal endpoints) — forcing the API to actually be usable.

[Source](https://www.latent.space/p/devday-2025)

---

## Sherwin Wu / Christina Huang (OpenAI) — 2025-10

**★★★** [Product]: ChatKit is deliberately not open-source — it ships as an iframe to stay evergreen, so users automatically pick up new models when they ship.

**Memories.ai implication**: Memories.ai implication: our "player / search widget" should be an iframe, not an SDK — avoid users getting stuck on old versions.

[Source](https://www.latent.space/p/devday-2025)

---

## Sherwin Wu / Christina Huang (OpenAI) — 2025-10

**★★★** [Product]: The MCP adoption decision is easy because "it really is an open protocol."

**Memories.ai implication**: Memories.ai implication: Memories.ai should plug into MCP as fast as possible, exposing portrait/memory queries to Claude/ChatGPT/Cursor.

[Source](https://www.latent.space/p/devday-2025)

---

## Jake Cooper (Railway) — 2026-04

**★★★** [Product]: "Agents don't need new primitives — they need 1000× the old primitives." Version control, observability — all of it has to be re-scaled.

**Memories.ai implication**: Memories.ai implication: API rate limits shouldn't be measured in requests/min — they should be measured in concurrent agent context.

[Source](https://www.latent.space/p/railway)

---

## Jake Cooper (Railway) — 2026-04

**★★★** [Product]: CLI matters more than canvas — agents need fine-grained control; the canvas becomes "the human review dashboard."

**Memories.ai implication**: Memories.ai implication: build a strong CLI / SDK first; the UI dashboard is secondary.

[Source](https://www.latent.space/p/railway)

---

## Jake Cooper (Railway) — 2026-04

**★★★** [Engineering & Management]: Building bare metal: 3-month payback, 70% margin — cloud economics have already flipped.

**Memories.ai implication**: Memories.ai implication: Given Memories.ai's video processing volume, we should also consider colocation / bare metal — especially for steady workloads like ASR + embedding.

[Source](https://www.latent.space/p/railway)

---

## Ivan Burazin (Daytona) — 2026-05

**★★★** [Product]: After the pivot, customers proactively called asking for an API key — that kind of "product pull" is the gold standard for confirming you pivoted correctly.

**Memories.ai implication**: Memories.ai implication: The Lucy team should ask: "If we open up the portrait API today, will external developers actively come asking for keys?" If not, the positioning needs another look.

[Source](https://www.latent.space/p/daytona)

---

## Ivan Burazin (Daytona) — 2026-05

**★★★** [Product]: A 25-person team differentiates on "insane responsiveness" (instant Slack/Huddle reply).

**Memories.ai implication**: Memories.ai implication: in the early phase of the public API, the founder should be personally in the Slack channel (not behind a ticketing system).

[Source](https://www.latent.space/p/daytona)

---

## Ivan Burazin (Daytona) — 2026-05

**★★★** [Engineering & Management]: RL / eval workloads went from 0% → 50% of platform usage in a few months; agent workloads have an extreme spiky pattern of "15% flat → 90% bursts."

**Memories.ai implication**: Memories.ai implication: billing and capacity models should assume burst, not steady — measure "burst budget" rather than "req/s."

[Source](https://www.latent.space/p/daytona)

---

## Ivan Burazin (Daytona) — 2026-05

**★★★** [Engineering & Management]: Bare metal + custom scheduling can hit 60ms cold-start per sandbox / 75 seconds for 50,000 sandboxes — both K8s and Firecracker are too slow.

**Memories.ai implication**: Memories.ai implication: If we want to build a "video sandbox" (agents processing user video), we also have to skip K8s.

[Source](https://www.latent.space/p/daytona)

---

## Aman Sanger (Cursor (Anysphere)) — 2024

**★★** [Product]: "We need a brand new AI-powered IDE" — the early Cursor thesis. Background: time spent across Gamelon/Bridgewater/McKinsey/Google/You.com — a composite background matters more than a pure ML resume.

[Source](https://www.latent.space/p/cursor)

---

← [Source index](./README.md) · [→ KB home](../README.md)