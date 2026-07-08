# Introducing Robostral Navigate

**Publisher:** Mistral AI
**Date:** 2026-07-07
**URL:** https://mistral.ai/news/robostral-navigate/
**Authors:** Théo Cachet, Arjun Majumdar, Srijan Mishra, Thomas Chabal, Chris Bamford, Elliot Chane-Sane, Benjamin Tibi, Ludovic Ho Fuh, Olivier Duchenne (AI Science Robotics team)

---

Mistral AI unveiled Robostral Navigate, an 8-billion parameter model designed for robotic navigation. The system uses only a single RGB camera to autonomously guide robots through complex indoor and outdoor environments using natural language instructions like "Leave the lobby, walk through the corridor, enter the supply room."

## Notable achievements

- Achieves 76.6% success rate on unseen R2R-CE benchmarks, surpassing multi-sensor approaches
- Built entirely in-house using simulation-trained data (~400,000 trajectories across 6,000 scenes)
- Employs pointing-based navigation combined with reinforcement learning
- Training efficiency improved through prefix-caching, reducing token requirements by 22×

The model generalizes across robot types and adapts to real-world obstacles not encountered during training, representing progress toward unified embodied AI capabilities.
