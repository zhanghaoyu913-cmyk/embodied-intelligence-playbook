<p align="center">
  <img src="../../assets/figures/banner_world_model.svg" alt="World model banner" width="100%"/>
</p>

# World Models

> **A world model is a bet:** that better prediction and state abstraction can reduce how much the robot must discover through costly trial and error.

<p align="center">
  <img src="../../assets/figures/flow_world_model.svg" alt="World model flow" width="92%"/>
</p>

---

## In-page Navigation

- [Topic Thesis](#topic-thesis)
- [Why This Topic Matters](#why-this-topic-matters)
- [Problem Decomposition](#problem-decomposition)
- [Core Technical Routes](#core-technical-routes)
- [Classical Backbone](#classical-backbone)
- [Frontier Watchlist (2025-2026)](#frontier-watchlist-2025-2026)
- [Open-source Projects & Toolchains](#open-source-projects--toolchains)
- [Datasets / Benchmarks / Simulators](#datasets--benchmarks--simulators)
- [Academic Labs & Company Systems](#academic-labs--company-systems)
- [Practical Build Paths](#practical-build-paths)
- [Common Failure Modes](#common-failure-modes)
- [Reading Sequence](#reading-sequence)
- [Research Radar](#research-radar)
- [Open Questions](#open-questions)

---

## Topic Thesis

The practical question for world models is not "can the model predict future frames?"

The real question is:

> **what kind of imagined future is operationally useful for control, planning, adaptation, and data generation?**

A world model matters only if it changes what the robot can do:

- plan more cheaply
- adapt with fewer trials
- evaluate more futures
- recover faster

---

## Why This Topic Matters

Embodied interaction is expensive:

- real robots are slow
- failure is costly
- long-horizon tasks compound error
- data collection is narrow and biased

World models are attractive because they promise:

- latent state abstraction
- action-conditioned prediction
- imagined rollouts
- sample efficiency
- better integration between perception and control

They matter most when the bottleneck is not seeing the world, but **anticipating how it will change**.

---

## Problem Decomposition

### 1. State abstraction

What should the model compress?

- pixels
- latent state
- objects and parts
- scene geometry
- affordances

### 2. Prediction target

What should it predict?

- next observation
- latent future
- reward
- success signal
- contact event
- task progress

### 3. Decision interface

How is the model used?

- planner in latent space
- policy improvement
- exploration guidance
- synthetic data generator
- reward estimator

### 4. Uncertainty

Can the model know when it should not be trusted?

### 5. Transfer

Does the model generalize across scenes, tasks, objects, and embodiments?

---

## Core Technical Routes

### Route A: latent dynamics models

Predict compact internal state transitions.

Best for: planning and model-based RL.

### Route B: video world models

Predict future observations or semantically rich video.

Best for: interpretable rollouts and multimodal integration.

### Route C: object-centric and scene-centric models

Represent the world as entities, parts, or relations.

Best for: manipulation, articulation, and relational reasoning.

### Route D: world model plus planner hybrids

Tie prediction directly to trajectory optimization or search.

Best for: continuous control and decision-focused rollouts.

### Route E: world model plus RL

Use the learned world to reduce real interaction cost.

Best for: sample efficiency and policy improvement.

### Route F: world models for data generation

Use predictive models to create or filter synthetic experience.

Best for: data scarcity and augmentation.

### Decision interface matrix

| Interface | What the model predicts | What it improves | What can go wrong |
|---|---|---|---|
| prediction only | next observation or latent future | representation quality | beautiful rollouts with no control gain |
| planner in latent space | task-relevant future states | trajectory search and foresight | planner quality hides model limits |
| RL with learned world | reward-bearing futures | sample efficiency | world-model exploitation and reward hacking |
| data generation | synthetic trajectories or relabeled futures | dataset breadth | synthetic bias and compounding errors |

---

## Classical Backbone

| Work | Why it still matters | Labels |
|---|---|---|
| [World Models](https://arxiv.org/abs/1803.10122) | canonical imagination-for-control framing | classical |
| [PlaNet](https://arxiv.org/abs/1811.04551) | compact latent planning with action-conditioned dynamics | classical |
| [DreamerV2](https://danijar.com/project/dreamerv2/) | major modern latent world-model RL milestone | classical |
| [DreamerV3](https://danijar.com/project/dreamerv3/) | practical baseline for broad world-model RL reference | classical, open-source, reproducible, beginner-friendly |
| [TD-MPC2](https://www.tdmpc2.com/) | strong latent planning baseline across control tasks | classical, open-source, reproducible |
| [MuZero](https://www.nature.com/articles/s41586-020-03051-4) | crucial decision-interface reference even outside robotics | classical |
| [V-JEPA](https://ai.meta.com/research/vjepa/) | predictive video modeling with embodied relevance | classical, industrial-signal |

---

## Frontier Watchlist (2025-2026)

| Work | Why it matters | Labels |
|---|---|---|
| [V-JEPA 2](https://ai.meta.com/research/publications/v-jepa-2-self-supervised-video-models-enable-understanding-prediction-and-planning/) | self-supervised video world model with a clear understanding-prediction-planning story | frontier-2025-2026, industrial-signal |
| [World-Gymnast](https://world-gymnast.github.io/) | RL fine-tuning inside an action-conditioned video world model | frontier-2025-2026 |
| [FLARE](https://research.nvidia.com/labs/gear/flare/) | joint policy plus latent future modeling from NVIDIA GEAR | frontier-2025-2026, industrial-signal |
| [Robotic World Model](https://github.com/leggedrobotics/robotic_world_model) | neural-simulator framing for robust policy optimization | frontier-2025-2026, open-source, reproducible |
| [MuJoCo Playground](https://playground.mujoco.org/) | not a world model alone, but a major open evaluation stack for predictive-control ideas | frontier-2025-2026, open-source, build-path |
| [GR00T N1.5](https://research.nvidia.com/labs/gear/gr00t-n1_5/) | tracks how predictive data and post-training enter humanoid stacks | frontier-2025-2026, industrial-signal |
| [GR-RL](https://seed.bytedance.com/en/gr_rl) | useful signal for how policy refinement and predictive components may merge in embodied systems | frontier-2025-2026, industrial-signal |
| [RynnVLA-002](https://github.com/alibaba-damo-academy/RynnVLA-002) | public signal that integrated embodied stacks are becoming more open | frontier-2025-2026, open-source |

---

## Open-source Projects & Toolchains

| Project | Why it matters | Labels |
|---|---|---|
| [DreamerV3](https://github.com/danijar/dreamerv3) | strongest accessible world-model RL reference | open-source, reproducible, beginner-friendly, build-path |
| [TD-MPC2](https://github.com/nicklashansen/tdmpc2) | modern latent-planning baseline | open-source, reproducible, build-path |
| [Robotic World Model](https://github.com/leggedrobotics/robotic_world_model) | robotics-specific world-model signal | open-source, reproducible |
| [MuJoCo Playground](https://github.com/google-deepmind/mujoco_playground) | open benchmarking stack for control ideas | open-source, build-path |
| [ManiSkill](https://maniskill.ai/) | useful for manipulation-side predictive evaluation | build-path, simulator |
| [OpenVLA](https://openvla.github.io/) | good adjacent control baseline when asking if prediction buys anything | reproducible |

---

## Datasets / Benchmarks / Simulators

| Resource | Why it matters | Best use |
|---|---|---|
| [Meta-World](https://meta-world.github.io/) | clean control benchmark | first controlled experiments |
| [MuJoCo Playground](https://playground.mujoco.org/) | open robot RL stack | predictive-control evaluation |
| [ManiSkill](https://maniskill.ai/) | scalable manipulation simulation | harder interaction tasks |
| [LIBERO](https://libero-project.github.io/main.html) | compositional manipulation benchmark | long-horizon manipulation evaluation |
| [BEHAVIOR-1K](https://behavior.stanford.edu/index.html) | household-scale task breadth | human-centered generalization |
| [BridgeData V2](https://rail-berkeley.github.io/bridgedata/) | real manipulation trajectories | offline or hybrid predictive training |

---

## Academic Labs & Company Systems

| Node | Why track it | Representative signals |
|---|---|---|
| Meta | strongest public predictive-video signal with embodied relevance | V-JEPA line |
| Berkeley | RL and robot learning anchor for decision-focused state models | BAIR, BridgeData, Octo ecosystem |
| Google DeepMind | planner, RL, and benchmark stack depth | MuJoCo ecosystem, model-based control history |
| NVIDIA GEAR | prediction plus policy plus humanoid stack | FLARE, GR00T line |
| Carnegie Mellon | embodied systems and predictive learning depth | self-supervised and agent-learning lines |
| Stanford | household systems where predictive state matters | BEHAVIOR, TidyBot-style systems |

---

## Practical Build Paths

### Build Path A: clean benchmark route

Use [World Model build path](../build_paths/world_model.md) with DreamerV3 or TD-MPC2 on Meta-World or MuJoCo tasks.

Best for: first reproducible predictive-control experiment.

### Build Path B: manipulation benchmark route

Use ManiSkill or LIBERO with a world-model baseline and a strong non-predictive baseline.

Best for: testing whether prediction helps under contact and long horizons.

### Build Path C: VLA bridge route

Use a fixed visuomotor baseline, then ask whether predictive state, imagined rollout scoring, or policy post-training improves closed-loop outcomes.

Best for: readers exploring world models as a subsystem rather than a standalone field.

---

## Common Failure Modes

- evaluating prediction quality instead of decision quality
- using good-looking video forecasts that do not improve control
- hiding planner weakness inside model weakness, or vice versa
- ignoring uncertainty when model errors compound
- comparing against weak baselines and overclaiming sample efficiency

---

## Reading Sequence

### Beginner

1. World Models
2. PlaNet
3. DreamerV3

Goal: understand latent dynamics and why prediction must serve control.

### Intermediate

1. TD-MPC2
2. MuZero
3. ManiSkill or Meta-World evaluation

Goal: compare planning interfaces and control relevance.

### Advanced

1. V-JEPA 2
2. World-Gymnast
3. FLARE

Goal: track the convergence of predictive video, RL, and integrated robot stacks.

---

## Research Radar

Watch these questions now:

- when are video world models actually better than latent control models
- how should uncertainty be exposed to planners and policies
- where should world models sit in VLA or humanoid stacks
- can predictive models become a reliable data-generation engine

---

## Open Questions

- What is the right decision interface for world models in robotics?
- How should models represent contact and hidden state?
- When does predictive modeling help more than stronger behavior cloning?
- How can world models stay trustworthy under embodiment change?
- What benchmarks actually reveal long-horizon planning gains rather than short-horizon reconstruction gains?

---

## Related Pages

- [Reinforcement Learning](rl.md)
- [VLA](vla.md)
- [Simulators](../resources/simulators.md)
- [Industry Map](../maps/industry.md)
- [World Model build path](../build_paths/world_model.md)
