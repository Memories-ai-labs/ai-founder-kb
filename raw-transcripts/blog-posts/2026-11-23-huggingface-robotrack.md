# RoboTrack: Point tracking for real-world robotic manipulation
# URL: https://huggingface.co/blog/allenai/robotrack
# Date: 2026-11-23
# Source: Hugging Face Blog (Ai2 / AllenAI)

**RoboTrack: Point tracking for real-world robotic manipulation**
Date: November 23, 2026
Author: Kyle Wiggers (Ai2Comms)
Publisher: Ai2 (AllenAI), via Hugging Face Blog

## Overview

Ai2 introduces RoboTrack, a benchmark and training data suite for point tracking in robotic manipulation. Point tracking follows a chosen location on an object across video frames, including when it is occluded.

## RoboTrack-Bench

A human-annotated benchmark of 307 videos from DROID, Ego-Exo4D, MolmoAct 2, and EgoVerse, with 2,522 tracks. Covers cluttered scenes and first- and third-person views.

## Existing Trackers Struggle

Four leading trackers (CoTracker3, BootsTAPNext, AllTracker, CoWTracker) all scored lower on RoboTrack-Bench than on RoboTAP, the other real-video robotics benchmark.

## RoboTrack-15M

A synthetic dataset of 15 million tracks from 3,000 simulated robot manipulation videos, generated with MolmoSpaces. Design was refined through several iterations guided by how far points move compared with real footage.

## New Models

- **RoboTracker**: Fine-tuned from AllTracker
- **RoboTracker-Warp**: Fine-tuned from CoWTracker; reached top AJ on 4 of 5 benchmarks
- Both models' weights are for noncommercial use

## Real-World Application

In a wet-lab pipetting task learned from one demonstration:
- Point tracking: 17/20 trials successful
- Object masks: 8/20 trials
- Optical flow: 5/20 trials

## Limitations

- Trackers struggle with long occlusions
- Reacquiring points after they reappear remains difficult
- Small objects against busy backgrounds are challenging
- Simulated data doesn't yet capture fine motions (e.g., pipette handling)

## Resources

- Tech report, datasets (RoboTrack-15M, RoboTrack-Bench), code, project page, and models all published
