# Engineering & Management (70 entries)

Sorted by signal strength (★★★ → ★★ → ★). Each entry includes source, link, and Memories.ai implication (if any).

---

## ★★★ (54 entries)

### Demis Hassabis — DeepMind · *Dwarkesh Podcast* (2024-02)

LLMs are a world model, but you still need "AlphaZero-like planning" layered on top — an LLM alone isn't enough for AGI.

**Memories.ai implication**: Memories.ai implication: treat "planning over video" as an independent component (not just chat).

[Source](https://www.dwarkesh.com/p/demis-hassabis)

---

### Demis Hassabis — DeepMind · *Dwarkesh Podcast* (2024-02)

"Scaling is an art form" — every stage requires tuning the recipe, not just mechanical scale-up; intermediate data points have to be validated.

**Memories.ai implication**: Memories.ai implication: video-model scaling can't directly inherit LLM scaling laws — we need our own data points.

[Source](https://www.dwarkesh.com/p/demis-hassabis)

---

### Liang Wenfeng — DeepSeek · *Wavelet (Waves) Interview* (2024-07)

"Chinese AI can't follow forever — someone has to stand at the frontier of the technology."

[Source](https://zhuanlan.zhihu.com/p/24066797610)

---

### Songlin — MIT 解读 · *Zhang Xiaojun EP94* (2025-02)

DeepSeek NSA + Kimi MOBA + MiniMax hybrid = three different long-context attention solutions; NSA is faster than full attention at both training and inference.

**Memories.ai implication**: Memories.ai implication: personal-memory retrieval is the canonical long-context scenario. The current RAG path should be re-evaluated against all three attention approaches.

[Source](https://www.xiaoyuzhoufm.com/episode/67bb3696606e5c5940533ef4)

---

### Sholto Douglas + Trenton Bricken — Anthropic · *Dwarkesh Podcast* (2025-05)

RL success = clean reward signals: "does it compile? does it pass the test?" Taste-based feedback remains nebulous.

**Memories.ai implication**: Memories.ai implication: Lucy's recap / portrait needs verifiable rewards (user retention / edit rate) — can't rely on human eval alone.

[Source](https://www.dwarkesh.com/p/sholto-trenton-2)

---

### Sholto Douglas + Trenton Bricken — Anthropic · *Dwarkesh Podcast* (2025-05)

The "evil model" experiment: fine-tuning on news articles about AI misalignment causes the model to adopt that persona — alignment lives at the persona/identity layer.

**Memories.ai implication**: Memories.ai implication: A personal memory model can't be trained on generic AI data — it'll describe itself as "an AI assistant" and break the personal experience.

[Source](https://www.dwarkesh.com/p/sholto-trenton-2)

---

### Sholto Douglas + Trenton Bricken — Anthropic · *Dwarkesh Podcast* (2025-05)

Inference compute will hit its ceiling before capability does: 100M H100s ~ 10M genius-level agents — not population scale.

**Memories.ai implication**: Memories.ai implication: the "always-on agent per user" cost model needs to be reworked from scratch.

[Source](https://www.dwarkesh.com/p/sholto-trenton-2)

---

### Eric Mitchell + Brandon McKinzie — OpenAI · *No Priors* (2025-05)

A reasoning model with no tools will "lose its mind in loops" — test-time scaling has to be paired with tool use.

**Memories.ai implication**: Memories.ai implication: we should wrap "portrait / memory query" as a tool definition (for external reasoning models to call).

[Source](https://podscripts.co/podcasts/no-priors-artificial-intelligence-technology-startups/o3-and-the-next-leap-in-reasoning-with-openais-eric-mitchell-and-brandon-mckinzie)

---

### Eric Mitchell + Brandon McKinzie — OpenAI · *No Priors* (2025-05)

Task difficulty = "environment simulatability" — coding is easy (highly simulatable); robotics is hard.

**Memories.ai implication**: Memories.ai implication: Video tasks have relatively high simulatability — better fit for RL training than robotics.

[Source](https://podscripts.co/podcasts/no-priors-artificial-intelligence-technology-startups/o3-and-the-next-leap-in-reasoning-with-openais-eric-mitchell-and-brandon-mckinzie)

---

### He Xiaopeng — XPeng Motors · *Luo Yonghao's Crossroads EP2* (2025-08-26)

Within one year, replaced more than a dozen execs + 90% of all first-level departments. "The chairman has to charge to the front line and act as CEO."

**Memories.ai implication**: Memories.ai implication: during a platform-strategy pivot, execs have to be hands-on in API design review — can't fully delegate.

[Source](https://finance.sina.com.cn/tech/csj/2025-08-27/doc-infnkyfm9223501.shtml)

---

### Yang Zhilin — Moonshot / Kimi · *Zhang Xiaojun Business Interview PodcastEP113* (2025-08-27)

Test-time scaling: long thinking and Agent RL both point in this direction; the biggest challenge is generalization.

[Source](https://podcasts.apple.com/us/podcast/id1634356920?i=1000723667168)

---

### Yang Zhilin — Moonshot / Kimi · *Zhang Xiaojun Business Interview PodcastEP113* (2025-08-27)

The management philosophy of team member Tim (Zhou Xinyu): "manage people with RL, not SFT" — give goals, not steps. "A lot of complexity is added by humans."

**Memories.ai implication**: Memories.ai implication: Management also has to give reward signals, not SOPs — especially for AI engineers.

[Source](https://podcasts.apple.com/us/podcast/id1634356920?i=1000723667168)

---

### Andrej Karpathy — (ex-OpenAI) · *Dwarkesh Podcast* (2025-10-17)

RL is "sucking supervision through a straw" — the whole trajectory gets up/down-weighted equally by the final reward, but the vast majority of intermediate actions are suboptimal. Waiting on an algorithmic breakthrough.

[Source](https://www.dwarkesh.com/p/andrej-karpathy)

---

### Wang Tao — DJI · *Huxiu Deep Interview* (2025-11)

A CEO can resolve at most ~4,000 "entropy reductions" a year, but 6,000 employees generate far more entropy. The solution is developing managers + tooling systems. Org capability going from 50 to 70 is "the chasm 99.9% of companies never cross." DJI took 8 years.

[Source](https://m.huxiu.com/article/4849425.html)

---

### Wang Tao — DJI · *Huxiu Deep Interview* (2025-11)

"For the first half of my life I was driven by the ego of being #1." Later I realized "the word 'I' is poison."

[Source](https://m.huxiu.com/article/4849425.html)

---

### Amjad Masad — Replit · *Sequoia Training Data* (2025-11)

Legacy products are optimized for the previous generation of model capability — they become a "local maximum." Cursor's integration with Claude 3.5 had issues = the IDE was never architected for an agentic reasoning loop. Replit is willing to scrap and rebuild.

**Memories.ai implication**: Memories.ai implication: the public API also has to be willing to rebuild when model capability jumps — Lucy Desktop's BFF layer is a local maximum.

[Source](https://sequoiacap.com/podcast/training-data-amjad-masad/)

---

### Gorkem Yurtseven — fal · *Sequoia Training Data* (2025-12)

Video models are compute-bound (LLMs are memory-bound) — completely different optimization paths.

**Memories.ai implication**: Memories.ai implication: the video pipeline must be compute-saturating — don't copy LLM-serving optimizations.

[Source](https://sequoiacap.com/podcast/the-rise-of-generative-media-fals-bet-on-video-infrastructure-and-speed/)

---

### Gorkem Yurtseven — fal · *Sequoia Training Data* (2025-12)

The half-life of a top-5 video model is 30 days — you have to build a tracing compiler that swaps kernels automatically; you can't hand-tune a single model.

**Memories.ai implication**: Memories.ai implication: Video indexing faces the same 30-day model turnover — the architecture has to support hot-swapping the backbone.

[Source](https://sequoiacap.com/podcast/the-rise-of-generative-media-fals-bet-on-video-infrastructure-and-speed/)

---

### Yan Junjie — MiniMax · *Luo Yonghao's Crossroads* (2025-12-10)

Wobbled for six months early on — "we thought AI talent + internet talent was enough; it just didn't work." The two logics can't coexist.

**Memories.ai implication**: Memories.ai implication: don't mix "big-tech veterans" with "AI people" in hiring — the culture will tear apart.

[Source](https://m.thepaper.cn/newsDetail_forward_32148957)

---

### Winston Weinberg — Harvey · *Sequoia Training Data* (2026)

"Penalize inaction, not failure": "I would much rather people just try and make a decision and then it's wrong, and a week later they adjust." Speed beats decision accuracy.

[Source](https://sequoiacap.com/podcast/harvey-ceo-winston-weinberg-why-you-should-reinvent-yourself-every-4-months/)

---

### Winston Weinberg — Harvey · *Sequoia Training Data* (2026)

The four-month cycle: "Every four months, I'd say, I get this mental block that there's too many things going wrong." Every 4 months you need to reinvent yourself — different leadership hires, structural changes.

[Source](https://sequoiacap.com/podcast/harvey-ceo-winston-weinberg-why-you-should-reinvent-yourself-every-4-months/)

---

### Bret Taylor — Sierra · *Cheeky Pint (John Collison)* (2026)

"The atomic unit of productivity in AI is a process, not a person." Most companies "ship their org charts" — using AI to optimize departments rather than reimagining the end-to-end workflow.

**Memories.ai implication**: Memories.ai implication: don't ship Lucy features one user-feature at a time. Design the API around end-to-end processes (e.g. "remember every meeting → surface insight → action item → follow-up").

[Source](https://cheekypint.substack.com/p/bret-taylor-of-sierra-on-ai-agents)

---

### Sonya Huang — Sequoia · *AI Ascent 2026 Keynote* (2026)

The agenticness spectrum: tab autocomplete → agentic dev → background / async agents → dark factories (no human review, straight to prod). Bret Taylor rebuilt Sierra over a weekend; Notion rewrote 8M lines in 6 weeks; "what you imagined over 100 years is now possible in 100 days."

**Memories.ai implication**: Memories.ai implication: for the infrastructure team — can agents auto-generate SDKs / docs / the multi-tenant layer / billing for xvu's ~454 endpoints?

[Source](https://www.youtube.com/watch?v=LRo33rnv6rQ)

---

### Ivan Zhao — Notion · *Sequoia Founder Spotlight* (2026)

"Building with LLMs is brewing beer, not engineering bridges" — you can't tell the yeast which flavor profile to hit. Designer + engineer + PM all sit around one cask, working through evals and experience, not PM→designer→engineer waterfall.

**Memories.ai implication**: Memories.ai implication: Memories.ai docs can't lead with "business use cases" the way traditional SaaS docs do — go straight to evals/examples/playgrounds. Lucy wrapping a BFF on top of luci-oc is exactly because the public API is too "bridge."

[Source](https://www.youtube.com/watch?v=ill76IbVuM8)

---

### Andrej Karpathy — independent · *Sequoia AI Ascent 2026* (2026)

Software 1.0 (write code) → 2.0 (train weights) → 3.0 (prompt + context window as program). "What is the piece of text to copy-paste to your agent? That's the programming paradigm now."

**Memories.ai implication**: Memories.ai implication: mintlify-docs should have a "copy-paste this to your Claude" onboarding path — not an SDK, but prompt + tool spec. This is a docs revolution at the affordance level.

[Source](https://www.youtube.com/watch?v=96jN2OCOfLs)

---

### Andrej Karpathy — independent · *Sequoia AI Ascent 2026* (2026)

"Verifiability is what makes a domain RL-able. Labs train on verifiable domains, so models come out jagged — peak math / code, weak everywhere else." The chess improvement from GPT-3.5 → 4 wasn't capability — someone at OpenAI added chess data to the pre-training mix.

**Memories.ai implication**: Memories.ai implication: ask whether portrait / personal-memory queries are verifiable. If yes, build our own RL gym instead of waiting for OpenAI / Anthropic to feed us.

[Source](https://www.youtube.com/watch?v=96jN2OCOfLs)

---

### Demis Hassabis — DeepMind · *Sequoia AI Ascent 2026* (2026)

"Machine learning is the right description language for biology, like math is for physics. Biology = weak signals + tons of data + emergent dynamics — humans can't analyze it, ML is a perfect fit." AI-for-science is the "second exponential."

**Memories.ai implication**: Memories.ai implication: "Personal life as a system to model" may be the same kind of problem — humans emit too many weak signals (location, conversation, mood, sleep) for an ML simulator to be optional.

[Source](https://www.youtube.com/watch?v=AFpeWo1GTeg)

---

### Jim Fan — NVIDIA Robotics · *Sequoia AI Ascent 2026* (2026)

The "great parallel" framing: LLMs went pre-train → SFT → RL → auto-research, and robotics has to walk the same path — but with video world models replacing strings. VLA should really be a World Action Model (WAM). "VEO3 emergent physics — gravity, refraction all emerged from next-pixel prediction." RIP teleop, long live sensorized human data.

**Memories.ai implication**: Memories.ai implication: Memories.ai is a video AI company — Jim is saying video world models are about to become the base layer for robotics. We can train our accumulated video data into a personal/business world model and sell it to other companies as a simulation engine.

[Source](https://www.youtube.com/watch?v=3Y8aq_ofEVs)

---

### Jim Fan — NVIDIA Robotics · *Sequoia AI Ascent 2026* (2026)

"Ego-centric video scaling law" — 21K hours of human ego video pre-training + 50 hours of mocap glove + 4 hours of teleop = ~0.1% of the training mix on teleop, but generalizes to dexterous tasks. **The iPhone is now a pocket world scanner.**

**Memories.ai implication**: Memories.ai implication: scrmemflow's screen capture + camera data may be exactly this kind of ego-centric training data — we should think hard about whether to monetize the ego-video corpus (worth far more than pure personal-memory search).

[Source](https://www.youtube.com/watch?v=3Y8aq_ofEVs)

---

### Dmitri Dolgov — Waymo · *Sequoia Founder Spotlight* (2026)

"Safety is a non-negotiable foundation from day 1, not an add-on at 90%. 90→99→99.9→99.99 are completely different problems and can't be solved the same way — this is why the AV hype cycle keeps failing." Waymo uses end-to-end model + structured materialized intermediate representation (not vanilla end-to-end).

**Memories.ai implication**: Memories.ai implication: Memories.ai's "personal memory + portrait + relationships" will eventually touch user-private data at production-grade safety. Lucy currently calls internal endpoints directly with no observability layer — a critical gap.

[Source](https://www.youtube.com/watch?v=I_0Kuf6Aa2c)

---

### Greg Brockman — OpenAI · *Sequoia AI Ascent 2026* (2026)

Cost of a prototype is now cheap → the bottleneck shifts to **sharing**. "Provenance tracking" is a new substrate — if a source doc's permissions change, every derived artifact needs to be invalidated.

**Memories.ai implication**: Memories.ai implication: the public API needs similar provenance — when a video is deleted, all derived embeddings, portrait facts, and speeches should cascade-delete.

[Source](https://www.youtube.com/watch?v=bBS93A0BeNI)

---

### Boris Cherny — Anthropic · *Sequoia AI Ascent 2026* (2026)

"Cross-disciplinary generalists are the future — everyone on the Claude Code team codes (PM, designer, data scientist, finance, user researcher). Specialists plus everyone-also-codes."

**Memories.ai implication**: Memories.ai implication: do all our PMs / docs writers / sales people also write prototypes? That's the yardstick for whether we're lagging.

[Source](https://www.youtube.com/watch?v=SlGRN8jh2RI)

---

### Jack Dorsey — Block · *Sequoia Founder Spotlight* (2026)

Block's reorg: only 3 roles — IC (builder, "judgment + taste + creativity") + DRI (customer outcomes, "ownership + accountability") + Player Coach ("capability building, shown not told"). One person can be all three at once. Max depth 5 → target 2-3 → ideally 1 (all 6,000 people reporting up to Jack).

**Memories.ai implication**: Memories.ai implication: At Memories.ai's thousand-person scale, try the 3-role experiment in 1-2 BUs — e.g., have the mavi-agent team operate fully as IC/DRI/Player Coach.

[Source](https://www.youtube.com/watch?v=YTVSwOY19Qs)

---

### Jack Dorsey — Block · *Sequoia Founder Spotlight* (2026)

"Meetings 2 months ago = slide deck review. Now = everyone brings a prototype, simulated or real data, modifiable in real time. Cost of being wrong is approaching zero — explore widely, then judgment pulls a focused thread."

**Memories.ai implication**: Memories.ai implication: ban pure decks in internal product reviews — require a working prototype + data. mintlify-docs should be a live playground, not static text.

[Source](https://www.youtube.com/watch?v=YTVSwOY19Qs)

---

### Sally Kornbluth — MIT · *Sequoia podcast* (2026)

"Don't solve problems with processes. Solve with DRIs + operating control" — the moment you add process, you start managing process instead of outcome. "Push decisions down, you can't punish mistakes — leadership corrects quickly, not prevents."

**Memories.ai implication**: Memories.ai implication: are we piling on process when we add endpoints? Audit which areas are DRI-owned vs. process-owned.

[Source](https://www.youtube.com/watch?v=e_2opghuq88)

---

### Sally Kornbluth — MIT · *Sequoia podcast* (2026)

"The 5:1 praise ratio is real, but only if you really mean it — if you fake praise, people think they're doing great when they're not." "Direct + blunt without being a jerk — write it down the night before, say it, don't add fluff" (Bill Campbell).

**Memories.ai implication**: Memories.ai implication: Culture-building — is the team's honest-negative-feedback culture actually healthy?

[Source](https://www.youtube.com/watch?v=e_2opghuq88)

---

### Dick Costolo — Twitter (ex-CEO) · *Sequoia Training Data* (2026)

"Velocity velocity velocity" — first principle when he took over Twitter. For every process, ask "what would have to change to take this from 6 weeks to 2?" No group decisions — push decisions down, name DRIs, "bias to yes" (only the direct manager can say no; no team is allowed to block by saying "go ask 14 people for approval").

**Memories.ai implication**: Memories.ai implication: is the xvu Java gateway's internal-endpoint decision process bias-to-yes? Or are sales / legal / security each running their own 14-person approval chain?

[Source](https://www.youtube.com/watch?v=Kw5hhIsw-wQ)

---

### Dick Costolo — Twitter (ex-CEO) · *Sequoia Training Data* (2026)

"Forestry management vs. putting out forest fires" — directors who only stamp out fires don't scale. Teach the director: don't get stuck in the fire, draw the territorial map — "what has to be true in 24 months."

**Memories.ai implication**: Memories.ai implication: are the infrastructure leads firefighting, or drawing the territorial map?

[Source](https://www.youtube.com/watch?v=Kw5hhIsw-wQ)

---

### Dick Costolo — Twitter (ex-CEO) · *Sequoia Training Data* (2026)

"Hire slow, fire fast" is a slogan — 99% of CEOs do the opposite. Managers use "trans-firing" (move them to the ads team) to dodge it. Rule: if the rating is below threshold, no transfer allowed. Look for people who score 2→3→2 — that tells you the manager is inflating.

**Memories.ai implication**: Memories.ai implication: When Memories.ai hires mid-level staff in bulk, the transfer policy has to be strict.

[Source](https://www.youtube.com/watch?v=Kw5hhIsw-wQ)

---

### Anna Goldie + Azalia Mirhoseini — Recursive AI · *Sequoia AI Ascent 2026* (2026)

"AlphaChip has been used across 4 generations of Google TPU + Axion CPU + Pixel + autonomous vehicle chips + MediaTek." Key insight: traditional chip design tools run for days per iteration → AI loves fast iteration loops → rewrite the tools to be 100,000× faster → then let AI do RL on top. "The designless era like the fabless era."

**Memories.ai implication**: Memories.ai implication: are our public API endpoint database indexes / RAG retrieval engine in the same spot — internal tools that can be sped up 100,000× and then auto-tuned by AI?

[Source](https://www.youtube.com/watch?v=K05Dh-QjM8c)

---

### Dario Amodei — Anthropic · *Dwarkesh Podcast* (2026-02-13)

Dogfooding is critical to product validation: "We have folks who say, this GPU kernel I used to write myself. I just have Claude do it." A 2,500-person internal feedback loop validates PMF before external release.

**Memories.ai implication**: Memories.ai implication: the entire internal team should dogfood the public API — if our own people don't want to use it, external developers definitely won't.

[Source](https://www.dwarkesh.com/p/dario-amodei-2)

---

### Dylan Patel — SemiAnalysis · *Dwarkesh Podcast* (2026-03)

The real bottleneck is ASML EUV: every GW of Rubin requires 3.5 EUV tools, capping AI at ~200GW by 2030 — it's not power, it's silicon.

**Memories.ai implication**: Memories.ai implication: Building our own inference long-term is unsustainable — long-term GPU rental contracts are key. If we have our own video model, we need to do the GPU economics carefully.

[Source](https://www.dwarkesh.com/p/dylan-patel)

---

### Dylan Patel — SemiAnalysis · *Dwarkesh Podcast* (2026-03)

DRAM prices tripled → iPhone BOM +$150 → smartphone shipments could fall from 1.1B to 5–600M.

**Memories.ai implication**: Memories.ai implication: the "local-first" narrative for on-device AI (Lucy Pin / Desktop) gets more expensive, which actually strengthens the cost advantage of cloud-side processing.

[Source](https://www.dwarkesh.com/p/dylan-patel)

---

### Lin Junyang — Qwen (Alibaba Tongyi) · *36Kr + Guancha* (2026-03-04)

Lin Junyang, the youngest P10 in Alibaba history, led Qwen to over half the global open-source share — and then left, due to team restructuring + new models missing expectations.

**Memories.ai implication**: Memories.ai implication: even when your tech lead is industry #1, big-company org churn still pushes core talent out — a startup has to give the tech leader long-term, stable org authority.

[Source](https://www.36kr.com/p/3708425301749891)

---

### Simon Willison — indie · *Lenny's Podcast* (2026-04)

The "lethal trifecta": private data + untrusted content + external comms = prompt injection. Lucy/scrmemflow is massively exposed.

**Memories.ai implication**: Memories.ai implication: Lucy Desktop handles screenshots + OAuth to 8 connectors + outbound API calls = a perfect lethal trifecta. We need platform-level defenses at the Memories.ai layer.

[Source](https://www.lennysnewsletter.com/p/an-ai-state-of-the-union)

---

### Simon Willison — indie · *Lenny's Podcast* (2026-04)

"Dark factory" — nobody writes code, nobody reviews it, AI QAs itself. But mid-career engineers, not juniors, get hit hardest.

**Memories.ai implication**: Memories.ai implication: the engineering org should have seniors lead evaluation and standards, and hand execution to AI.

[Source](https://www.lennysnewsletter.com/p/an-ai-state-of-the-union)

---

### Evan Spiegel — Snap · *Cheeky Pint* (2026-04)

Two-thirds of new Snap code is written by Claude; services that used to need 15 engineers now run on "half a person's time."

**Memories.ai implication**: Memories.ai implication: don't estimate xvu refactor work in "engineer-months" — estimate in "AI agent-months."

[Source](https://cheekypint.substack.com/p/what-comes-after-smartphones-with)

---

### Jake Cooper — Railway · *Latent Space* (2026-04)

Building bare metal: 3-month payback, 70% margin — cloud economics have already flipped.

**Memories.ai implication**: Memories.ai implication: Given Memories.ai's video processing volume, we should also consider colocation / bare metal — especially for steady workloads like ASR + embedding.

[Source](https://www.latent.space/p/railway)

---

### Logan Kilpatrick + Tulsee Doshi — Google DeepMind · *Cognitive Revolution* (2026-05)

"The model eats the scaffolding. Every crank of the model flywheel, the model eats a bunch of scaffolding." DeepMind now ships a complete agent harness instead of a bare model — and simultaneously trains for "harness diversity" so the model generalizes outside Google.

**Memories.ai implication**: Memories.ai implication: the scaffolding application-layer startups are building today may get eaten by the model next year. Lucy Desktop's BFF proxy and pHash dedup are exactly this kind of soon-to-be-eaten scaffolding.

[Source](https://www.cognitiverevolution.ai/the-model-eats-the-scaffolding-deepmind-s-logan-kilpatrick-tulsee-doshi-on-3-5-flash-omni-more/)

---

### Ivan Burazin — Daytona · *Latent Space* (2026-05)

RL / eval workloads went from 0% → 50% of platform usage in a few months; agent workloads have an extreme spiky pattern of "15% flat → 90% bursts."

**Memories.ai implication**: Memories.ai implication: billing and capacity models should assume burst, not steady — measure "burst budget" rather than "req/s."

[Source](https://www.latent.space/p/daytona)

---

### Ivan Burazin — Daytona · *Latent Space* (2026-05)

Bare metal + custom scheduling can hit 60ms cold-start per sandbox / 75 seconds for 50,000 sandboxes — both K8s and Firecracker are too slow.

**Memories.ai implication**: Memories.ai implication: If we want to build a "video sandbox" (agents processing user video), we also have to skip K8s.

[Source](https://www.latent.space/p/daytona)

---

### Anthropic Team — Anthropic · *Founder's Playbook — MVP* (2026-05-14)

Engineering discipline at the MVP stage is non-negotiable: Claude Code + CLAUDE.md project-memory files + Multi-Agent Team pattern (separate agents for UI / backend / QA).

**Memories.ai implication**: Memories.ai implication: internally we're already using CLAUDE.md (the 4000-word context at the top of this very conversation). This is Anthropic's officially recommended practice — we can formalize it as an engineering standard.

[Source](https://claude.com/blog/the-founders-playbook)

---

### Anthropic Team — Anthropic · *Founder's Playbook — MVP* (2026-05-14)

Tech-debt defense has to start in the MVP stage — don't wait until Scale. AI-generated code accumulates debt fast.

**Memories.ai implication**: Memories.ai implication: Lucy Desktop's /api/proxy/memories/* BFF layer is the textbook case of not defending against debt in MVP — now it's wedged in the middle. New companies need to set architecture red lines on day one.

[Source](https://claude.com/blog/the-founders-playbook)

---

### Anthropic Team — Anthropic · *Founder's Playbook — Scale Stage* (2026-05-14)

The essence of the scale phase: build a repeatable "agentic operating system" — not hiring, but templated workflows.

**Memories.ai implication**: Memories.ai implication: Platformizing Memories.ai = templating internal workflows and exposing them externally. That's the same thing as "building a public API," just stated differently.

[Source](https://claude.com/blog/the-founders-playbook)

---

## ★★ (16 entries)

### Guigu101 — NVIDIA GTC 2025 · *硅谷101* (2025)

NVIDIA's second moat = NVLink Scale Up + Spectrum-X Scale Out dual narrative + Dynamo as the "AI factory OS."

**Memories.ai implication**: Memories.ai implication: our Temporal workflow is essentially "the OS of the memory factory." That metaphor should be used to name the top layer of the public API.

[Source](https://www.bilibili.com/video/BV1uNZMYREpE/)

---

### Guigu101 — NVIDIA · *硅谷101* (2025)

A 100MW AI factory: Hopper needs 45,000 chips / 1,400 racks; Blackwell is substantially better — hardware generation directly determines economics.

**Memories.ai implication**: Memories.ai implication: personal memory indexing has the same "generation gap" concept — pgvector vs. dedicated vector hardware. Which path we pick determines the long-term API price.

[Source](https://www.bilibili.com/video/BV1uNZMYREpE/)

---

### Fu Sheng — Orion Star (Lieyao Xingkong) · *Finance Interview* (2025-03)

"The real moat for large models comes from data"; the best entry is "high-quality data + agent framework."

[Source](https://finance.sina.com.cn/stock/t/2026-01-20/doc-inhhyski6902733.shtml)

---

### Jiang Daxin — StepFun (Jieyue Xingchen) · *Sina Tech* (2025-05-09)

22 foundation models in 2 years, 70% multimodal; co-developing with multiple domestic Chinese chip makers.

[Source](https://finance.sina.com.cn/tech/roll/2025-05-09/doc-inevysvt8396575.shtml)

---

### Zhang Xiangyu — StepFun (Jieyue Xingchen) · *Zhang Xiaojun EP102* (2025-08)

Multimodal reasoning must move toward visual chain-of-thought reasoning — not "caption the video and dump it into an LLM."

**Memories.ai implication**: Memories.ai implication: internally we have the ILM/VLM foundation, but the public API only exposes chat completion — visual intermediate representations should be opened up.

[Source](https://zhuanlan.zhihu.com/p/1913994932059895271)

---

### He Xiaopeng — XPeng Motors · *Luo Yonghao's Crossroads EP2* (2025-08-26)

Fatal executive mistake: once the company is big, wanting to "find a bunch of smart people to do it for me" — and ending up "the last person in the entire company to know what's actually going on."

**Memories.ai implication**: Memories.ai implication: Execs can't detach from the public API + customer feedback front line.

[Source](https://finance.sina.com.cn/tech/csj/2025-08-27/doc-infnkyfm9223501.shtml)

---

### Boris Cherny — Anthropic (Claude Code) · *Lenny's Podcast* (2026)

"Underfunding teams and giving them unlimited tokens leads to better AI products" — keep org headcount tight, be generous with compute. Claude Code now accounts for 4% of public GitHub commits; DAU doubled last month.

**Memories.ai implication**: Memories.ai implication: the opposite of our current practice — teams should be small, but compute / API calls should be unlimited.

[Source](https://www.lennysnewsletter.com/p/head-of-claude-code-what-happens)

---

### Dmitri Dolgov — Waymo · *Sequoia Founder Spotlight* (2026)

"Waymo Foundation Model" = driver + simulator + critic, three pillars sharing the same base. A multimodal world-action-language model — 3D spatial physics + behavior prediction + general world knowledge aligned (from VLM).

**Memories.ai implication**: Memories.ai implication: consider a single "Memory Foundation Model" that serves search, generation (recap), and critic (accuracy assessment) — instead of separate models per product.

[Source](https://www.youtube.com/watch?v=I_0Kuf6Aa2c)

---

### Dick Costolo — Twitter (ex-CEO) · *Sequoia Training Data* (2026)

The Steve Jobs / Pixar trick: every Friday the CEO sits with the team's ICs alone, manager not in the room. "What's not working at Pixar? What is working?" Take notes; talk to the manager Monday. The gap between team and leadership perception is exposed instantly.

**Memories.ai implication**: Memories.ai implication: Memories.ai infrastructure / Lucy teams should try it — skip the mid-level manager and listen to ICs directly.

[Source](https://www.youtube.com/watch?v=Kw5hhIsw-wQ)

---

### Dick Costolo — Twitter (ex-CEO) · *Sequoia Training Data* (2026)

"Many CEOs raise too much money, then stop worrying about operating efficiency." A $100M Series B is the new $20M B — lots of companies burn out of control because there's too much cash for anyone to watch it.

**Memories.ai implication**: Memories.ai implication: on fundraising — right now, raising too much is the actual risk.

[Source](https://www.youtube.com/watch?v=Kw5hhIsw-wQ)

---

### Zhang Peng — Zhipu AI · *Zhang Xiaojun Business Interview Podcast2026第一集* (2026-01)

From perception to cognition: a full retrospective of the 2023–2025 paradigm shift + the 2025 lesson of learning from DeepSeek.

[Source](https://www.xiaoyuzhoufm.com/podcast/626b46ea9cbbf0451cf5a962)

---

### Demis Hassabis — Google DeepMind · *CNBC Tech Download* (2026-01-15)

Talks with Sundar Pichai "every day" — DeepMind = Google's "engine room." In a "ferocious competitive environment," structure is adjusted to ship products fast.

[Source](https://www.cnbc.com/2026/01/16/deepmind-google-ai-competition-demis-hassabis.html)

---

### Sergey Levine — Physical Intelligence · *Invest Like the Best* (2026-03)

A general-purpose robotic foundation model beats narrow-domain solutions — analogous to how the PC unlocked the software application explosion.

**Memories.ai implication**: Memories.ai implication: same logic — "general-purpose video foundation model > narrow-domain." Don't split products by "meeting video / family video."

[Source](https://barbellinsights.com/podcast/invest-like-the-best-with-patrick-o-shaughnessy/sergey-levine-building-llms-for-the-physical-world-invest-like-the-best-ep-465)

---

### Sergey Levine — Physical Intelligence · *Invest Like the Best* (2026-03)

Vision-language-action as one — pure vision or pure language alone is not enough; you need a closed loop with action.

**Memories.ai implication**: Memories.ai implication: extend "video understanding" to "video understanding + decision + triggering external actions" (Calendar / Slack / Notion).

[Source](https://barbellinsights.com/podcast/invest-like-the-best-with-patrick-o-shaughnessy/sergey-levine-building-llms-for-the-physical-world-invest-like-the-best-ep-465)

---

### Wang Xing / Wang Huiwen — Meituan · *Meituan Internal 2025 Postmortem* (2026-Q1)

"Results-oriented" gets abused — business units inflate merchant costs for short-term KPIs, AI coding teams quietly fork open source and "file off the serial numbers." New metrics shift to user satisfaction / effective output / real ROI.

[Source](https://m.thepaper.cn/newsDetail_forward_32870208)

---

### Wang Xing / Wang Huiwen — Meituan · *Meituan Internal 2025 Postmortem* (2026-Q1)

Cultural reset: Wang Xing's "let's cut the formality — starting with me," employees address him by first name.

[Source](https://m.thepaper.cn/newsDetail_forward_32870208)

---

← [Topic index](./README.md) · [→ KB home](../README.md)