# Microduck Obstacle Avoidance: A Sim2Real Workflow with Isaac Lab and Newton
# URL: https://huggingface.co/blog/nvidia/microduck-obstacle-avoidance
# Date: 2026-11-24
# source: Hugging Face Blog (NVIDIA)

## Summary

NVIDIA details a sim-to-real workflow for adding obstacle avoidance to the Pollen Robotics Microduck while keeping its existing walking policy frozen. A separate navigation policy uses time-of-flight (ToF) sensing to adjust gamepad velocity commands at 50 Hz; the frozen walking policy then turns those commands into joint actions.

## Architecture

- **Two-policy design:** Navigation policy (adjusts commands) + frozen walking policy (joint actions). Keeps walking policy fixed.
- **Sensing:** Simulates VL53L5CX ToF sensor — 8×8 grid, 15 Hz, 45° FOV, 0.12–4 m range. Training adds noise, delays, missing readings, and mounting variation.
- **Actor/critic split:** Actor uses only real-robot-available signals; critic can use extra simulation state during training.

## Training

- PPO across 16,384 parallel environments for 1,500 iterations (reference setup).
- Smaller run on NVIDIA DGX Spark: ~6 hours with 4,096 environments.
- Obstacle courses built from primitives and SimReady OpenUSD assets; layouts randomized at each reset.

## Reward design

Rewards progress toward goal and safe arrivals. Penalizes fast approaches, abrupt command changes, collisions, and falls.

## Real-robot deployment

A laptop runs the navigation model and sends adjusted commands to the robot's walking policy. Forward speed capped at 0.15 m/s by default; close-obstacle brake and stale-input stopping included.

## Resources

Isaac Lab docs, Microduck home page, deployment README, SimReady asset dataset — all linked in the original post.
