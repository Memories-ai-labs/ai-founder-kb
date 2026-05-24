# Andrej Karpathy

**Company / role**: (ex-OpenAI)  
**Region**: Western  
**Entries**: 11

---

## Dwarkesh Podcast

Date: 2025-10-17 · [Source](https://www.dwarkesh.com/p/andrej-karpathy)

### ★★★ [Strategy]

"It's the decade of agents, not the year of agents." Pattern-matching against 15 years of AI experience — industry hype timelines are consistently too short.

**Memories.ai implication**: Memories.ai implication: Don't let the 2025 agent hype dictate short-term decisions. Design the API for a 5-10 year horizon.

### ★★★ [Strategy]

After actually building nanochat, Karpathy found coding models misunderstand custom implementations, layer on over-defensive error handling, and use deprecated APIs — a strong rebuttal to the "AI automates AI research" narrative. Great at boilerplate, weak at integrating novel systems.

### ★★★ [Strategy]

Model collapse is the fundamental obstacle to self-improvement — ask ChatGPT to tell a joke and you'll only ever get about three variants. Synthetic data fails at scale; humans preserve entropy, models don't.

### ★★★ [Product]

Why coding dominates AI revenue: text-based + existing infrastructure (diff/IDE/VCS) + LLMs are strong at text. Tasks of equivalent surface simplicity (spaced repetition / slides / transcription editing) are still unsolved — pre-built infrastructure determines whether AI can actually land.

**Memories.ai implication**: Memories.ai implication: before building a video-memory product, ask: is there pre-built infrastructure? If not, you have to build it yourself (this is the essential work of Lucy).

### ★★★ [Engineering & Management]

RL is "sucking supervision through a straw" — the whole trajectory gets up/down-weighted equally by the final reward, but the vast majority of intermediate actions are suboptimal. Waiting on an algorithmic breakthrough.

## Sequoia AI Ascent 2026

Date: 2026 · [Source](https://www.youtube.com/watch?v=96jN2OCOfLs)

### ★★★ [Hiring]

Hiring change: classical coding puzzles are obsolete. Agentic engineering hiring: "build me a Twitter clone for agents, then I'll use 10 codex 5.4x to break it." "You can outsource thinking but not understanding."

**Memories.ai implication**: Memories.ai implication: Interviews at xvu / Luci-memory should be reformed — give candidates a large project and have agents evaluate.

### ★★★ [Product]

The MenuGen v3.0 lesson: building your own OCR + image gen + render is "working in the old paradigm." v3.0: photo → Gemini → "use Nano Banana to overlay" → render directly. The whole app is now one model call.

**Memories.ai implication**: Memories.ai implication: What Lucy Desktop's audio_worker.rs does today (pHash + ffmpeg + ElevenLabs + Gemini) might collapse into "upload video → one VLM call → done" within a few versions.

### ★★★ [Product]

"Why are people still telling me what to do? What's the text I should copy-paste to my agent?" All docs / settings / sign-up flows are still written for humans. Genuinely agent-native infrastructure needs sensor/actuator decomposition.

**Memories.ai implication**: Memories.ai implication: the right metric for our public API may not be "docs page views" but "could an agent complete this task end-to-end with no human in the loop?" We need LLM-readable docs.

### ★★★ [Engineering & Management]

Software 1.0 (write code) → 2.0 (train weights) → 3.0 (prompt + context window as program). "What is the piece of text to copy-paste to your agent? That's the programming paradigm now."

**Memories.ai implication**: Memories.ai implication: mintlify-docs should have a "copy-paste this to your Claude" onboarding path — not an SDK, but prompt + tool spec. This is a docs revolution at the affordance level.

### ★★★ [Engineering & Management]

"Verifiability is what makes a domain RL-able. Labs train on verifiable domains, so models come out jagged — peak math / code, weak everywhere else." The chess improvement from GPT-3.5 → 4 wasn't capability — someone at OpenAI added chess data to the pre-training mix.

**Memories.ai implication**: Memories.ai implication: ask whether portrait / personal-memory queries are verifiable. If yes, build our own RL gym instead of waiting for OpenAI / Anthropic to feed us.

### ★★ [Strategy]

"Animals vs ghosts" — LLMs aren't animals (no fun, no curiosity). They're ghosts — pure statistical simulation with RL bolted on. "You can't yell at a ghost."

**Memories.ai implication**: Memories.ai implication: Don't treat Memories.ai ASR/VLM like a "hard-working intern" — there's no inner drive. It can only be driven by spec/context.

---

← [Person index](../README.md) · [→ KB home](../../README.md)