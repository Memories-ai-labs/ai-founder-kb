# OpenAI

**Entries**: 22  
**People featured**: Eric Mitchell + Brandon McKinzie, Greg Brockman, Sam Altman, Sherwin Wu / Christina Huang, Yao Shunyu

---

## Eric Mitchell + Brandon McKinzie

### ★★★ [Engineering & Management] · No Priors (2025-05)

A reasoning model with no tools will "lose its mind in loops" — test-time scaling has to be paired with tool use.

**Memories.ai implication**: Memories.ai implication: we should wrap "portrait / memory query" as a tool definition (for external reasoning models to call).

[Source](https://podscripts.co/podcasts/no-priors-artificial-intelligence-technology-startups/o3-and-the-next-leap-in-reasoning-with-openais-eric-mitchell-and-brandon-mckinzie)

### ★★★ [Engineering & Management] · No Priors (2025-05)

Task difficulty = "environment simulatability" — coding is easy (highly simulatable); robotics is hard.

**Memories.ai implication**: Memories.ai implication: Video tasks have relatively high simulatability — better fit for RL training than robotics.

[Source](https://podscripts.co/podcasts/no-priors-artificial-intelligence-technology-startups/o3-and-the-next-leap-in-reasoning-with-openais-eric-mitchell-and-brandon-mckinzie)

## Greg Brockman

### ★★★ [Strategy] · Cheeky Pint (2025-07)

When the API launched it "felt totally doomed" — nobody knew the use cases; the biggest customer turned out to be AI Dungeon.

**Memories.ai implication**: Memories.ai implication: the public API's first killer use case probably won't be what Memories.ai is imagining today (not search/memory — likely some kind of creative tool).

[Source](https://cheekypint.transistor.fm/1/transcript)

### ★★★ [Product] · Cheeky Pint (2025-07)

The scaling hypothesis came from Dota: 2× compute per week → 2× performance. Not theory — empirical observation.

**Memories.ai implication**: Memories.ai implication: publish our own scaling curves (video duration × indexing quality) so customers can see the ROI of their investment.

[Source](https://cheekypint.transistor.fm/1/transcript)

### ★★★ [Product] · Cheeky Pint (2025-07)

"Refactoring is the killer enterprise feature" — converting legacy COBOL to Python is the best-fit scenario for AI.

**Memories.ai implication**: Memories.ai implication: The video-domain equivalent is "reformatting old footage" — re-cutting and captioning media companies' archives.

[Source](https://cheekypint.transistor.fm/1/transcript)

### ★★★ [Strategy] · Sequoia AI Ascent 2026 (2026)

"Human attention is the new bottleneck — doing things is now easy, but 'is this what I wanted? Is this aligned with my values?' becomes the scarce resource." OpenAI Chronicle lets the model watch the desktop and form memory automatically — "Why are you explaining to your computer what's going on?"

**Memories.ai implication**: Memories.ai implication: Personal memory at Memories.ai is fundamentally about supplying context to AI and conserving human attention. Memories.ai = a human-attention amplifier, not a video search engine. That narrative is far bigger than "video search."

[Source](https://www.youtube.com/watch?v=bBS93A0BeNI)

### ★★★ [Engineering & Management] · Sequoia AI Ascent 2026 (2026)

Cost of a prototype is now cheap → the bottleneck shifts to **sharing**. "Provenance tracking" is a new substrate — if a source doc's permissions change, every derived artifact needs to be invalidated.

**Memories.ai implication**: Memories.ai implication: the public API needs similar provenance — when a video is deleted, all derived embeddings, portrait facts, and speeches should cascade-delete.

[Source](https://www.youtube.com/watch?v=bBS93A0BeNI)

### ★★ [Strategy] · Sequoia AI Ascent 2026 (2026)

"How much compute do we need? All of it. Margin is positive, so scale infinitely." "GPU compute availability in 2026 rounds to zero." OpenAI is refocusing — "singular product: AGI you can talk to with all context." "Painful no's — what we don't build."

**Memories.ai implication**: Memories.ai implication: we need our own "painful no's" — 77 public + 377 shadow endpoints is too many. Cut against a singular product vision.

[Source](https://www.youtube.com/watch?v=bBS93A0BeNI)

### ★★ [Hiring] · Sequoia AI Ascent 2026 (2026)

"Anecdote: an AI pings a coworker on Slack about an install issue. Two minutes later: 'This is taking too long, I've escalated to manager.' The model's EQ needs work — knowing when to escalate vs. wait."

**Memories.ai implication**: Memories.ai implication: portrait / relationship write operations should have risk classification — not a uniform approval flow, but tiered auto vs. human based on "social cost."

[Source](https://www.youtube.com/watch?v=bBS93A0BeNI)

## Yao Shunyu

### ★★★ [Strategy] · Zhang Xiaojun EP115 (2025-09)

In the second half of the agent era the bottleneck shifts: from "method" to "how do you define a good task and good environment."

**Memories.ai implication**: Memories.ai implication: we need to make "personal memory as environment" a public concept — let external agents call into user memory the way they'd call into any environment.

[Source](https://www.xiaoyuzhoufm.com/episode/68c29ca12c82c9dccadba127)

### ★★★ [Strategy] · Zhang Xiaojun EP115 (2025-09)

"Language is a tool humans invented to achieve generalization — it's more fundamental than anything else."

**Memories.ai implication**: Memories.ai implication: there must be a language layer on top of video/image embeddings that external models can consume. Today's public API is thin at this layer.

[Source](https://m.aitntnews.com/newDetail.html?newId=18188)

### ★★★ [Strategy] · Zhang Xiaojun EP115 (2025-09)

The future of intelligence isn't unipolar — it will be defined collectively by multiple Super Apps.

**Memories.ai implication**: Memories.ai implication: Don't chase being "the one entrance to personal AI." Be "the memory layer every Super App calls."

[Source](https://m.aitntnews.com/newDetail.html?newId=18188)

### ★★★ [Product] · Zhang Xiaojun EP115 (2025-09)

The biggest opportunity for startups = designing a different interface. As model capability rises, it will eventually spawn a Super App beyond ChatGPT.

**Memories.ai implication**: Memories.ai implication: Lucy Desktop uses ElevenLabs + direct Gemini calls instead of Memories.ai endpoints = our public API interface isn't good enough. It needs to be redesigned.

[Source](https://m.aitntnews.com/newDetail.html?newId=18188)

## Sherwin Wu / Christina Huang

### ★★★ [Product] · Latent Space (2025-10)

help.openai.com runs on AgentKit itself — internal dogfooding determines whether the public product can succeed.

**Memories.ai implication**: Memories.ai implication: our own internal customer support / sales tools should run on the public API (not internal endpoints) — forcing the API to actually be usable.

[Source](https://www.latent.space/p/devday-2025)

### ★★★ [Product] · Latent Space (2025-10)

ChatKit is deliberately not open-source — it ships as an iframe to stay evergreen, so users automatically pick up new models when they ship.

**Memories.ai implication**: Memories.ai implication: our "player / search widget" should be an iframe, not an SDK — avoid users getting stuck on old versions.

[Source](https://www.latent.space/p/devday-2025)

### ★★★ [Product] · Latent Space (2025-10)

The MCP adoption decision is easy because "it really is an open protocol."

**Memories.ai implication**: Memories.ai implication: Memories.ai should plug into MCP as fast as possible, exposing portrait/memory queries to Claude/ChatGPT/Cursor.

[Source](https://www.latent.space/p/devday-2025)

## Sam Altman

### ★★ [Strategy] · Uncapped (2025-06)

Medium-term (5–10 years), AI will genuinely "discover new science" — not just mimic existing knowledge.

**Memories.ai implication**: Memories.ai implication: our long-term narrative should be explicit: "video/memory data is the largest untapped training source for new scientific discovery."

[Source](https://podcasts.apple.com/do/podcast/uncapped-13-sam-altman-from-openai/id1801867202)

### ★★ [Strategy] · Uncapped (2025-06)

The "strangest marker" is widespread humanoid robots — more iconic than AGI software itself.

**Memories.ai implication**: Memories.ai implication: Lucy Pin / Glass-class hardware is well-positioned if it lands on the humanoid wave.

[Source](https://podcasts.apple.com/do/podcast/uncapped-13-sam-altman-from-openai/id1801867202)

### ★★ [Strategy] · Big Technology Podcast (2025-12-18)

Memory is the lock-in moat: long-term "infinite, perfect memory" creates massive switching cost — competitors can't copy the context a user has accumulated.

**Memories.ai implication**: Memories.ai implication: direct validation of our core direction. But OpenAI is also building memory — we have to move faster than they do.

[Source](https://www.bigtechnology.com/p/sam-altman-on-openais-plan-to-win)

### ★★ [Strategy] · Big Technology Podcast (2025-12-18)

Hardware isn't a single device but a Jony Ive-designed device family that understands user context across physical and digital environments.

**Memories.ai implication**: Memories.ai implication: ChatGPT-as-OS is now an explicit direction — OpenAI has validated the Luci Pin hardware path.

[Source](https://www.bigtechnology.com/p/sam-altman-on-openais-plan-to-win)

### ★★ [Product] · Big Technology Podcast (2025-12-18)

Product direction: deliberately build EQ + relationship-forming, but don't lock users in — positioned as a differentiator against competitors who monetize emotional engagement.

[Source](https://www.bigtechnology.com/p/sam-altman-on-openais-plan-to-win)

### ★★ [Hiring] · Conversations with Tyler (2026)

The big green flag in candidate evaluation: "how they use AI today" + whether they think about "what their day-to-day is going to look like in three years."

**Memories.ai implication**: Memories.ai implication: Ask Memories.ai candidates directly: what AI tools do you use today? What does your work look like in 3 years?

[Source](https://conversationswithtyler.com/episodes/sam-altman-2/)

---
← [Company index](./README.md) · [→ KB home](../README.md)