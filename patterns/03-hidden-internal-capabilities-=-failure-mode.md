# #03 — Hidden Internal Capabilities = Failure Mode

## One-Line Summary

Capability ≠ product. Capabilities must be exposed in callable / observable / distributable form. OpenAI's o1 hiding its reasoning lost differentiation vs DeepSeek showing thought traces; Yao Shunyu states bluntly that interface design is the biggest startup opportunity; Ren Xin says "senior engineers are the ones best at designing fences."

## Supporting Evidence (Independent Sources)

Xiao Hong on Manus / BAAI interview (OpenAI o1 vs DeepSeek) / Yao Shunyu on Zhang Xiaojun EP115 / Ren Xin on AI Alchemy Podcast ("senior engineers design fences") / Lucy's own situation (Lucy team doesn't use the public API) / Memories.ai's current state (87 internal Luci endpoints, all hidden)

## Action Implication for Memories.ai

P0: Promote `/api/v2/luci-memory/personal/*` and `/api/v2/luci-memory/portrait/*` to Mintlify docs (controllers already exist, no backend work). Add user-facing progress visibility for video "smart segmentation" and portrait extraction.

---

← [Patterns index](./README.md) · [→ KB home](../README.md)