# P0 Actions

**8 items**

---

## 1. Promote `/api/v2/luci-memory/personal/*` and `/api/v2/luci-memory/portrait/*` to public Mintlify docs

**Theme**: Strategy / Product  
**Time window**: < 30 days

**Evidence / pattern**: Directly addresses the "hidden internal capabilities = failure" pattern. Controllers already exist — pure docs work. CLAUDE.md P0 already flagged.

---

## 2. Shawn does podcasts: Latent Space, Dwarkesh, Zhang Xiaojun first

**Theme**: Strategy  
**Time window**: < 30 days — send booking emails

**Evidence / pattern**: Long-form is the de facto founder-distribution path. Content output first, then product iteration.

---

## 3. Fix `list_unique_ids` with pagination (prerequisite for external multi-tenancy)

**Theme**: Engineering & Management  
**Time window**: < 14 days

**Evidence / pattern**: Empirically confirmed in this session: 133KB returned in a single call — will explode for any active tenant.

---

## 4. Convert internal customer support + sales to Claude agents (dogfood experiment)

**Theme**: Product / Engineering & Management  
**Time window**: < 30 days — single squad leads

**Evidence / pattern**: Validated by both Anthropic Playbook and OpenAI DevDay (help.openai.com runs on AgentKit): dogfooding is the only real API test.

---

## 5. Write Memories.ai cultural values doc + integrate into interviews

**Theme**: Hiring  
**Time window**: < 14 days — Shawn drafts personally

**Evidence / pattern**: Daniela Amodei: not subjective culture-fit preference — write explicit cultural values, then evaluate objectively.

---

## 6. Find 10 external candidate developers to act as design partners (Anthropic Idea-stage exit criteria)

**Theme**: Product  
**Time window**: < 30 days

**Evidence / pattern**: Anthropic Idea-stage exit criteria: 10 paying-intent users + 3 articulated differentiators + 20 raw user interview transcripts.

---

## 7. Run Brad Jacobs's "A-player test" on every core IC (would you panic if they quit?)

**Theme**: Hiring  
**Time window**: < 30 days — do not tell employees

**Evidence / pattern**: Founders Podcast (Brad Jacobs). 3-month retain plan for barrels; reassess role for non-barrels.

---

## 8. Issue sub-user keys to external dogfooders (isolate from admin-tenant key)

**Theme**: Engineering & Management  
**Time window**: < 14 days

**Evidence / pattern**: Empirically confirmed in this session: admin key shows a completely different view than what external developers see. Multi-tenant + sub-key is a Phase 2b prerequisite.

---

← [Actions index](./README.md) · [→ KB home](../README.md)