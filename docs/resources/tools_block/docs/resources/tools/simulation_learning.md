# Simulation and Learning Frameworks

> This file covers **where to train, benchmark, and iterate on embodied policies**.

## Quick selector

| Problem | Best first choices |
|---|---|
| modular robot-learning framework | Isaac Lab |
| bleeding-edge Isaac branch | Isaac Lab 3.0 Beta |
| manipulation simulation and training | ManiSkill, ManiSkill 3 |
| embodied simulation with HRI and humanoids | Habitat 3.0 |
| imitation learning baselines | robomimic |
| practical low-cost real-robot path | LeRobot |

---

## 1. Isaac Lab

### Isaac Lab
- **What it is**: a unified and modular framework for robot learning.
- **Best for**: RL, imitation, sim-to-real experiments, large-scale training on NVIDIA’s stack.
- **Why use it**: strong if you want a serious simulation/training environment with broad robotics workflows.
- **Official links**
  - Docs: https://isaac-sim.github.io/IsaacLab/

### Isaac Lab 3.0 Beta
- **What it is**: the newer beta line with active experimentation around Newton integration and engine abstraction.
- **Best for**: users who want to watch where the Isaac stack is going next.
- **Why use it**: important as a forward-looking path, but more experimental than the stable path.
- **Official links**
  - Beta docs: https://isaac-sim.github.io/IsaacLab/main/source/experimental-features/newton-physics-integration/isaaclab_newton-beta-2.html
  - Release notes: https://isaac-sim.github.io/IsaacLab/main/source/refs/release_notes.html

---

## 2. ManiSkill

### ManiSkill
- **What it is**: a unified framework for robot simulation and training with a strong focus on manipulation.
- **Best for**: manipulation, demonstrations, RL/imitation benchmarks, SAPIEN-based workflows.
- **Official links**
  - Docs: https://maniskill.readthedocs.io/

### ManiSkill 3
- **What it is**: the current v3 beta line.
- **Best for**: newer manipulation workflows, higher-performance collection, more modern APIs.
- **Why use it**: if your main topic is manipulation, this is one of the most natural stacks to watch and use.
- **Official links**
  - Beta docs: https://maniskill.readthedocs.io/
  - Beta repo/release path: https://github.com/zhuoqun-chen/ManiSkill3

---

## 3. Habitat

### Habitat
- **What it is**: a simulation platform for embodied AI.
- **Best for**: navigation, embodied agents, egocentric tasks, indoor environments.
- **Official links**
  - Platform: https://aihabitat.org/
  - Habitat-Lab repo: https://github.com/facebookresearch/habitat-lab
  - Habitat-Sim repo: https://github.com/facebookresearch/habitat-sim

### Habitat 3.0
- **What it is**: the newer Habitat line focused on humanoid simulation, human-in-the-loop interaction, and collaborative human-robot tasks.
- **Best for**: HRI-heavy embodied simulation and humanoid studies in home environments.
- **Official links**
  - Habitat 3.0 page: https://aihabitat.org/habitat3/

---

## 4. Imitation and real-robot practical stacks

### robomimic
- **What it is**: a standard open imitation-learning framework and dataset ecosystem.
- **Best for**: behavior cloning baselines, manipulation imitation, benchmark-aligned experiments.
- **Official links**
  - Project: https://robomimic.github.io/

### LeRobot
- **What it is**: a practical ecosystem for robot datasets, policies, and low-cost robot experimentation.
- **Best for**: real-robot practical paths, hosted datasets, short build paths from teleop to training.
- **Official links**
  - Docs: https://huggingface.co/docs/lerobot/index

---

## Practical guidance

### If you care about manipulation first
Use:
- ManiSkill 3 + robomimic + LeRobot

### If you care about RL at scale
Use:
- Isaac Lab

### If you care about navigation / HRI / embodied agents
Use:
- Habitat / Habitat 3.0

### If you care about the shortest practical builder path
Use:
- LeRobot

---

## Common failure modes

- choosing the biggest simulator before defining the benchmark
- starting RL before a strong imitation baseline exists
- ignoring dataset/tooling fit
- mixing benchmark results from incompatible setups
