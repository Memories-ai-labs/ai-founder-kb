# Putting Sign Language AI Into Users' Hands
# URL: https://deepmind.google/blog/putting-sign-language-ai-into-users-hands/
# Date: 2026-08-12
# Source: Google DeepMind Blog

## Overview

Google DeepMind unveiled a breakthrough sign-language-to-text (SL2T) translation model, powering new accessibility features in Gboard and Live Transcribe on Pixel 11, beginning with American Sign Language (ASL) to English translation.

## The Innovation

The SL2T model addresses a significant accessibility gap that persisted despite rapid progress in spoken language AI. According to the team: "signing in ASL is faster, more natural, and more delightful than typing in English."

## Technical Approach

- Trained on over 100,000 hours of data across more than 50 sign languages
- Uses on-device pose tracking to identify body landmark locations, protecting user privacy by discarding original video immediately
- Translates coordinate sequences directly into text, bypassing intermediate gloss annotations which fail to capture full sign language grammar complexity
- On-device processing preserves privacy

## Community-Centered Development

The team established the AI Sign Language Advisory Committee (AISLAC), composed of global Deaf organizations, ensuring impacted communities directly influence development priorities. This represents a model for participatory AI design.

## Availability

Features shipping on Pixel 11 with ASL support first; additional sign languages and expanded capabilities on the development roadmap.
