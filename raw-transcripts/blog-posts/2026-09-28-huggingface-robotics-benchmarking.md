# Robotics Benchmarking: Where We Are and What Comes Next
# URL: https://huggingface.co/blog/projectsim/robotics-benchmarking-where-we-are-and-what-comes
# Date: 2026-09-28
# Source: Hugging Face Blog (Community Article)

**Authors:** Luca Cilio and collaborators (lucakae, Karneet, tf-k3d, nqt230, sanyarobot)

## Current State of Robotics Benchmarking

The field has developed increasingly sophisticated evaluation methods. Early benchmarks like YCB (2015) standardized test objects, while modern suites like BEHAVIOR 1K assess complex household tasks involving liquids and cloth. Current benchmarks evaluate:
- Component-level performance (pose estimation)
- Task execution in simulation (MetaWorld, RLBench)
- Skill combination and transfer (LIBERO, CALVIN)

## The Physical Testing Challenge

Unlike language model evaluation, repeating physical robot tests is costly and difficult. The authors note that "sharing a policy and its code does not reproduce the camera calibration, gripper pads, table surface or object placements." Environmental variations compound this problem, requiring numerous trials to distinguish real improvement from normal variation.

They reference DROID's data collection effort — "76,000 demonstrations...took 50 people across 13 institutions a year."

## Future Direction

The authors propose benchmarks should identify policy weaknesses and guide training data collection decisions. Rather than just measuring performance, evaluation should suggest targeted practice to address specific failures — a cycle connecting "successive rounds of testing and learning."

## ProjectSim's Approach

Their experiment reconstructs physical robot setups in simulation using high-fidelity assets, geometry, and appearance data. The goal is determining whether improved simulations can faithfully reproduce real robot performance, enabling scaled practice without continuous physical reset work.
