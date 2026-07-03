# More details on Fable 5's cyber safeguards and our jailbreak framework
**Source:** Anthropic
**URL:** https://www.anthropic.com/news/fable-safeguards-jailbreak-framework
**Date:** 2026-07-02
**Category:** Announcements / Safety

---

## Summary

Anthropic published detailed documentation of Fable 5's cybersecurity safeguards alongside an early draft of an industry-wide jailbreak severity scoring framework, co-developed with Amazon, Microsoft, Google, and other Glasswing partners.

## Cyber Safeguards: Four-Tier Request Classification

Anthropic implements safety classifiers that categorize cybersecurity requests into four tiers:

**Prohibited Use** — activities with minimal defensive utility and high harm potential:
- Ransomware development
- Malware creation
- Defense evasion techniques
- Data exfiltration tools
All blocked.

**High-Risk Dual Use** — legitimate security work (pen testing, exploit development) that also enables attacks. Blocked pending better access controls for verified professionals.

**Low-Risk Dual Use** — vulnerability identification, OSINT. Tilted toward defense; most allowed, some blocked as safety margin.

**Benign Use** — secure coding, patch management, incident response. Rarely blocked (only false positives).

## Cyber Jailbreak Severity (CJS) Framework

Anthropic proposes a 0–4 severity scale measuring real-world risk across four axes:

- **Capability Gain:** How far the jailbreak advances attacker capabilities beyond existing tools
- **Breadth of Capability Gain:** How many distinct offensive tasks the technique enables
- **Ease of Weaponization:** Effort required to convert jailbreak into operational attacks
- **Discoverability:** How readily threat actors can find the technique

**Bands:**
- CJS-0: Informational
- CJS-1: Low
- CJS-2: Medium
- CJS-3: High
- CJS-4: Critical

Note: capability gain is time-dependent — vulnerabilities disclosed years ago score zero uplift today.

## Implementation

- HackerOne bug bounty program for jailbreak discovery
- Community feedback: cyber-safeguards@anthropic.com
- Framework includes hypothetical and historical examples for calibration

## Significance for Founders

This is the first public AI lab-led effort to create a shared severity taxonomy for jailbreak risks — analogous to CVSS for traditional security vulnerabilities. If adopted industry-wide, this creates a common language for AI security teams, insurers, and regulators. Founders building security-adjacent AI products should track this framework.
