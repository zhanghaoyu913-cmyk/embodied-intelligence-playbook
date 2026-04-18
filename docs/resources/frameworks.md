# Frameworks

This page lists practical frameworks and codebases that are especially useful for embodied-intelligence work.

---

## Quick recommendation table

| Goal | Framework |
|---|---|
| easiest practical robotics ML entry | [LeRobot](#lerobot) |
| offline imitation learning baselines | [robomimic](#robomimic) |
| open VLA training and fine-tuning | [OpenVLA](#openvla) |
| open generalist robot policies | [Octo](#octo) |
| model-based continuous control | [TD-MPC2](#td-mpc2) |
| GPU-accelerated robot-learning playground | [MuJoCo Playground](#mujoco-playground) |

---

## LeRobot

A rapidly maturing open-source robotics stack with datasets, models, docs, and hardware interfaces.

Why use it:
- very practical onboarding experience
- integrates models, datasets, training, and deployment
- supports real-world robotics workflows

Links:
- [Hub](https://huggingface.co/lerobot)
- [GitHub](https://github.com/huggingface/lerobot)

Best for:
- quick prototyping
- training ACT and related policies
- real-world experiments
- dataset and deployment pipelines

---

## robomimic

A classic framework for robot learning from demonstration.

Why use it:
- standardized offline imitation-learning baselines
- strong documentation
- clean dataset + baseline structure

Links:
- [Project](https://robomimic.github.io/)
- [Code](https://github.com/ARISE-Initiative/robomimic)

Best for:
- offline imitation learning
- benchmark reproduction
- baseline comparisons

---

## OpenVLA

Open-source VLA training and fine-tuning codebase.

Why use it:
- reference stack for open VLA work
- supports RLDS-format data mixtures
- practical fine-tuning path for downstream robots

Links:
- [Project](https://openvla.github.io/)
- [Code](https://github.com/openvla/openvla)

Best for:
- VLA research
- robot-policy fine-tuning
- Open-X-style data mixtures

---

## Octo

Open-source generalist robot policy project.

Why use it:
- compact and practical open-source generalist policy
- flexible observation and action definitions
- good bridge from Open-X data to downstream fine-tuning

Links:
- [Project](https://octo-models.github.io/)
- [Code](https://github.com/octo-models/octo)

Best for:
- generalist policy experimentation
- cross-dataset robotics work
- starting open policy research

---

## TD-MPC2

Model-based RL framework for continuous control and multitask scaling.

Why use it:
- strong model-based control baseline
- good if your question is really about planning/control efficiency rather than language grounding

Links:
- [Project](https://www.tdmpc2.com/)
- [Code](https://github.com/nicklashansen/tdmpc2)

Best for:
- continuous control
- model-based RL
- multitask world-model experiments

---

## MuJoCo Playground

Open-source framework for GPU-accelerated robot learning and sim-to-real transfer.

Why use it:
- fast setup
- modern MJX/MuJoCo ecosystem
- convenient for control-heavy iteration

Links:
- [Website](https://playground.mujoco.org/)
- [Code](https://github.com/google-deepmind/mujoco_playground)

Best for:
- rapid robot-learning iteration
- control and sim-to-real experiments
- modern MuJoCo workflows

---

## CALVIN codebase

Long-horizon language-conditioned manipulation benchmark and baselines.

Links:
- [Project](https://calvin.cs.uni-freiburg.de/)
- [Code](https://github.com/mees/calvin)

Best for:
- long-horizon language-conditioned policy evaluation

---

## LIBERO

Benchmark and codebase for transfer and lifelong robot learning.

Links:
- [Project](https://libero-project.github.io/main.html)
- [Code](https://github.com/Lifelong-Robot-Learning/LIBERO)

Best for:
- transfer studies
- benchmark-driven evaluation
- continual / lifelong learning

---

## BridgeData V2 codebase

Training code and reference implementations on BridgeData V2.

Links:
- [Project](https://rail-berkeley.github.io/bridgedata/)
- [Code](https://github.com/rail-berkeley/bridge_data_v2)

Best for:
- goal-conditioned BC
- diffusion / language-conditioned robot learning on real data

---

## PerAct / Diffusion Policy / ACT

These are not general-purpose frameworks in the same sense as LeRobot or robomimic, but they are critical reference implementations.

- [PerAct](https://github.com/peract/peract)
- [Diffusion Policy](https://github.com/real-stanford/diffusion_policy)
- [ACT](https://github.com/tonyzhaozh/act)

Use them when:
- you want paper-faithful reproduction
- you care about a specific policy family
- you want to compare action interfaces

---

## How to choose a framework

### If you want to build quickly
- LeRobot
- robomimic
- ManiSkill ecosystem

### If you want to study foundation-model robotics
- OpenVLA
- Octo
- Open X tooling

### If you want strong control / world-model baselines
- TD-MPC2
- DreamerV3
- MuJoCo Playground

### If you want paper-faithful manipulation baselines
- PerAct
- Diffusion Policy
- ACT
