<p align="center">
  <img src="../../assets/figures/banner_rl.svg" alt="RL banner" width="100%"/>
</p>

# Reinforcement Learning

> **Reinforcement learning is the discipline of improvement under consequence.** In embodied AI, that means learning not only what to do, but what to keep doing when the world refuses to cooperate.

<p align="center">
  <img src="../../assets/figures/flow_rl.svg" alt="RL flow" width="92%"/>
</p>

---

## Topic Mood

In robotics, RL matters whenever demonstrations are incomplete, the task is long-horizon, or the policy must improve by interacting with its environment rather than only imitating it.

The practical question is not simply “should I use RL?” but:

> **Where should RL sit in the stack — in simulation, in a world model, on the real robot, or as a post-training stage on top of imitation or VLA policies?**

---

## What this topic is really about

RL in embodied AI spans at least five regimes:

1. **online RL in simulation** — efficient for locomotion and repeated tasks
2. **offline RL from datasets** — useful when real interaction is expensive
3. **model-based RL** — planning in a learned latent or predictive model
4. **RL fine-tuning of pretrained policies** — the 2025–2026 trend for VLA and world-model stacks
5. **real-world RL** — hardest but often the most convincing route for adaptation and recovery

---

## Where RL usually earns its keep

- locomotion and balance
- dexterous control
- recovery behaviors after off-nominal execution
- long-horizon task improvement after imitation learning
- policy adaptation to new dynamics, tools, or embodiments

---

## Core technical routes

### 1. Model-free RL
Examples: PPO, SAC and their descendants.

**Good for:** strong baselines, robust optimization loops, locomotion stacks with heavy simulation.

### 2. Model-based RL
Examples: DreamerV3, TD-MPC2, recent robotic world-model work.

**Good for:** sample efficiency, planning, latent-state reasoning, scaling across tasks.

### 3. RL + imitation
A common recipe is to pretrain with demonstrations, then refine with RL.

**Good for:** manipulation where pure exploration is too expensive.

### 4. RL inside a learned world model
A newer direction uses action-conditioned video or latent models to run RL in imagination.

**Good for:** reducing real-world interaction cost while retaining task-specific optimization.

---

## 2025–2026 frontier watchlist

| Work | Why it matters | Links |
|---|---|---|
| World-Gymnast (2026) | RL fine-tuning of a VLA policy inside a learned video world model | [paper](https://arxiv.org/abs/2602.02454) · [project](https://world-gymnast.github.io/) · [code](https://github.com/world-gymnast/world-gymnast) |
| MuJoCo Playground (2025) | modern open-source training stack for robot RL and sim-to-real | [paper](https://arxiv.org/abs/2502.08844) · [project](https://playground.mujoco.org/) · [code](https://github.com/google-deepmind/mujoco_playground) |
| Robotic World Model (2025) | neural-simulator view of model-based RL for robotics | [code](https://github.com/leggedrobotics/robotic_world_model) |
| Seed GR-RL (2025) | ByteDance’s RL-focused robotics entry built on top of generalist VLA ideas | [official](https://seed.bytedance.com/en/gr_rl) |

---

## Compact classic foundation

| Work | Why start here | Links |
|---|---|---|
| DreamerV3 | general world-model RL baseline with unusually broad scope | [paper](https://arxiv.org/abs/2301.04104) · [project](https://danijar.com/project/dreamerv3/) · [code](https://github.com/danijar/dreamerv3) |
| TD-MPC2 | practical model-based RL with strong continuous-control scaling | [paper](https://arxiv.org/abs/2310.16828) · [project](https://www.tdmpc2.com/) · [code](https://github.com/nicklashansen/tdmpc2) |
| Learning to Walk in 20 Minutes | direct real-world RL for quadruped locomotion | [paper](https://www.roboticsproceedings.org/rss19/p056.pdf) |
| OpenAI Dactyl / Rubik’s Cube | classic sim-to-real dexterous manipulation through RL and domain randomization | [Learning Dexterity](https://openai.com/index/learning-dexterity/) · [Rubik’s Cube](https://openai.com/index/solving-rubiks-cube/) |

---

## Practical stacks worth using

### Simulation-first RL stacks
- [Isaac Lab](https://isaac-sim.github.io/IsaacLab/)
- [MuJoCo Playground](https://playground.mujoco.org/)
- [legged_gym](https://github.com/leggedrobotics/legged_gym)

### Dataset / imitation / offline hybrids
- [robomimic](https://robomimic.github.io/)
- [LeRobot](https://huggingface.co/docs/lerobot/index)

### Good benchmark families to pair with RL
- [LIBERO](https://libero-project.github.io/main.html)
- [CALVIN](https://github.com/mees/calvin)
- [Meta-World](https://meta-world.github.io/)
- [BEHAVIOR-1K](https://behavior.stanford.edu/index.html)

---

## Build-first reading strategy

### If your goal is locomotion
Start with:
1. MuJoCo Playground / Isaac Lab
2. legged_gym and ANYmal-style papers
3. TD-MPC2 or DreamerV3 as model-based alternatives

### If your goal is manipulation
Start with:
1. robomimic / LeRobot / BridgeData V2
2. imitation learning baseline
3. RL fine-tuning or world-model RL only after the BC baseline is solid

### If your goal is VLA improvement
Start with:
1. OpenVLA or Octo
2. a fixed task family and reward definition
3. World-Gymnast-style fine-tuning, not RL from scratch

---

## What to inspect when a robotics RL paper claims success

- how much real-world data is used
- whether the reward is hand-engineered, learned, or VLM-based
- whether the policy is trained in physics simulation or a learned world model
- whether recovery behavior is shown, not just nominal success
- whether deployment latency and stability are discussed

---

## Closing Thought

RL becomes most interesting in embodied AI when it is not treated as an isolated algorithmic badge, but as a **placement decision in the system stack**: where should the agent improve, against which signal, and with what cost of interaction?
