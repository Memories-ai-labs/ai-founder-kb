# Project Glasswing: An Initial Update
# URL: https://www.anthropic.com/research/glasswing-initial-update
# Date: 2026-05-22
# source: Anthropic Research Blog

Last month, Anthropic launched Project Glasswing, a collaborative initiative designed to identify critical vulnerabilities in essential software before advanced AI systems could potentially exploit them. Within the first month, approximately 50 partners discovered over 10,000 high- or critical-severity vulnerabilities using Claude Mythos Preview.

The core challenge revealed by this effort is a timing mismatch: finding vulnerabilities has become dramatically faster with AI assistance, but the processes for verifying, disclosing, and patching them remain slow and resource-intensive.

## Early Results

Partners reported significant findings. Cloudflare identified 2,000 bugs across critical systems, with 400 classified as high- or critical-severity. Mozilla discovered 271 vulnerabilities in Firefox 150—more than ten times their findings in an earlier version using a previous Claude model.

External evaluations confirmed Mythos Preview's capabilities. The UK's AI Security Institute reported it as "the first model to solve both of their cyber ranges end to end." XBOW described it as "a significant step up over all existing models" on exploit benchmarks.

## Open-Source Software Scanning

Anthropic scanned over 1,000 open-source projects and identified approximately 6,202 high- or critical-severity vulnerabilities. Of 1,752 vulnerabilities assessed by independent security firms, 90.6% proved valid, with 62.4% confirmed as high- or critical-severity.

An illustrative example: Mythos Preview detected a vulnerability in wolfSSL, an open-source cryptography library used by billions of devices worldwide. The model "constructed an exploit that would let an attacker forge certificates" potentially enabling fraudulent websites.

## The Disclosure Challenge

The software industry follows a 90-day coordinated disclosure standard. However, the volume of AI-discovered vulnerabilities now exceeds human capacity for triage and patching. Several open-source maintainers reported being "severely capacity constrained" and requested slower disclosure rates to manage workloads.

Anthropic reported 530 high- or critical-severity bugs to maintainers, with only 75 patched and 65 receiving public advisories. This reflects the genuine bottleneck: finding vulnerabilities is straightforward; fixing them requires sustained human effort.

## Adaptations for Defenders

**For developers:** Shorten patch cycles and make security fixes available rapidly. Use publicly available AI models to accelerate development processes.

**For network defenders:** Reduce patch testing and deployment timelines. Implement foundational controls like hardened configurations, multi-factor authentication, and comprehensive logging.

## Available Tools

Anthropic released Claude Security in public beta for Enterprise customers, enabling vulnerability scanning and fix generation. In three weeks, Claude Opus 4.7 helped patch over 2,100 vulnerabilities — faster than open-source patching because organizations fix their own code rather than coordinating with volunteer maintainers.

The company also established a Cyber Verification Program allowing security professionals to use Claude for legitimate cybersecurity purposes without certain safety restrictions.

## Ecosystem Support

Anthropic partnered with the Open Source Security Foundation's Alpha-Omega project to help maintainers process bug reports. The company also supported development of ExploitBench and ExploitGym — benchmarks for tracking frontier AI exploit capabilities.

## Future Direction

Mythos-class models remain unreleased publicly. Anthropic states that "no company — including Anthropic — has developed safeguards strong enough to prevent such models from being misused." Project Glasswing provides critical infrastructure defenders with early access while safeguards develop.

The organization plans to expand partnerships with additional organizations and governments, and eventually release Mythos-class models once stronger safeguards are implemented. The underlying goal: creating a future where "important code is hardened far better than it is today, and in which hacking is far less prevalent."
