---
Title: Grabette: An Open System to Record Robot-Manipulation Data
Source: Hugging Face Blog
URL: https://huggingface.co/blog/grabette
Date: 2026-07-21
Publisher: Hugging Face (Pollen Robotics guest post)
Authors: Steve Nguyen, Claire Houziel, Gaelle Lannuzel, Simon Le Goff, Jeremy Laville, Etienne, contributors from Pollen Robotics
---

# Grabette: An Open System to Record Robot-Manipulation Data

**Published:** July 21, 2026

## Problem

Robot learning has a supply problem — large, diverse, real-world manipulation data is the bottleneck. Traditional approaches require expensive teleoperation rigs, creating barriers to entry.

## Solution

Grabette is an **open-source handheld gripper system** for democratizing robot manipulation data collection. Just human hand + gripper + camera.

## Hardware

- **Grabette**: Handheld recording device (~490 EUR BOM) with two cameras, an IMU, and a gripper
- **Gripette**: Motorized gripper (~120 EUR BOM) for robotic execution

## Workflow

1. Record demonstrations by hand
2. Process in a **web browser** (no local compute required): handles SLAM trajectory recovery, conversion to LeRobot format, and dataset creation on the Hugging Face Hub

## Community Focus

Open, collaborative manipulation dataset — anyone can contribute demonstrations. Positioned as a democratization play for robotics data collection.

## Significance for Founders

The ~490 EUR BOM cost to create robot training data is a hardware cost signal — robotics data collection is becoming accessible to small teams and individuals, not just well-funded labs with teleoperation infrastructure.
