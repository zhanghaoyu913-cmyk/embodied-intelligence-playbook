<p align="center">
  <img src="../../assets/figures/banner_world_model.svg" alt="World model banner" width="100%"/>
</p>

# World Models

> **A world model is a bet:** that better prediction and state abstraction can reduce how much the robot must discover through painful trial and error.

<p align="center">
  <img src="../../assets/figures/flow_world_model.svg" alt="World model flow" width="92%"/>
</p>

---

## Topic Mood

World models are where embodied AI becomes less reactive and more anticipatory. The central question is not merely “can the model predict video?” but:

> **What kind of latent world is useful enough to support planning, control, adaptation, and transfer?**

---

## What this topic is really about

A useful world model should ideally support some combination of:

- state compression
- action-conditioned prediction
- counterfactual evaluation
- planning or policy improvement
- uncertainty estimation
- transfer to new scenes, tasks, or embodiments

---

## Major technical routes

### Latent dynamics models
Compact internal states with action-conditioned transitions.

### Video world models
Predict future visual observations or semantic video trajectories.

### Object-centric or scene-centric models
Useful when object state, contact, and relational structure matter.

### World model + planner / RL hybrids
Often strongest when prediction is explicitly tied to downstream decision-making.

---

## 2025–2026 frontier watchlist

| Work | Why it matters | Links |
|---|---|---|
| V-JEPA 2 (2025) | self-supervised video world model with understanding, prediction, and zero-shot robot planning signals | [paper](https://ai.meta.com/research/publications/v-jepa-2-self-supervised-video-models-enable-understanding-prediction-and-planning/) · [project](https://ai.meta.com/research/vjepa/) |
| World-Gymnast (2026) | connects learned video world models directly to RL improvement for robot policies | [paper](https://arxiv.org/abs/2602.02454) · [project](https://world-gymnast.github.io/) |
| Robotic World Model (2025) | neural network simulator perspective for robust policy optimization | [code](https://github.com/leggedrobotics/robotic_world_model) |
| GR00T N1.5 / N1.6 (2025) | frontier humanoid stack where predictive modeling and policy quality co-evolve | [N1.5](https://research.nvidia.com/labs/gear/gr00t-n1_5/) · [N1.6](https://research.nvidia.com/labs/gear/gr00t-n1_6/) |

---

## Compact classic foundation

| Work | Why it matters | Links |
|---|---|---|
| DreamerV3 | most practical modern world-model RL reference point | [paper](https://arxiv.org/abs/2301.04104) · [project](https://danijar.com/project/dreamerv3/) |
| TD-MPC2 | planning in latent space with strong continuous-control performance | [paper](https://arxiv.org/abs/2310.16828) · [project](https://www.tdmpc2.com/) |
| Open X + Octo / OpenVLA | not “world models” in the narrow sense, but essential open baselines for comparison | [Open X](https://robotics-transformer-x.github.io/) · [Octo](https://octo-models.github.io/) · [OpenVLA](https://openvla.github.io/) |

---

## Datasets and simulators that matter here

- [Open X-Embodiment](https://robotics-transformer-x.github.io/)
- [BridgeData V2](https://rail-berkeley.github.io/bridgedata/)
- [BEHAVIOR-1K](https://behavior.stanford.edu/index.html)
- [MuJoCo Playground](https://playground.mujoco.org/)
- [Isaac Lab](https://isaac-sim.github.io/IsaacLab/)

---

## What to inspect in a world-model paper

- what variables are predicted: pixels, latent states, objects, rewards, contact, language-conditioned futures
- whether uncertainty is represented or ignored
- whether planning is explicit or only implied
- whether transfer is across scenes only, or across embodiments too
- whether the model helps downstream control more than a strong policy baseline

---

## Project directions

### Beginner
Reproduce DreamerV3 on a small control benchmark, then compare against PPO/SAC.

### Intermediate
Study whether TD-MPC2-style latent planning helps more than behavior cloning on a manipulation benchmark.

### Advanced
Test whether a video world model can provide enough signal to fine-tune a VLA policy, in the style of World-Gymnast.

---

## Closing Thought

The right question for world models is not “can the robot imagine?” It is “**what kind of imagination is operationally useful?**” Useful world models are those that make better decisions cheaper.
