# OpenAI and Cisco introduce Shirudo
# URL: https://openai.com/index/introducing-shirudo/
# Date: 2026-11-23
# Source: OpenAI Blog

**OpenAI and Cisco introduce Shirudo**
Date: November 23, 2026
Category: Security | Partnerships

OpenAI and Cisco have released Shirudo, an open-source runtime that helps operators protect running Linux systems while a permanent patch is being prepared.

## The Problem

Patching can take days or weeks. Traditional approaches to blocking an exploit's Linux operation can also inadvertently block legitimate traffic and take a service offline.

## The Approach

Teams create temporary safeguards called "shields." Operators can test a shield, approve it, and deploy it without restarting the service.

## How It Works

Shirudo uses eBPF (extended Berkeley Packet Filter), a Linux technology that runs small programs inside the operating system to observe activity and apply targeted protections.

## Core Capabilities

- **Live protection**: Guards running services without requiring a restart
- **Machine-speed defense**: Agent-driven tools with security teams controlling deployment
- **Trusted deployment**: Cryptographic signing and verification of shields
- **Hardware-backed verification**: Uses a Trusted Platform Module (TPM)

## Example

In a controlled test, a Codex-generated shield blocked a Java4Shell exploit against a running Elasticsearch service without a restart.

## Long-term Goals

- Hardening the kernel and core services
- Limiting workload permissions
- Making updates and recovery safer

## Open Source

Shirudo is licensed under BSD 2-Clause, with its BPF programs dual-licensed under BSD and GPL. Available on GitHub.
An online developer webinar is scheduled for December 15.

## Signal for Founders

Security tooling for AI-deployed systems is becoming a first-class product category. OpenAI and Cisco partnering on open-source runtime security signals that AI labs are taking production infrastructure security seriously, and that there's a growing opportunity for startups that can integrate with AI-generated protective capabilities.
