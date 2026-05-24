# P1 Actions

**10 items**

---

## 1. Public release of `/api/v2/lifelog/*` + `/api/v2/recap/*` + `/api/v2/capture/*` endpoints

**Theme**: Strategy / Product  
**Time window**: 60-90 days

**Evidence / pattern**: Tagged P1 in CLAUDE.md. Lucy has validated product value — exposing publicly lets external devs build personal-AI assistant apps.

---

## 2. Ship TS + Python SDKs with SSE/polling/async fully wrapped

**Theme**: Product  
**Time window**: 60-90 days

**Evidence / pattern**: CLAUDE.md P2 promoted to P1. A unified SDK gets Lucy and external developers using the same API surface.

---

## 3. Multi-tenancy: org → project → sub-user hierarchy with per-sub-user API keys

**Theme**: Engineering & Management  
**Time window**: 60 days

**Evidence / pattern**: Tagged P2 in CLAUDE.md. ServeInterceptor.java already supports org→user; add a project layer.

---

## 4. MCP server — expose portrait/memory queries to Claude / ChatGPT / Cursor

**Theme**: Strategy / Product  
**Time window**: 60-90 days

**Evidence / pattern**: OpenAI DevDay confirms MCP is an open protocol. Lets Memories.ai memory become a layer callable by external super-apps.

---

## 5. Pricing redesign: per-result + per-agent-run + tiered + cost calculator

**Theme**: Strategy / Product  
**Time window**: 90 days

**Evidence / pattern**: Current token-based pricing doesn't reflect the heterogeneous value of memory queries (Dario). Replit / Crosby / Benioff all validate that pricing is a product signal.

---

## 6. Generous free tier (enough to build a full demo, not a 30-day trial)

**Theme**: Product  
**Time window**: 60 days

**Evidence / pattern**: Both Elena Verna on Lenny's and Grant Lee (Gamma) confirm: free tier > paid ads.

---

## 7. Formalize CLAUDE.md project memory + Multi-Agent Team workflow across all engineering

**Theme**: Engineering & Management  
**Time window**: 60 days

**Evidence / pattern**: Anthropic Founder Playbook officially recommends this pattern. This conversation's CLAUDE.md is already a working prototype.

---

## 8. "11-star Lucy experience" design sprint (Brian Chesky's back-into-PMF method)

**Theme**: Product  
**Time window**: 90-day sprint

**Evidence / pattern**: Write out what an 11-star Lucy experience would be — e.g., "Lucy already knows what you want to find and has it edited." Reverse-engineer from there to current 5 stars.

---

## 9. Webhook + HMAC signing + retry (InfraCallbackController is currently unprotected)

**Theme**: Engineering & Management  
**Time window**: 60 days

**Evidence / pattern**: Tagged P3 in CLAUDE.md. Event reliability is a prerequisite for external devs to build businesses on top.

---

## 10. Bottom-up GTM experiments: 1-2 hackathons + open-source SDK example repo

**Theme**: Strategy  
**Time window**: 90 days (one hackathon in Q3)

**Evidence / pattern**: n8n / Replit / Cohere all confirm: enterprise-first is an anti-pattern in the AI era.

---

← [Actions index](./README.md) · [→ KB home](../README.md)