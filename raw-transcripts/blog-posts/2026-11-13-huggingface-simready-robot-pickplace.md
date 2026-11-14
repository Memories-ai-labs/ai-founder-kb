# Build a Robot Pick-and-Place Simulation with SimReady Assets
# URL: https://huggingface.co/blog/nvidia/simready-assets-robot-pick-and-place
# Date: 2026-11-13
# Source: Hugging Face Blog (NVIDIA)

A tutorial on building a robot pick-and-place simulation in NVIDIA Isaac Sim using SimReady assets from SimReady Central. The setup combines a UR17G arm, a Robotiq 2F-140 gripper, and a beverage can as the target object. An AI agent generates the task controls; the author walks through joint-limit checks, gripper movement, and can-grasp validation. Notes the limits of scripted simulation setups vs. reinforcement-learning-based approaches, and links to resources for custom SimReady-based simulations.

**Key takeaways for founders:**
- Synthetic data and simulation pipelines are becoming accessible enough for smaller teams to prototype physical AI applications.
- The Sim-to-Real gap is being attacked via standardized asset formats (SimReady) rather than purely algorithmic advances.
- NVIDIA's ecosystem lock-in strategy runs through open simulation tooling (Isaac Sim) and asset marketplaces.
