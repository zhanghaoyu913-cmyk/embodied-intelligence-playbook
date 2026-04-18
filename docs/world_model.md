<p align="center">
  <img src="../../assets/figures/banner_world_model.svg" alt="World model banner" width="100%"/>
</p>

# World Models

> **A world model is a bet:** that better prediction and state abstraction can reduce how much the robot must discover through painful trial and error.

<p align="center">
  <img src="../../assets/figures/flow_world_model.svg" alt="World model flow" width="92%"/>
</p>

---

## Topic Thesis

World models are where embodied AI tries to become **anticipatory** rather than purely reactive.

The central question is not simply:

> *Can the model predict future pixels or video?*

The practical question is:

> **What kind of imagined future is operationally useful for control, planning, adaptation, and transfer?**

A world model is only as good as what it helps the robot do:
- plan more cheaply
- recover faster
- generalize farther
- adapt with fewer real-world trials

---

## Why this topic matters

In embodied AI, raw interaction is expensive:
- real robots are slow
- data collection is costly
- contact failures are risky
- long-horizon tasks compound error quickly

World models promise a partial escape route by providing:
- compact latent state
- action-conditioned prediction
- imagined rollouts
- uncertainty-aware evaluation
- better sample efficiency

They matter most when the task needs:
- foresight
- counterfactual reasoning
- planning under limited data
- policy improvement beyond imitation

---

## Problem Decomposition

### 1. State abstraction
What should the model compress?
- pixels
- objects
- scene geometry
- affordances
- latent dynamics
- reward-relevant hidden variables

### 2. Prediction target
What should it predict?
- observations
- latent states
- rewards
- success signals
- contact events
- action consequences

### 3. Decision interface
How is the world model used?
- planner in latent space
- policy improvement
- reward estimation
- exploration guidance
- data generation
- test-time adaptation

### 4. Uncertainty and reliability
Does the model know when it does **not** know enough?

### 5. Transfer
Does the model generalize:
- across scenes
- across objects
- across tasks
- across embodiments

---

## Major Technical Routes

### Route A — latent dynamics models
Compact internal state transitions conditioned on actions.

**Good for**
- planning
- model-based RL
- efficient control loops

**Core idea**
Predict in latent space rather than reconstructing every pixel.

---

### Route B — video world models
Predict future visual observations or semantic videos.

**Good for**
- human-interpretable futures
- trajectory imagination
- integration with vision-language models

**Main challenge**
Good-looking video is not the same as decision-useful state.

---

### Route C — object-centric and scene-centric models
Represent the world as entities, parts, or relationships.

**Good for**
- manipulation
- articulated objects
- relational reasoning
- contact-aware planning

---

### Route D — world model + planner hybrids
Tie prediction directly to downstream decision-making.

**Good for**
- continuous control
- local trajectory optimization
- high-value imagined rollouts

---

### Route E — world model + RL
Use the learned world to reduce the need for real interaction.

**Good for**
- policy improvement
- long-horizon optimization
- bootstrapping from demonstrations

---

### Route F — world models for data generation
Use predictive models to synthesize or transform training data.

**Good for**
- reducing data scarcity
- creating diverse robot experience
- sim2real or real2real augmentation

---

## Frontier Watchlist (2025–2026)

| Work | Why it matters | Links |
|---|---|---|
| V-JEPA 2 (2025) | self-supervised video world model with a clear understanding-prediction-planning story | [paper](https://ai.meta.com/research/publications/v-jepa-2-self-supervised-video-models-enable-understanding-prediction-and-planning/) · [project](https://ai.meta.com/research/vjepa/) |
| World-Gymnast (2026) | directly trains robot policies with RL inside a learned action-conditioned video world model | [paper](https://arxiv.org/abs/2602.02454) · [project](https://world-gymnast.github.io/) · [code](https://github.com/world-gymnast/world-gymnast) |
| FLARE (2025) | lightweight joint policy + latent future modeling from NVIDIA GEAR | [project](https://research.nvidia.com/labs/gear/flare/) |
| Robotic World Model (2025) | neural-simulator framing for robust policy optimization | [code](https://github.com/leggedrobotics/robotic_world_model) |
| GigaBrain-0 (2025) | VLA foundation model empowered by world-model-generated data; useful nearby signal | [paper](https://arxiv.org/abs/2510.19430) |
| GR00T N1.5 / N1.6 (2025) | not a pure world-model project, but important for tracking predictive data and post-training trends in humanoid stacks | [N1.5](https://research.nvidia.com/labs/gear/gr00t-n1_5/) · [N1.6](https://research.nvidia.com/labs/gear/gr00t-n1_6/) |

---

## Classical Backbone

| Work | Why it matters | Links |
|---|---|---|
| World Models (Ha & Schmidhuber) | canonical early statement that imagination can support control | [paper](https://arxiv.org/abs/1803.10122) |
| PlaNet | compact latent planning with action-conditioned dynamics | [paper](https://arxiv.org/abs/1811.04551) |
| DreamerV2 | major modern latent world-model RL milestone | [project](https://danijar.com/project/dreamerv2/) |
| DreamerV3 | most practical current baseline for broad world-model RL reference | [project](https://danijar.com/project/dreamerv3/) · [code](https://github.com/danijar/dreamerv3) |
| TD-MPC2 | latent planning with strong scaling across many continuous-control tasks | [project](https://www.tdmpc2.com/) · [code](https://github.com/nicklashansen/tdmpc2) |
| MuZero | not robotics-specific, but crucial for understanding model-based decision interfaces | [paper](https://www.nature.com/articles/s41586-020-03051-4) |

---

## Datasets, Simulators, and Nearby Resources

### Good datasets for world-model thinking
- [Open X-Embodiment](https://robotics-transformer-x.github.io/)
- [BridgeData V2](https://rail-berkeley.github.io/bridgedata/)
- [BEHAVIOR-1K](https://behavior.stanford.edu/index.html)
- [LIBERO](https://libero-project.github.io/main.html)

### Good simulator / training environments
- [MuJoCo Playground](https://playground.mujoco.org/)
- [Isaac Lab](https://isaac-sim.github.io/IsaacLab/)
- [Meta-World](https://meta-world.github.io/)
- [ManiSkill](https://maniskill.ai/)

### Useful nearby open baselines for comparison
- [OpenVLA](https://openvla.github.io/)
- [Octo](https://octo-models.github.io/)
- [Open X-Embodiment](https://robotics-transformer-x.github.io/)

These are not world models in the narrow sense, but they are excellent control baselines that help test whether the world model actually buys something.

---

## A practical reading ladder

### Level 1 — learn latent dynamics
1. World Models
2. PlaNet
3. DreamerV2
4. DreamerV3

**Goal**  
Understand why latent-space prediction can be enough for action selection.

---

### Level 2 — learn planning in latent space
1. TD-MPC2
2. MuJoCo Playground
3. compare world-model planning with PPO / SAC baselines

**Goal**  
Understand whether prediction helps enough to justify the added complexity.

---

### Level 3 — study the new frontier
1. V-JEPA 2  
2. World-Gymnast  
3. FLARE  
4. Robotic World Model  

**Goal**  
Track the shift from “predict for representation” to “predict for policy improvement.”

---

## Build Paths

### Build Path A — clean benchmark path
DreamerV3 or TD-MPC2 → small control benchmark → compare against PPO / SAC.

**Best for**
- beginners entering model-based RL
- readers who want a controlled setting

---

### Build Path B — manipulation benchmark path
Latent planner or predictive model → CALVIN / LIBERO / ManiSkill-like tasks → compare with BC or diffusion-policy baselines.

**Best for**
- readers who want robotics relevance without jumping straight to real robots

---

### Build Path C — VLA + world-model path
Take a strong manipulation policy or VLA baseline → add predictive rollouts / imagined fine-tuning → evaluate recovery and scene transfer.

**Best for**
- advanced thesis-level work
- researchers interested in bridging world models and foundation policies

---

## What to inspect in a world-model paper

- what variables are predicted: pixels, latent states, objects, rewards, success, contact, language-conditioned futures
- whether uncertainty is represented or ignored
- whether planning is explicit or only implied
- whether the model helps downstream control more than a strong policy baseline
- whether the “imagination” is causal enough to be operational
- whether transfer is across scenes only, or across embodiments too

---

## Common Failure Modes

- beautiful predictions that do not improve control
- latent states that are compact but not actionable
- planning gains that disappear under realistic latency
- overclaiming transfer from scene generalization to embodiment generalization
- evaluation on toy tasks only
- no comparison against a strong behavior-cloning or diffusion baseline

---

## Open Questions

- What is the right state granularity for robotics: latent vector, object graph, video tokens, or something hybrid?
- Can video world models support precise contact-rich manipulation rather than only coarse foresight?
- How should uncertainty enter control decisions in world-model robotics?
- Can world models become a practical way to generate diverse robot data rather than just a research curiosity?
- How should memory, planning, and embodiment adaptation be shared inside one predictive stack?

---

## Closing Thought

The right question for world models is not:

> *Can the robot imagine?*

It is:

> **What kind of imagination is operationally useful?**

Useful world models are the ones that make better decisions cheaper.
