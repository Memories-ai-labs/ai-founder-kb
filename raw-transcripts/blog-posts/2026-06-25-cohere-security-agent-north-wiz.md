# Creating a security agent with Cohere North and Wiz
# URL: https://cohere.com/blog/cohere-security-ai-agent-north-wiz
# Date: 2026-06-25
# Source: Cohere Blog

**Author:** Bolaji Agunbiade, Member of Technical Staff, Security  
**Reading Time:** 8 minutes

---

## The Challenge

Cohere's security team faced a bottleneck in incident response workflows. Processing critical security findings from Wiz required manual steps consuming 30 minutes to 2 hours per alert, including investigation, ticket creation, report drafting, and status updates. This manual triage became unsustainable as their cloud infrastructure expanded.

## The Solution

The team developed an automated incident response system by integrating Cohere North with Wiz through a custom Model Context Protocol (MCP) server. The architecture flows as: North (agent platform) → Custom MCP server → Wiz GraphQL API.

## Eight Core Tools

The MCP server exposed Wiz's capabilities through atomic functions:
- Issue listing and filtering
- Detailed finding retrieval
- Toxic combination identification (multi-factor attack paths)
- Vulnerability searches with CVE data
- Security posture snapshots
- Cloud asset queries
- Compliance status reporting
- Issue status updates

## Three Key Use Cases

**1. Toxic Combination Analysis:** North evaluates critical multi-factor attack paths, ranking them by blast radius while factoring internet exposure, privilege levels, and data sensitivity.

**2. Assisted Incident Response:** The agent retrieves critical findings, searches for existing tickets, creates new ones in Linear, generates structured IR reports, and updates Wiz status — all from a single prompt.

**3. Autonomous Weekly Posture Brief:** A scheduled automation runs Monday mornings, producing security reports covering metrics, top issues, toxic combinations, and actively exploited CVEs without manual intervention.

## Technical Architecture

- North authenticates to the MCP server via shared secret headers
- The server uses OAuth2 client credentials for secure Wiz authentication
- Service account tokens remain server-side
- Tools designed for atomic, fault-tolerant operations

## Key Technical Lessons

- Critical instructions should appear at the top of system prompts rather than distributed throughout
- Tool design must account for actual API behavior, not just documentation
- Write operations require fault tolerance for partial failures
- Limit hallucinations by distinguishing finding types (configuration vs. vulnerability)
- Exact Wiz field values prevent name inference errors

## Implementation Results

The automation eliminated first-pass triage, shifting human effort from reading alerts to evaluating agent assessments. Weekly posture briefs now deliver consistent visibility without manual labor.

## Key Quote

> "North's MCP-native architecture provided the leverage we needed: build the Wiz integration once and expose it across all workflows."
