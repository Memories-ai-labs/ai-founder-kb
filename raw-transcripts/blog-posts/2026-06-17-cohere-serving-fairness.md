# LLM Serving Fairness: No More Noisy Neighbours
# Source: Cohere Blog
# URL: https://cohere.com/blog/serving-fairness
# Date: 2026-06-17
# Publisher: Cohere
# Authors: Manoj Govindassamy (Manager of Technical Staff, External Serving), Musa Talluzi (Member of Technical Staff)

---

Running large language models as a multi-tenant SaaS platform creates a fairness challenge: multiple organizations share GPU resources, and their traffic patterns are unpredictable and uneven. Without proper management, "one customer's spike can become every other customer's latency problem."

## The Noisy Neighbor Problem

Inference operates most efficiently when requests are batched together on GPUs. However, this creates a fairness problem in shared environments. When a single organization submits thousands of requests while another sends just a few, the large burst can dominate the queue, causing significant delays for other tenants.

## The Solution: Four Layered Mechanisms

### 1. Rate Limiter
Admission control caps the maximum number of requests a tenant can submit within specified timeframes. The system also performs real-time throttling — if the queue cannot serve a request within its latency target, the request is rejected early rather than accepted and delayed.

### 2. Performance Tier
Compute resources are allocated based on service-level agreements. Higher-paying tiers receive greater priority and faster queue handling.

### 3. Deficit Round Robin (DRR)
Each tenant receives its own queue; the scheduler rotates between them granting each a small budget per turn. "Cheap requests let a tenant come up more often, and expensive ones less, so no tenant can run away with the GPU."

Two cost models:
- **Request-based budgeting**: Each request costs 1 unit regardless of size (best for generative endpoints)
- **Token-based budgeting**: Requests charged by token count (optimal for embeddings and rerankers)

### 4. Priority
Within each tenant's fair allocation, requests are ordered by priority level, deadline, and arrival time.

## Availability

Serving Fairness is now enabled for all customers using Cohere models through the SaaS API and third-party marketplace deployments including AWS.
