# FINAL-Bench Quantum: An Open, Neutral Benchmark for Quantum-Computing Methods

**Source**: HuggingFace Blog (Community Article)
**Date**: 2026-06-14
**URL**: https://huggingface.co/blog/FINAL-Bench/quantum-leaderboard
**Author**: FINAL-Bench (SeaWolf-AI/VIDRAFT_LAB)

---

## Full Article

Comparing quantum-computing results proves challenging since identical metrics like "logical error rate" or "query fidelity" can signify vastly different things depending on implementation specifics. FINAL-Bench Quantum introduces "a suite where methods compete in five events under identical, published protocols" with clearly labeled measurements and sourced citations.

**Leaderboard Location:** huggingface.co/spaces/FINAL-Bench/quantum-bench-leaderboard

### The Core Rule — Two Tracks

The benchmark operates under two distinct tracks:

- **Track A (Verified):** Methods undergo measurement on a single, frozen public test set with 95% confidence intervals reported. These figures remain directly comparable.
- **Track B (Reported):** Numbers sourced from published papers and announcements. Since "codes, noise models, and hardware differ," these measurements lack direct comparability.

Two governing principles:
1. No quantum-advantage claims
2. Simulations are explicitly labeled; real hardware identifies the specific chip

When results overlap statistically, they constitute a tie rather than determining a winner.

### The Five Events

| Event | Measurement | Analogy |
|-------|------------|---------|
| ① QEC Decoder | Logical error rate on rotated surface code | Quantum "spell-checker" accuracy |
| ② Optimization | Max-Cut quality ratio | Finding optimal solutions among vast possibilities |
| ③ VQE | Molecular ground-state energy accuracy | Quantum chemistry calculations |
| ④ QRAM | Quantum-memory query fidelity | Quantum "memory chip" accuracy |
| ⑤ Simulation | Classical method circuit-handling capacity | Emulating quantum computers classically |

Each event includes verified measurements, hardware results, published references, charts, medal participation data, and methodology information.

### How to Submit

The submission process requires method names, links (GitHub/Hugging Face), email, and optional results files. Submissions remain private, undergo reproduction under fixed protocols, and creators receive notification about inclusion.

### Why Neutrality Matters

The benchmark's credibility depends on disciplined inclusion of "strong competitors even when they beat the host's own entries," faithful source attribution, and honest measurement boundaries. Entries from Google, IBM, NVIDIA, USTC, Riverlane, and a Korean team (VIDRAFT) compete under identical standards.

Since quantum computing hasn't achieved fault-tolerance, "a shared, hype-free yardstick that honestly records what has actually been measured today" remains essential for progress.
