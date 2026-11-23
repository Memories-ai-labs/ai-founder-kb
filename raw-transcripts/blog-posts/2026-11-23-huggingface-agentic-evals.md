# How to build and maintain an agentic evaluation
# URL: https://huggingface.co/blog/agentic-evals
# Date: 2026-11-23
# Source: Hugging Face Blog
# Authors: Avijit Ghosh (evijit), Ben Burtenshaw (burtenshaw), Irene Solaiman (irenesolaiman)

## Summary

Practical guide to building and maintaining agentic evaluations — evaluations that score what an AI agent changes in an environment, rather than just its text outputs. The authors argue that many factors (agent harness, environment, grader) can shift scores substantially, and recommend reusing open infrastructure so effort goes into domain expertise and validation.

## Key Points

**The core challenge:** Agentic evals score environmental changes, not text. This means the agent harness, environment setup, and grader all affect scores independently of model capability — creating noise that makes cross-model comparison hard.

**Recommended approach (8 steps):**
1. Define the specific capability claim being tested
2. Find an existing starting task (don't reinvent)
3. Run the task unchanged first to establish baseline
4. Adapt the task to your domain
5. Check evaluation validity (can the grader be gamed?)
6. Read the traces (understand what the agent actually did)
7. Report the score with full context
8. Compare models systematically

**Key warning — shortcut vulnerability:** A worked example using a physics-lab Raman spectra task showed that a shortcut script passed the original grader by returning the correct defect ratio without actually fitting the data. This led to stronger checks on the fitting process itself — illustrating that graders must test the process, not just the final answer.

**Open infrastructure recommended:**
- Harbor: agent harness framework
- Terminal-Bench: benchmarking suite
- Reusing these allows teams to focus on domain expertise and task curation

**Benchmark hygiene:**
- Public review has exposed flaws in many benchmarks
- Document corrections with affected version numbers
- Contamination vs. saturation are distinct problems — hiding test data alone doesn't prevent saturation
- Expert curation and larger test sets correlate with lower saturation

**Selective openness framework:** A table maps each evaluation component to what can be published vs. protected:
- Tasks, environments, verifiers: publishable
- Traces, results: publishable
- Some test data: controlled review only

## Significance for AI Founders

Practical, evidence-based guidance for teams building AI products that use agents. The emphasis on reusing open infrastructure and the shortcut-vulnerability example are directly applicable to any team building internal evals for coding agents, customer service agents, or workflow automation.
