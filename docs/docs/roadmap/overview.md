<p align="center">
  <img src="../../assets/figures/banner_overview.svg" alt="Overview banner" width="100%"/>
</p>

# Overview

> **Embodied intelligence is not one problem.** It is a stack: perception, state representation, action, memory, reward, physics, and adaptation.

---

## Reading this repository the right way

This repository treats embodied AI as a **system stack**, not a loose collection of papers:

1. **Perception** — images, video, point clouds, proprioception, language, touch  
2. **State** — latent scene structure, object states, affordance maps, world models  
3. **Policy** — behavior cloning, diffusion policies, VLA systems, planners, RL agents  
4. **Interaction** — grasping, contact-rich manipulation, locomotion, navigation, handoff  
5. **Learning loop** — demonstrations, RL, synthetic data, world-model rollouts, evaluation  
6. **Deployment** — simulation, sim-to-real, embodiment transfer, safety, monitoring, repair  

A strong embodied system rarely wins on only one layer. Most impressive results come from the **coupling** between layers:
- perception that exposes the right state variables
- state representations that can support planning
- policies that can recover after off-nominal execution
- learning loops that can keep improving after the first deployment

---

## The six topic roadmaps in this repository

| Roadmap | Core question | Best for |
|---|---|---|
| [Vision-Language-Action](vla.md) | how instructions become actions | readers tracking foundation-model robotics |
| [World Models](world_model.md) | what kind of prediction actually helps control | readers interested in foresight and latent state |
| [Reinforcement Learning](rl.md) | where improvement should sit in the stack | readers building adaptation loops |
| [Manipulation](manipulation.md) | how robots complete tasks under contact and uncertainty | readers implementing real or simulated robot tasks |
| [Grasping](grasping.md) | how the system chooses stable, task-useful contact | readers building pick-and-place or clutter pipelines |
| [Affordance Learning](affordance.md) | what can be done, where, and why | readers linking perception to executable action |

---

## A map of the field by build path

### Route A — language to action
Use this if you want to understand the current foundation-model wave.

**Suggested sequence**
1. [VLA](vla.md)
2. [Manipulation](manipulation.md)
3. [Grasping](grasping.md)
4. [Datasets](../resources/datasets.md)
5. [Frameworks](../resources/frameworks.md)

**Typical project path**
Open X-Embodiment → OpenVLA / Octo → BridgeData V2 / Mobile ALOHA / LeRobot → task-specific fine-tuning.

---

### Route B — world model to control
Use this if you care about planning, latent state, sample efficiency, and long-horizon prediction.

**Suggested sequence**
1. [World Models](world_model.md)
2. [Reinforcement Learning](rl.md)
3. [Manipulation](manipulation.md)
4. [Simulators](../resources/simulators.md)

**Typical project path**
DreamerV3 / TD-MPC2 → MuJoCo Playground / Isaac Lab → policy improvement in simulation or learned world models.

---

### Route C — perception to physical interaction
Use this if you want to connect perception with touch, contact, and action geometry.

**Suggested sequence**
1. [Grasping](grasping.md)
2. [Affordance Learning](affordance.md)
3. [Manipulation](manipulation.md)
4. [Benchmarks](../resources/benchmarks.md)

**Typical project path**
GraspNet / Contact-GraspNet → affordance maps / part reasoning → manipulation benchmarks such as CALVIN, LIBERO, and BEHAVIOR-1K.

---

## What changed in 2025–2026

The field changed in an important way.

Earlier waves often asked:
- can large multimodal models touch robotics?
- can imitation scale with more robot data?
- can simulation transfer improve control?

The newer wave asks:
- where should **reasoning** live in a robot stack?
- where should **RL** be inserted: in simulation, in a world model, or on the real robot?
- what parts of the stack are now becoming **open-source and reproducible**?
- how much of the robot stack can be moved from one embodiment to another?

That is why this repository explicitly tracks:
- VLA systems and open training stacks
- world-model-based planning and RL
- humanoid and mobile-manipulation system releases
- low-cost real-robot build paths
- institution and company ecosystems, not only papers

---

## One practical way to read any paper in embodied AI

When reading a paper or project, ask these four questions first:

1. **What is the action interface?**  
   Joint deltas, end-effector commands, chunks, skills, trajectories, tokens?

2. **Where does the world state live?**  
   Pixels, latent state, object graph, affordance map, memory buffer?

3. **How does the system improve after failure?**  
   Better prompts, more demonstrations, RL, test-time adaptation, world-model rollouts?

4. **What changes when the embodiment changes?**  
   Action head only, whole policy, prompt adapter, controller, data mix?

If these questions remain vague, the work may be impressive but less reusable than it appears.

---

## How this repository differs from a plain paper list

This repository is built around four principles:

### 1. System placement matters
A method is not only “good” or “bad”; it matters **where it sits in the stack**.

### 2. Open build paths matter
Links to code, datasets, simulators, and tutorials matter as much as paper links.

### 3. Classical backbone + frontier watchlist
Each topic page separates:
- **classical backbone**
- **frontier watchlist (2025–2026)**
- **open-source toolchains**
- **build paths**
- **failure modes**

### 4. Aesthetic structure should aid memory
The visual style is not decoration alone. It should make the field easier to remember.

---

## Recommended first-week reading plans

### If you are a beginner
- Day 1: [VLA](vla.md)
- Day 2: [Manipulation](manipulation.md)
- Day 3: [Grasping](grasping.md)
- Day 4: [Affordance Learning](affordance.md)
- Day 5: [Datasets](../resources/datasets.md) + [Frameworks](../resources/frameworks.md)

### If you want to build a system
- [Manipulation](manipulation.md)
- [Grasping](grasping.md)
- [Affordance Learning](affordance.md)
- [Simulators](../resources/simulators.md)
- [Frameworks](../resources/frameworks.md)

### If you want to do research
- [World Models](world_model.md)
- [Reinforcement Learning](rl.md)
- [Academic Labs & Universities](../resources/academia_map.md)
- [Conferences & Journals](../resources/venues.md)

---

## Closing Thought

The best way to use this repository is not to read everything.

Pick a route, build one system, fail in a visible way, and then return to the map.  
Embodied AI becomes much clearer once the abstractions are forced to meet contact, latency, and deployment.
