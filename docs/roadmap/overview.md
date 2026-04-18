<p align="center">
  <img src="../../assets/figures/banner_overview.svg" alt="Overview banner" width="100%"/>
</p>

# Overview

> **Embodied intelligence is not one problem.** It is a stack: perception, state representation, action, memory, reward, physics, and adaptation.

---

## What this repository treats as the core stack

The playbook organizes embodied AI around six mutually coupled layers:

1. **Perception** — images, video, point clouds, proprioception, language, touch
2. **State** — latent scene structure, object states, affordance maps, world models
3. **Policy** — behavior cloning, diffusion policies, VLA systems, planners, RL agents
4. **Interaction** — grasping, contact-rich manipulation, locomotion, navigation, handoff
5. **Learning loop** — demonstrations, RL, synthetic data, world-model rollouts, evaluation
6. **Deployment** — simulation, sim-to-real, embodiment transfer, safety and monitoring

A strong embodied system rarely wins on only one layer.

---

## The six roadmaps in this repository

| Roadmap | What it centers on | Best starting use |
|---|---|---|
| [Vision-Language-Action](vla.md) | instruction-grounded action | readers tracking the foundation-model wave |
| [World Models](world_model.md) | dynamics, prediction, planning | readers who care about latent state and foresight |
| [Reinforcement Learning](rl.md) | reward-driven improvement | readers building control and adaptation loops |
| [Manipulation](manipulation.md) | task execution under contact | readers implementing real or simulated robot tasks |
| [Grasping](grasping.md) | stable task-aware interaction | readers needing a solid entry for pick-and-place stacks |
| [Affordance Learning](affordance.md) | what can be done, where, and why | readers linking perception to executable action |

---

## How to read the field without getting lost

### Route 1 — follow the data + policy thread
Open X-Embodiment → Octo / OpenVLA → BridgeData / Mobile ALOHA / ACT → deployment and adaptation.

### Route 2 — follow the world-model + RL thread
DreamerV3 → TD-MPC2 → MuJoCo Playground / Isaac Lab → V-JEPA 2 / World-Gymnast.

### Route 3 — follow the physical interaction thread
GraspNet / Contact-GraspNet → affordance reasoning → manipulation benchmarks such as CALVIN, LIBERO, and BEHAVIOR-1K.

---

## What changed in 2025–2026

The field shifted from “can large multimodal models touch robotics?” to “which pieces of the robot stack can foundation models, world models, and RL improve in practice?”

That is why this repository now explicitly tracks:

- VLA systems and open training stacks
- world-model-based planning and RL
- humanoid and mobile-manipulation system releases
- institution and company maps, not only papers

---

## Suggested first reading sequence

### Beginner
1. [VLA](vla.md)
2. [Manipulation](manipulation.md)
3. [Datasets](../resources/datasets.md)
4. [Frameworks](../resources/frameworks.md)

### Building systems
1. [Manipulation](manipulation.md)
2. [Grasping](grasping.md)
3. [Affordance Learning](affordance.md)
4. [Simulators](../resources/simulators.md)

### Research-oriented
1. [World Models](world_model.md)
2. [Reinforcement Learning](rl.md)
3. [Academic Labs & Universities](../resources/academia_map.md)
4. [Conferences & Journals](../resources/venues.md)

---

## One practical rule

When reading a paper or project, always ask four questions:

1. **What is the action interface?**
2. **Where does the world state live?**
3. **How does the system improve after failure?**
4. **What changes when the embodiment changes?**

If a paper is impressive but these four questions remain vague, it is often less reusable than it appears.
