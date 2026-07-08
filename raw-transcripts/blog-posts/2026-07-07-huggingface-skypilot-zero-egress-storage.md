# Run AI workloads on any cloud, store on Hugging Face: zero-egress storage with SkyPilot

**Publisher:** Hugging Face / SkyPilot
**Date:** 2026-07-07
**URL:** https://huggingface.co/blog/skypilot-hf-storage
**Authors:** Nikhil Jha, Zhanghao Wu, Hope Wang, Adrien Carreira, Julien Chaumond

---

Announces the integration of Hugging Face Storage as a first-class backend for SkyPilot, enabling users to run compute across multiple cloud providers while maintaining centralized data storage without incurring egress fees.

## Primary innovations

- The `hf://` URL scheme allows mounting Hugging Face Buckets and Hub repositories into SkyPilot tasks
- Mount models and datasets as read-only resources; write checkpoints to buckets using a single authentication token
- Leverages lazy-loading via FUSE — a process can start working through a large file before the whole file has downloaded

## Key advantage

Eliminates vendor lock-in by decoupling storage location from compute location. Teams no longer need to maintain separate data copies across cloud providers or pay cross-cloud transfer costs, since "Hugging Face charges no egress, so reading your data onto those GPUs costs nothing, on any cloud."

## Deduplication

The Xet-backed storage system implements content-defined chunking — only modified data segments require upload during checkpoint saves or model variant creation.
