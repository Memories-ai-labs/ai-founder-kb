# Source: Sequoia AI Ascent 2026

**Entries**: 29

---

## Demis Hassabis (DeepMind) — 2026

**★★★** [Strategy]: "Be 5 years ahead, not 50 — Elixir Studios tried to simulate AI for a million-person city on a Pentium. Too early is dead." The AGI 2030 timeline was set as a 20-year mission in 2010, and it's on track so far.

**Memories.ai implication**: Memories.ai implication: A personal memory platform might be too early. Is opening up the API now 5 years early or 50 years early? Lucy in production = 5 years (do it). Notion-level enterprise dataspace = 50 years (defer).

[Source](https://www.youtube.com/watch?v=AFpeWo1GTeg)

---

## Mati Staniszewski (ElevenLabs) — 2026

**★★★** [Strategy]: ElevenLabs launched in 2022 when audio was still a niche: "tons of audio data, you have to transcribe and annotate first, and the model is much smaller than an LLM." Audio was chosen precisely because it bootstraps to revenue fast and doesn't need hundreds of millions in compute.

**Memories.ai implication**: Memories.ai implication: we already picked video AI — but is personal memory + portrait the same kind of unfair angle? A small company can ship a frontier-grade model if the niche is right.

[Source](https://www.youtube.com/watch?v=ZNzYN2jyVTU)

---

## Greg Brockman (OpenAI) — 2026

**★★★** [Strategy]: "Human attention is the new bottleneck — doing things is now easy, but 'is this what I wanted? Is this aligned with my values?' becomes the scarce resource." OpenAI Chronicle lets the model watch the desktop and form memory automatically — "Why are you explaining to your computer what's going on?"

**Memories.ai implication**: Memories.ai implication: Personal memory at Memories.ai is fundamentally about supplying context to AI and conserving human attention. Memories.ai = a human-attention amplifier, not a video search engine. That narrative is far bigger than "video search."

[Source](https://www.youtube.com/watch?v=bBS93A0BeNI)

---

## Boris Cherny (Anthropic) — 2026

**★★★** [Strategy]: The 7 Powers framework: AI erodes switching costs and process power (Claude can learn the process), but network effects, scale economies, and cornered resources still hold. The "SaaS apocalypse" doesn't mean all SaaS dies — it means process-mode companies die. Startup count will go 10×.

**Memories.ai implication**: Memories.ai implication: our moat cannot be built on process (any AI company can replicate it). It must be built on network effects (more users = a better personal model) or a cornered resource (exclusive lifelog data).

[Source](https://www.youtube.com/watch?v=SlGRN8jh2RI)

---

## Oege de Moor (XBOW) — 2026

**★★★** [Strategy]: XBOW autonomously hacked a Bing image search RCE for $3K. #1 hacker on HackerOne. "Alloy of models" — flip a coin at each step to pick Gemini or Sonnet; much better than either model alone. "Time from CVE publish → exploitation has gone NEGATIVE — most CVEs are already being exploited before disclosure."

**Memories.ai implication**: Memories.ai implication: the personal-memory API must go through adversarial red-teaming. Try the "alloy" approach — mix multiple models for query, not just Gemini.

[Source](https://www.youtube.com/watch?v=eHsr1Fl2jNA)

---

## Andrej Karpathy (independent) — 2026

**★★★** [Hiring]: Hiring change: classical coding puzzles are obsolete. Agentic engineering hiring: "build me a Twitter clone for agents, then I'll use 10 codex 5.4x to break it." "You can outsource thinking but not understanding."

**Memories.ai implication**: Memories.ai implication: Interviews at xvu / Luci-memory should be reformed — give candidates a large project and have agents evaluate.

[Source](https://www.youtube.com/watch?v=96jN2OCOfLs)

---

## Andrej Karpathy (independent) — 2026

**★★★** [Product]: The MenuGen v3.0 lesson: building your own OCR + image gen + render is "working in the old paradigm." v3.0: photo → Gemini → "use Nano Banana to overlay" → render directly. The whole app is now one model call.

**Memories.ai implication**: Memories.ai implication: What Lucy Desktop's audio_worker.rs does today (pHash + ffmpeg + ElevenLabs + Gemini) might collapse into "upload video → one VLM call → done" within a few versions.

[Source](https://www.youtube.com/watch?v=96jN2OCOfLs)

---

## Andrej Karpathy (independent) — 2026

**★★★** [Product]: "Why are people still telling me what to do? What's the text I should copy-paste to my agent?" All docs / settings / sign-up flows are still written for humans. Genuinely agent-native infrastructure needs sensor/actuator decomposition.

**Memories.ai implication**: Memories.ai implication: the right metric for our public API may not be "docs page views" but "could an agent complete this task end-to-end with no human in the loop?" We need LLM-readable docs.

[Source](https://www.youtube.com/watch?v=96jN2OCOfLs)

---

## Mati Staniszewski (ElevenLabs) — 2026

**★★★** [Product]: 400 employees, $400M revenue, fewer than 10 per function, no titles, "an engineer embedded in every non-tech team (people / GTM / legal)" — non-engineering teams also vibe-code, with security / review handled by humans.

**Memories.ai implication**: Memories.ai implication: platform-side teams (mintlify-docs writers, BD, support) should all have engineers embedded. That's the way to bridge the "traditional team can't use the AI infra" gap.

[Source](https://www.youtube.com/watch?v=ZNzYN2jyVTU)

---

## Mati Staniszewski (ElevenLabs) — 2026

**★★★** [Product]: Voice agent use case evolution: customer support → revenue-generating (Deliveroo calling restaurants) → government/civic (Ukraine wartime info hotline) → education (MasterClass Gordon Ramsay yelling at you while you cook). "Agents will interrupt the human."

**Memories.ai implication**: Memories.ai implication: Think about the voice entry point — let users query personal memory by natural speech, not GUI. Lucy App's Luci Pin is already live; it should be elevated to a public API.

[Source](https://www.youtube.com/watch?v=ZNzYN2jyVTU)

---

## Boris Cherny (Anthropic) — 2026

**★★★** [Product]: "Coding is solved for me — the model writes 100% of my code, I do ~150 PRs in a day. /loop is a game-changer: cron-scheduled background agents babysit PRs, fix flaky CI, cluster Twitter feedback. Dozens of loops running concurrently. Routines = server-side persistent loops."

**Memories.ai implication**: Memories.ai implication: the public API should natively support a "loop" concept — users/agents can schedule background tasks, cron-style and long-lived.

[Source](https://www.youtube.com/watch?v=SlGRN8jh2RI)

---

## Boris Cherny (Anthropic) — 2026

**★★★** [Product]: The "printing press parallel": before the 1400s, 10% of Europe was literate; within 50 years, more literature was written than in the prior 1,000 years combined. AI is moving far faster than 50 years — software is becoming a basic skill like reading; every accountant writes their own accounting software.

**Memories.ai implication**: Memories.ai implication: our target user shouldn't be "the developer who needs video AI" but "any knowledge worker who has memories they want to query" — orders of magnitude larger market.

[Source](https://www.youtube.com/watch?v=SlGRN8jh2RI)

---

## Andrej Karpathy (independent) — 2026

**★★★** [Engineering & Management]: Software 1.0 (write code) → 2.0 (train weights) → 3.0 (prompt + context window as program). "What is the piece of text to copy-paste to your agent? That's the programming paradigm now."

**Memories.ai implication**: Memories.ai implication: mintlify-docs should have a "copy-paste this to your Claude" onboarding path — not an SDK, but prompt + tool spec. This is a docs revolution at the affordance level.

[Source](https://www.youtube.com/watch?v=96jN2OCOfLs)

---

## Andrej Karpathy (independent) — 2026

**★★★** [Engineering & Management]: "Verifiability is what makes a domain RL-able. Labs train on verifiable domains, so models come out jagged — peak math / code, weak everywhere else." The chess improvement from GPT-3.5 → 4 wasn't capability — someone at OpenAI added chess data to the pre-training mix.

**Memories.ai implication**: Memories.ai implication: ask whether portrait / personal-memory queries are verifiable. If yes, build our own RL gym instead of waiting for OpenAI / Anthropic to feed us.

[Source](https://www.youtube.com/watch?v=96jN2OCOfLs)

---

## Demis Hassabis (DeepMind) — 2026

**★★★** [Engineering & Management]: "Machine learning is the right description language for biology, like math is for physics. Biology = weak signals + tons of data + emergent dynamics — humans can't analyze it, ML is a perfect fit." AI-for-science is the "second exponential."

**Memories.ai implication**: Memories.ai implication: "Personal life as a system to model" may be the same kind of problem — humans emit too many weak signals (location, conversation, mood, sleep) for an ML simulator to be optional.

[Source](https://www.youtube.com/watch?v=AFpeWo1GTeg)

---

## Jim Fan (NVIDIA Robotics) — 2026

**★★★** [Engineering & Management]: The "great parallel" framing: LLMs went pre-train → SFT → RL → auto-research, and robotics has to walk the same path — but with video world models replacing strings. VLA should really be a World Action Model (WAM). "VEO3 emergent physics — gravity, refraction all emerged from next-pixel prediction." RIP teleop, long live sensorized human data.

**Memories.ai implication**: Memories.ai implication: Memories.ai is a video AI company — Jim is saying video world models are about to become the base layer for robotics. We can train our accumulated video data into a personal/business world model and sell it to other companies as a simulation engine.

[Source](https://www.youtube.com/watch?v=3Y8aq_ofEVs)

---

## Jim Fan (NVIDIA Robotics) — 2026

**★★★** [Engineering & Management]: "Ego-centric video scaling law" — 21K hours of human ego video pre-training + 50 hours of mocap glove + 4 hours of teleop = ~0.1% of the training mix on teleop, but generalizes to dexterous tasks. **The iPhone is now a pocket world scanner.**

**Memories.ai implication**: Memories.ai implication: scrmemflow's screen capture + camera data may be exactly this kind of ego-centric training data — we should think hard about whether to monetize the ego-video corpus (worth far more than pure personal-memory search).

[Source](https://www.youtube.com/watch?v=3Y8aq_ofEVs)

---

## Greg Brockman (OpenAI) — 2026

**★★★** [Engineering & Management]: Cost of a prototype is now cheap → the bottleneck shifts to **sharing**. "Provenance tracking" is a new substrate — if a source doc's permissions change, every derived artifact needs to be invalidated.

**Memories.ai implication**: Memories.ai implication: the public API needs similar provenance — when a video is deleted, all derived embeddings, portrait facts, and speeches should cascade-delete.

[Source](https://www.youtube.com/watch?v=bBS93A0BeNI)

---

## Boris Cherny (Anthropic) — 2026

**★★★** [Engineering & Management]: "Cross-disciplinary generalists are the future — everyone on the Claude Code team codes (PM, designer, data scientist, finance, user researcher). Specialists plus everyone-also-codes."

**Memories.ai implication**: Memories.ai implication: do all our PMs / docs writers / sales people also write prototypes? That's the yardstick for whether we're lagging.

[Source](https://www.youtube.com/watch?v=SlGRN8jh2RI)

---

## Anna Goldie + Azalia Mirhoseini (Recursive AI) — 2026

**★★★** [Engineering & Management]: "AlphaChip has been used across 4 generations of Google TPU + Axion CPU + Pixel + autonomous vehicle chips + MediaTek." Key insight: traditional chip design tools run for days per iteration → AI loves fast iteration loops → rewrite the tools to be 100,000× faster → then let AI do RL on top. "The designless era like the fabless era."

**Memories.ai implication**: Memories.ai implication: are our public API endpoint database indexes / RAG retrieval engine in the same spot — internal tools that can be sped up 100,000× and then auto-tuned by AI?

[Source](https://www.youtube.com/watch?v=K05Dh-QjM8c)

---

## Andrej Karpathy (independent) — 2026

**★★** [Strategy]: "Animals vs ghosts" — LLMs aren't animals (no fun, no curiosity). They're ghosts — pure statistical simulation with RL bolted on. "You can't yell at a ghost."

**Memories.ai implication**: Memories.ai implication: Don't treat Memories.ai ASR/VLM like a "hard-working intern" — there's no inner drive. It can only be driven by spec/context.

[Source](https://www.youtube.com/watch?v=96jN2OCOfLs)

---

## Demis Hassabis (DeepMind / Isomorphic) — 2026

**★★** [Strategy]: "Drug discovery 99% should be in silico, wet lab only for the validation step — reduce 10 years → months → days. Build the tool first (AGI), then use the tool to solve everything."

**Memories.ai implication**: Memories.ai implication: the tool-first → use-the-tool-to-solve-everything path is highly relevant. First make the personal-memory API a tool, then let other companies use it to solve healthcare / education / therapy.

[Source](https://www.youtube.com/watch?v=AFpeWo1GTeg)

---

## Jim Fan (NVIDIA Robotics) — 2026

**★★** [Strategy]: "Compute = environments = data." Robotics RL can't rely on a million robots — it relies on real-to-sim-to-real iPhone scans + a handful of real stations + a massive neural simulator. Three milestones: physical Turing test → physical API → physical auto-research.

**Memories.ai implication**: Memories.ai implication: should the public API offer a "capture the world + generate a digital twin" service? That's real AI infrastructure, not just a video understanding API.

[Source](https://www.youtube.com/watch?v=3Y8aq_ofEVs)

---

## Mati Staniszewski (ElevenLabs) — 2026

**★★** [Strategy]: "Authenticated real AI > authenticated real human" — the future detection problem isn't AI vs human, it's authenticated AI vs unauthenticated. All voice should be assumed fake by default.

**Memories.ai implication**: Memories.ai implication: The Memories.ai personal-memory API must build an authenticated identity system — otherwise portrait queries between agents can't establish trust.

[Source](https://www.youtube.com/watch?v=ZNzYN2jyVTU)

---

## Greg Brockman (OpenAI) — 2026

**★★** [Strategy]: "How much compute do we need? All of it. Margin is positive, so scale infinitely." "GPU compute availability in 2026 rounds to zero." OpenAI is refocusing — "singular product: AGI you can talk to with all context." "Painful no's — what we don't build."

**Memories.ai implication**: Memories.ai implication: we need our own "painful no's" — 77 public + 377 shadow endpoints is too many. Cut against a singular product vision.

[Source](https://www.youtube.com/watch?v=bBS93A0BeNI)

---

## Boris Cherny (Anthropic) — 2026

**★★** [Strategy]: Origins of Claude Code: an internal Anthropic Labs incubator, 3 people, team disbands once the mission is done — built Claude Code, MCP, the desktop app. "Build for the next model, not the current model — deliberately spent six months pre-PMF because the model wasn't ready yet."

**Memories.ai implication**: Memories.ai implication: we need an internal incubator culture — 1–2 person teams running for 6 months pre-PMF. luci-oc-cloud not using Memories.ai is a signal the API may simply not be well-designed.

[Source](https://www.youtube.com/watch?v=SlGRN8jh2RI)

---

## Oege de Moor (XBOW) — 2026

**★★** [Strategy]: "Open-weight models will catch up to Microsoft/Claude in cyber capabilities in 6-9 months — start fixing now if you want a peaceful Thanksgiving."

**Memories.ai implication**: Memories.ai implication: The attack surface on Memories.ai personal data will be probed at scale by open-weight models within 6-9 months. The security audit can't wait.

[Source](https://www.youtube.com/watch?v=eHsr1Fl2jNA)

---

## Naveen Rao (Unconventional AI) — 2026

**★★** [Strategy]: "Brain 20W vs. phone 1W vs. squirrel 10mW. The compute substrate from the 1940s was designed for a different purpose. Landauer principle: biology is ~2 orders of magnitude from the physical limit, we're 3 orders below biology." Nobody has asked in 80 years what a computer should actually be.

**Memories.ai implication**: Memories.ai implication: our current inference cost is climbing. Long-term, making always-on lifelog economically viable may require swapping the substrate (neuromorphic / unconventional compute).

[Source](https://www.youtube.com/watch?v=Zw1J5pJJMGw)

---

## Greg Brockman (OpenAI) — 2026

**★★** [Hiring]: "Anecdote: an AI pings a coworker on Slack about an install issue. Two minutes later: 'This is taking too long, I've escalated to manager.' The model's EQ needs work — knowing when to escalate vs. wait."

**Memories.ai implication**: Memories.ai implication: portrait / relationship write operations should have risk classification — not a uniform approval flow, but tiered auto vs. human based on "social cost."

[Source](https://www.youtube.com/watch?v=bBS93A0BeNI)

---

← [Source index](./README.md) · [→ KB home](../README.md)