# Simulators

This page lists simulators and benchmark environments that matter most for embodied-intelligence practice.

---

## Quick recommendation table

| If you care about... | Start here |
|---|---|
| contact-rich control with mature physics | [MuJoCo](#mujoco) |
| GPU-scale robot learning with photorealism | [Isaac Lab](#isaac-lab) |
| open-source manipulation research at scale | [ManiSkill](#maniskill) |
| benchmark-heavy multi-task manipulation | [RLBench](#rlbench) |
| articulated objects and custom assets | [SAPIEN](#sapien) |
| embodied navigation / home environments | [Habitat 3.0](#habitat-30) |

---

## MuJoCo

The most standard physics engine in modern robot learning.

Why use it:
- fast and reliable contact simulation
- broad community support
- huge ecosystem of environments, wrappers, and MJCF assets

Links:
- [Official site](https://mujoco.org/)
- [Documentation](https://mujoco.readthedocs.io/)
- [GitHub](https://github.com/google-deepmind/mujoco)

Best for:
- control
- model-based RL
- manipulation prototyping
- custom robot modeling

---

## Isaac Lab

A modular robot-learning framework built on NVIDIA Isaac Sim.

Why use it:
- GPU-accelerated simulation
- photorealistic scenes and sensors
- strong for sim-to-real and large-batch experiments

Links:
- [Official site](https://isaac-sim.github.io/IsaacLab/)
- [Developer page](https://developer.nvidia.com/isaac/lab)
- [GitHub](https://github.com/isaac-sim/IsaacLab)

Best for:
- large-scale RL
- imitation learning at scale
- photorealistic robot experiments
- sim-to-real workflows

---

## ManiSkill

Unified, open-source framework for robot simulation and training with a manipulation focus.

Why use it:
- scalable visual data collection
- manipulation-first design
- excellent benchmark / dataset / simulator combination

Links:
- [Website](https://www.maniskill.ai/)
- [Documentation](https://maniskill.readthedocs.io/)
- [GitHub](https://github.com/haosulab/maniskill)

Best for:
- manipulation
- benchmark-based comparison
- generalizable robot learning
- data generation

---

## RLBench

Large benchmark and learning environment for manipulation research.

Why use it:
- many tasks
- widely cited in manipulation literature
- clear evaluation structure

Links:
- [Website](https://sites.google.com/view/rlbench)
- [Code](https://github.com/stepjam/RLBench)

Best for:
- manipulation benchmarking
- multi-task imitation learning
- PerAct-style 3D action-centric methods

---

## SAPIEN

Part-based interactive simulation environment with strong support for articulated assets.

Why use it:
- articulated-object ecosystem
- close integration with PartNet-Mobility style assets
- useful for affordance and articulated manipulation studies

Links:
- [Website](https://sapien.ucsd.edu/)

Best for:
- articulated objects
- affordance learning
- object-part interaction
- custom asset workflows

---

## Habitat 3.0

Embodied-AI simulator for human-robot interaction in home environments.

Why use it:
- rich home scenes
- human-avatar / robot interaction
- navigation + manipulation + embodied scene reasoning

Links:
- [Project](https://aihabitat.org/habitat3/)
- [Habitat platform](https://aihabitat.org/)

Best for:
- embodied navigation
- home environments
- collaborative human-robot tasks

---

## CoppeliaSim / PyRep via RLBench

You may not pick CoppeliaSim directly for new projects, but you will encounter it through RLBench.

Best for:
- reproducing RLBench-based literature
- comparing with classic manipulation baselines

---

## Choosing the right simulator

### Choose by problem
- control / model-based RL → MuJoCo
- general manipulation benchmark work → ManiSkill or RLBench
- articulated-object affordance → SAPIEN
- photorealistic large-scale sim → Isaac Lab
- navigation / home environments → Habitat

### Choose by engineering cost
- easiest to enter for classic robotics ML → MuJoCo
- easiest to reproduce benchmark papers → RLBench / CALVIN / LIBERO environment stacks
- best for custom articulated assets → SAPIEN / MuJoCo
- best for GPU-heavy scaling → Isaac Lab / ManiSkill

### Choose by output
- fast iteration → MuJoCo
- strong benchmark comparability → RLBench / ManiSkill
- stronger rendering / sensors → Isaac Lab / Habitat
- articulated interaction assets → SAPIEN
