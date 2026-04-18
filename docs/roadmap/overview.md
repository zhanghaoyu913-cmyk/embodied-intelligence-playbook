<p align="center">
  <img src="../../assets/figures/banner_overview.svg" alt="Overview banner" width="100%"/>
</p>

# Overview

> **Embodied intelligence is a stack, not a slogan.** Good systems work because perception, state, policy, interaction, learning, and deployment fit together.

---

## In-page Navigation

- [Reading the atlas](#reading-the-atlas)
- [The six-layer stack](#the-six-layer-stack)
- [The six topic roadmaps](#the-six-topic-roadmaps)
- [Build routes](#build-routes)
- [Resource and map layer](#resource-and-map-layer)
- [How to read a paper](#how-to-read-a-paper)
- [Research radar](#research-radar)

---

## Reading the atlas

This repository is organized around one judgment:

> embodied AI becomes understandable when you know **where a method sits in the system** and **what it lets you build next**.

So the repository is not arranged primarily by year or conference. It is arranged by:

1. stack placement
2. classical backbone
3. frontier watchlist
4. reproducible tools
5. build paths
6. ecosystem maps

---

## The six-layer stack

| Layer | Question | Main repository entry points |
|---|---|---|
| Perception | what is in the scene and what matters now | [VLA](vla.md), [Grasping](grasping.md), [Affordance](affordance.md) |
| State | what latent or structured representation supports control | [World Models](world_model.md), [Affordance](affordance.md) |
| Policy | how instructions, plans, or rewards become action | [VLA](vla.md), [RL](rl.md), [Manipulation](manipulation.md) |
| Interaction | how the robot actually contacts and changes the world | [Manipulation](manipulation.md), [Grasping](grasping.md), [Affordance](affordance.md) |
| Learning loop | how the system improves after failure or new data | [RL](rl.md), [World Models](world_model.md) |
| Deployment | how simulation, latency, embodiment, and monitoring affect success | [Simulators](../resources/simulators.md), [Frameworks](../resources/frameworks.md), [Sim-to-Real build path](../build_paths/sim2real.md) |

---

## Shared labels

Use these labels as navigation cues across roadmap tables:

- `classical`
- `frontier-2025-2026`
- `open-source`
- `benchmark`
- `simulator`
- `industry-system`
- `build-path`
- `beginner-friendly`
- `reproducible`
- `industrial-signal`

---

## The six topic roadmaps

| Topic | Core question | Best starting reader |
|---|---|---|
| [Vision-Language-Action](vla.md) | how instructions become grounded action | readers tracking foundation-model robotics |
| [World Models](world_model.md) | what prediction actually helps control | readers interested in planning, sample efficiency, and foresight |
| [Reinforcement Learning](rl.md) | where improvement should sit in the stack | readers building adaptation loops and control refinements |
| [Manipulation](manipulation.md) | how robots finish tasks under contact and uncertainty | readers implementing real or simulated robot tasks |
| [Grasping](grasping.md) | how contact is chosen for downstream success | readers building pick, place, or clutter pipelines |
| [Affordance Learning](affordance.md) | what can be done, where, and why | readers linking perception to executable interaction |

---

## Build routes

### Route A: Language to action

1. [VLA](vla.md)
2. [Manipulation](manipulation.md)
3. [Benchmarks](../resources/benchmarks.md)
4. [VLA Entry build path](../build_paths/vla_entry.md)

Best for: readers who want an open-source route into current VLA systems.

### Route B: Prediction to control

1. [World Models](world_model.md)
2. [RL](rl.md)
3. [Simulators](../resources/simulators.md)
4. [World Model build path](../build_paths/world_model.md)

Best for: readers who care about sample efficiency, planning, and predictive state.

### Route C: Perception to physical interaction

1. [Grasping](grasping.md)
2. [Affordance](affordance.md)
3. [Manipulation](manipulation.md)
4. [Grasping + Affordance build path](../build_paths/grasping_affordance.md)

Best for: readers who want to connect visual understanding to contact and downstream action.

### Route D: Simulation to deployment

1. [Benchmarks](../resources/benchmarks.md)
2. [Simulators](../resources/simulators.md)
3. [Frameworks](../resources/frameworks.md)
4. [Sim-to-Real build path](../build_paths/sim2real.md)

Best for: readers who already have a simulator result and want to move toward hardware.

---

## Resource and map layer

The roadmap pages are the backbone. The rest of the repository exists to make them executable.

| Need | Best page |
|---|---|
| choose an evaluation world | [Benchmarks](../resources/benchmarks.md) |
| choose a dataset | [Datasets](../resources/datasets.md) |
| choose a simulator | [Simulators](../resources/simulators.md) |
| choose a codebase | [Frameworks](../resources/frameworks.md) |
| know who to follow in academia | [Academia Map](../maps/academia.md) |
| know which companies matter and why | [Industry Map](../maps/industry.md) |

---

## How to read a paper

When reading any embodied-AI paper, ask these four questions first:

1. What is the **action interface**?
2. Where does the **state** live?
3. How does the system **improve after failure**?
4. What breaks when the **embodiment changes**?

If a paper is unclear on those four questions, it may still be interesting, but it is harder to place inside a reusable system.

---

## Research radar

The field shifted materially in 2025-2026. The most important changes are not just "bigger models."

Watch these axes:

- reasoning layers inside robot stacks, not only perception-to-action mapping
- RL inserted after imitation or inside world models, not only from scratch
- on-device and whole-body deployment paths, not only lab demos
- benchmark and tooling ecosystems that let outsiders reproduce parts of the stack
- ecosystem nodes: labs, companies, and open-source communities that define default workflows

---

## Closing thought

The best way to use this repository is not to read every page.

Pick one route, build one system, hit one visible failure mode, then come back to the atlas with a sharper question.
