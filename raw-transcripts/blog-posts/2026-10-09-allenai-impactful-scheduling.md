# Impactful scheduling for GPU clusters
# URL: https://huggingface.co/blog/allenai/impactful-scheduling
# Date: 2026-10-09
# source: HuggingFace / Allen AI (Ai2)

Author: Kyle Wiggers (Ai2Comms)
Publisher: Hugging Face Blog (Allen Institute for AI)

---

Ai2's AI Infrastructure team replaced a priority-based GPU scheduler with a system built on GPU time budgets, hierarchical fair-share allocation, and a time-slicing "scheduling contract."

## Problem with the old scheduler

- Researchers parked idle "squatting" workloads
- Priority levels inflated until lower tiers were starved
- On-call engineers spent much of their time negotiating shutdowns of non-preemptible jobs

## New system design

**Budgets, not schedules:** Managers allocate shares of GPU time to programs, projects, and researchers. Work that isn't funded by a budget can be preempted, so gaming the scheduler draws from the user's own allocation.

**Fair-share:** The scheduler tracks usage over a sliding 7-day window and favors under-served allocations. Builds on existing approaches such as Hadoop's and SLURM's fair schedulers.

**Scheduling contract:** Workloads declare a minimum runtime (capped at 8 hours) during which they're protected from preemption. After that, they can be requeued. Unhealthy hosts can drain automatically.

**Simulations:** Before rollout, a simulator predicted large drops in debug-job wait times. Real results exceeded predictions.

## Results (30-day test period)

- Teams received 98% of the GPU hours they were owed
- Occupancy held at 98%, with demand running 2-3x capacity
- Debug-workload p90 queue wait: from ~2 hours → 30 seconds
- Repairs needing human intervention: dropped 74%

## Challenges and future work

- Interactive dev sessions suffered under the 8-hour protection cap → Ai2 plans a CPU-only cluster and restorable sessions
- Capacity fragmentation could delay the largest jobs — still under investigation
- Future work targets utilization, including checkpointing and training efficiency
