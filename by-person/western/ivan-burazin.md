# Ivan Burazin

**Company / role**: Daytona  
**Region**: Western  
**Entries**: 4

---

## Latent Space

Date: 2026-05 · [Source](https://www.latent.space/p/daytona)

### ★★★ [Product]

After the pivot, customers proactively called asking for an API key — that kind of "product pull" is the gold standard for confirming you pivoted correctly.

**Memories.ai implication**: Memories.ai implication: The Lucy team should ask: "If we open up the portrait API today, will external developers actively come asking for keys?" If not, the positioning needs another look.

### ★★★ [Product]

A 25-person team differentiates on "insane responsiveness" (instant Slack/Huddle reply).

**Memories.ai implication**: Memories.ai implication: in the early phase of the public API, the founder should be personally in the Slack channel (not behind a ticketing system).

### ★★★ [Engineering & Management]

RL / eval workloads went from 0% → 50% of platform usage in a few months; agent workloads have an extreme spiky pattern of "15% flat → 90% bursts."

**Memories.ai implication**: Memories.ai implication: billing and capacity models should assume burst, not steady — measure "burst budget" rather than "req/s."

### ★★★ [Engineering & Management]

Bare metal + custom scheduling can hit 60ms cold-start per sandbox / 75 seconds for 50,000 sandboxes — both K8s and Firecracker are too slow.

**Memories.ai implication**: Memories.ai implication: If we want to build a "video sandbox" (agents processing user video), we also have to skip K8s.

---

← [Person index](../README.md) · [→ KB home](../../README.md)