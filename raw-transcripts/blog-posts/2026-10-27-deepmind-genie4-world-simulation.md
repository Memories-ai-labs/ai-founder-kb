# Genie 4: A new generation of world simulation
# URL: https://deepmind.google/blog/genie-4-a-new-generation-of-world-simulation/
# Date: 2026-10-27
# Source: Google DeepMind Blog

Google DeepMind announced Genie 4, a world model offering greater realism and real-time interactive simulation. It is natively multimodal, generating music, ambient sound, and interactive dialogue alongside visuals. It draws on the Gemini family: Gemini Omni anchors simulations in real-world appearance and behavior, while other Gemini models maintain scene coherence over time.

Users can steer a simulation in real time with keyboard controls for navigation and camera movement, plus text prompts. Changing weather, moving the camera, or adding a person or object is done in natural language, and Gemini adapts those changes to the surrounding scene. Improved physics include aerodynamics, collisions, more natural human movement, and native audio including dialogue that adapts as events unfold.

Gemini also acts as a guiding agent during generation: it observes the scene, breaks a goal into steps, checks whether each step succeeded, and revises its plan when the world shifts or a user intervenes. DeepMind experimented with Gemini 4 Argon and Genie 4 together to simulate an Apptronik Apollo humanoid playing checkers — framed as a path toward simulating scenarios for robotics and agents before they reach the real world.

Genie 4 is rolling out as a research preview to trusted testers, with broader availability planned for Google AI Ultra subscribers in Project Genie and early-access partners in the Gemini API and Google AI Studio. Use cases include previz, turning archival photos into explorable scenes, and rapid game prototyping. All generated video and audio carry SynthID watermarks.

Limitations acknowledged: visual details and object permanence can drift over longer sessions or after many prompt edits; complex physics, audio accuracy, legible text, spatial accuracy, and long-term consistency remain active research areas. DeepMind frames future work around hybrid world models combining Gemini's structured reasoning with Genie's pixel-level rendering.
