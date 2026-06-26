# How we contain Claude across products

Title: How we contain Claude across products
Author: Max McGuinness, Mikaela Grace, Jiri De Jonghe, Jake Eaton, Abel Ribbink
URL: https://www.anthropic.com/engineering/how-we-contain-claude
Date: 2026-05-25
Source: Anthropic Engineering Blog

---

As agents grow more capable, so does their potential blast radius. The engineering question is how to cap it. Here's what we've learned building containment for claude.ai, Claude Code, and Cowork.

Twelve months ago, we'd have rejected out of hand the idea of granting Claude access sufficient to take down an internal Anthropic service. Today that level of access is routine, and Anthropic developers are more productive for it. The risk of these deployments has two components: how likely a failure is, and how much damage one could do. Progress on safeguards and model training has steadily driven down the first; the second—the theoretical blast radius—only grows as capabilities and access expand. Yet as agents become capable of doing work that once required a person or even a team, the cost of _not_ deploying grows large enough that the risk-reward calculation tips heavily toward adoption, as long as products can be made safe. The engineering question becomes how to cap the blast radius.

When bounds can be placed on the relative damage of an autonomous agent—such as through control over its environment—high-utility capabilities can motivate deployment. Claude Mythos Preview is an example of a model whose blast radius was deemed too high to ship in April 2026. However, we expect broader release of models with similar levels of capability to become appropriate as defenders harden critical systems and safeguards mature—even though some risk will always remain. Model capability is an important factor in the total risk of an agent's deployment.

There are broadly two ways to do this.

The first is to supervise the agent's behavior via a human-in-the-loop. Claude Code previously protected against agents taking unintended actions by asking users for permission at each turn. Theoretically that works, but we've found the approach to be fallible. Our telemetry showed users approved roughly 93% of permission prompts. The more approvals a user sees, the less attention they pay to each, becoming over time much less diligent in their supervision. We recently built Claude Code auto mode, which automates safer approvals in order to reduce this approval fatigue. Still, vulnerabilities remain—any probabilistic defense has a non-zero miss rate.

The second approach to capping the blast radius—and the focus of much of this post—is containment. Rather than supervising what the agent does, we supervise what it's _able_ to do by enforcing access boundaries through, for example, sandboxes, virtual machines, and egress controls. This is where Anthropic engineering has devoted the most effort, and also where many of the most surprising security failures have occurred.

Over the past two years, we've shipped three primary agentic products: claude.ai, Claude Code, and Claude Cowork. Each serves a different audience, requiring a different containment architecture. This article shares what's held up, what's broken, and what we've learned about agent security along the way.

## Three types of risk, three components of defense

Security risks to agents fall into one of three categories:

**User misuse:** A user—either maliciously or through carelessness—directs the agent to do something harmful.

**Model misbehavior:** The agent takes a harmful action no one asked for. As our models have improved, they have become more aligned on most behavior evaluations, but this doesn't mean risk necessarily shrinks. Less capable models are more likely to misread a situation and make obvious errors. More capable models make fewer mistakes, but they're also better at finding unexpected paths to a goal, often by routing around restrictions nobody thought to write down.

At Anthropic, we've seen Claude models "helpfully" escape a sandbox in order to complete a task, examine git history to find answers to a coding test, and spontaneously identify the benchmark it was being run on in order to decrypt its answer key.

**External attackers:** The agent is attacked through external vectors such as tools, files, or network access.

When building containment and defense systems, we apply defenses to three main components:

**The environment in which the agent runs.** We constrain where and how an agent can act with process sandboxes, VMs, filesystem boundaries, and egress controls. A tight perimeter also means you can relax oversight. Claude Code's reference devcontainer exists precisely so that the agent can run unattended, without per-action approvals.

**The model the agent consults.** Mechanisms include system prompts, classifiers, probes, and training modifications. On Gray Swan's Agent Red Teaming benchmark, Claude Opus 4.7 holds attack success to roughly 0.1% on single attempts, and around 5–6% after 100 adaptive attempts. Claude Code auto mode catches roughly 83% of overeager behaviors before they execute.

**The external content the agent can reach.** MCP servers, third-party plugins, and web search tools all feed content into the agent's context from sources you don't control. An audited connector isn't the same as audited data—a GitHub connector, for instance, can load a poisoned README straight into the model's context despite passing malware checks.

## Patterns for containing agents

### Pattern 1: The ephemeral container (claude.ai code execution)

When Claude runs code inside claude.ai, it does so in a gVisor container on isolated infrastructure. The agent is entirely server-side; no code runs on the local machine, and the filesystem is ephemeral (per-session). The blast radius is minimal, but so is the ceiling on what Claude can do.

### Pattern 2: The human-in-the-loop sandbox (Claude Code)

Claude Code runs on a user's machine and has access to their filesystem, shell, and network. Claude Code launched with the simplest possible defense: allow reads, require approval for write, bash, and network access. Approval fatigue showed up within weeks—telemetry showed users approved roughly 93% of prompts.

An OS-level sandbox (Seatbelt on macOS, bubblewrap on Linux) was added: reads allowed, writes allowed inside the workspace, network denied by default. Result: 84% reduction in permission prompts. The runtime was open-sourced.

**Risk we missed: Everything before the trust dialog**
Between mid-2025 and January 2026, three vulnerabilities targeted code executing before the user consented. A developer clones a repository containing a .claude/settings.json which defines a hook—because Claude Code reads project settings during startup before presenting the "Do you trust this folder?" prompt, the attacker's hook executes automatically. Fix: defer parsing and execution of project-local configuration until after the user accepts the trust prompt.

**Risk we missed: The user as an injection vector**
In February 2026, during a controlled red-team exercise, a researcher successfully phished an employee into launching Claude Code with a malicious prompt. Across 25 retries, Claude completed the credential exfiltration 24 times. The only defense that holds: egress controls that block the POST regardless of intent.

### Pattern 3: The local VM (Claude Cowork)

Claude Cowork runs inside a full virtual machine (Apple's Virtualization framework on macOS, HCS on Windows). The VM has its own Linux kernel, filesystem, and process table. Credentials stay in the host's keychain and never enter the guest machine.

**Risk we missed: Exfiltration through an approved domain**
A malicious file in the user's workspace carried hidden instructions along with an API key controlled by an attacker. Claude read workspace files and called Anthropic's Files API using the attacker's key. The egress proxy saw api.anthropic.com and let it through. Fix: a defensive man-in-the-middle proxy inside the VM that only passes requests carrying the VM's own provisioned session token.

**Risk we missed: VM isolation kept endpoint detection software out**
The same isolation keeping Claude contained also kept host-based EDR out. Current mitigation: pull-based OTLP exports for after-the-fact event log retrieval.

## Trusting what the agent reads

**Remote versus local is more important than it seems.** A locally installed tool is auditable. A remote tool—a hosted MCP server, a cloud connector—can change behavior at any point after approval; your install-time trust decision may no longer apply.

**Tool output is an attack surface even when the tool is trusted.** Any input scanning applied to web pages needs to be applied to network-enabled tool results with the same rigor.

## Looking ahead

**Persistent memory poisoning.** As more agent state survives the session (product memory, CLAUDE.md files, mounted workspaces, scheduled agent state directories), injections that land in these are reloaded each time the agent starts.

**Multi-agent trust escalation.** If a sub-agent's output is treated as higher-trust than raw tool results, a new vector for prompt injection is introduced.

**Agent identity.** Should an agent possess its own principal identity, or act as an extension of the user? The answer may be a blend of the two.

## Summary — Core Principles

1. **Design for containment at the environment layer first, then steer behavior at the model layer.** The deterministic boundary is what gets hit when everything probabilistic misses.

2. **Match isolation strength to the user's capacity for oversight.** A developer who can read bash and a knowledge worker who can't are not running the same threat model.

3. **Be wary of custom components.** Battle-tested hypervisors, syscall filters, and container runtimes have survived more adversarial attention than anything you'll build. Across every deployment described here, the standard primitives held while our own work around them exposed flaws.

## Acknowledgements

Written by Max McGuinness, Mikaela Grace, Jiri De Jonghe, Jake Eaton, and Abel Ribbink. Special thanks to Anthropic security and product engineering teams.
