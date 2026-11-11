# Gemini Robotics 2.5 accelerates real-world general dexterity
# URL: https://deepmind.google/blog/gemini-robotics-2-5-accelerates-real-world-physical-intelligence/
# Date: 2026-11-10
# Source: Google DeepMind Blog

Author: Carolina Parada

---

Google DeepMind's Gemini Robotics 2.5 is described as its "most capable vision-language-action (VLA) model to date," aimed at broadening the skills robots can learn and speeding up how quickly they learn them for less structured real-world settings. Rolling out to robotics partners.

## Key Technical Advances

**Dexterity and task breadth:**
- Tested on 200+ distinct tasks: serving food with tongs, tying bows, pipetting liquids
- Combines tool use, deformable object manipulation, delicate item handling
- 30–100% higher success rates vs. previous baseline (varies by task type)
- Tasks completed 20–30% faster

**Real-world reliability:**
- Proof-of-concept with Apptronik and Mercedes-Benz
- Apollo 2 humanoid robots sorted automotive parts on production lines with 96% success rate
- System pairs Gemini Robotics ER (workflow tracking) + Robotics 2.5 (hands/arms control)

**Cross-platform support:**
- Apollo 2 humanoid (five-finger hand)
- Franka Duo platform (two-finger grippers)
- Native multi-robot type support

**Safety and steerability:**
- Inference-time reasoning guidance helps robots avoid physical hazards
- 33% increase in safe task completion around obstacles
- 43% increase around nearby people
- Released ASIMOV-Jailbreak: open-source benchmark for robotics-specific adversarial prompts
- Gemini 4 Argon: 99.5% jailbreak resistance vs. 82% for previous baseline

**Simulation-driven training:**
- Gemini 4 Argon acts as simulation engine
- Generates simulated practice runs and digital twins from real camera scenes
- Combined with real demonstrations, helps robots generalize to new scenes and objects
- Can analyze failure footage and test improvements in simulation before real-robot trials

## Significance for AI Founders

Physical AI is maturing rapidly. The pairing of a reasoning model (ER) with an action model (Robotics 2.5) is an architectural pattern — "think + act" — that mirrors agentic software architectures. The 96% automotive parts sorting success rate suggests production-ready performance for structured manufacturing tasks.
