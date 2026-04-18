<p align="center">
  <img src="../../assets/figures/banner_rl.svg" alt="RL banner" width="100%"/>
</p>

# Reinforcement Learning

> **Reinforcement learning is the discipline of improvement under consequence.** In embodied AI, that means learning not only what to do, but what to keep doing when the world refuses to cooperate.

<p align="center">
  <img src="../../assets/figures/flow_rl.svg" alt="RL flow" width="92%"/>
</p>

---

## Topic Thesis

In embodied AI, RL is best understood not as a badge, but as a **placement decision in the system stack**:

> **Where should the robot improve, from what signal, and at what interaction cost?**

That is the practical framing that matters more than asking whether RL is “better” than imitation learning.

---

## Why this topic matters

Demonstrations are powerful, but they are incomplete:
- they may be suboptimal
- they may not cover recovery behavior
- they often fail on edge cases
- they do not scale to every embodiment and environment shift

RL matters whenever the agent must improve by interacting with consequences:
- locomotion and balance
- dexterous control
- recovery after failed execution
- long-horizon refinement after imitation learning
- adaptation to new dynamics, tools, and layouts

---

## The five RL regimes that matter most in embodied AI

### 1. Online RL in simulation
The classic workhorse for locomotion and control.

**Best for**
- many repeated trials
- rich simulation
- motor skill discovery
- dynamics randomization

---

### 2. Offline RL from datasets
Useful when real robot interaction is expensive or unsafe.

**Best for**
- demonstration-heavy settings
- filtered robot logs
- bridging imitation and optimization

---

### 3. Model-based RL
Optimize behavior with the help of a learned predictive model.

**Best for**
- sample efficiency
- planning
- tasks where imagined rollouts are good enough to be useful

---

### 4. RL fine-tuning of pretrained policies
A major 2025–2026 direction.

**Best for**
- improving VLA systems
- manipulation tasks where BC is near-correct but not precise enough
- cases where demonstrations are helpful but not optimal

---

### 5. Real-world RL
The most convincing and the hardest regime.

**Best for**
- adaptation
- robustness
- recovery behavior
- research that cares about actual deployment

---

## Core Technical Routes

### Route A — model-free RL
Examples: PPO, SAC, descendants.

**Strengths**
- strong baselines
- stable optimization loops
- excellent for simulation-heavy locomotion

**Weaknesses**
- expensive interaction
- weak sample efficiency without careful engineering

---

### Route B — model-based RL
Examples: DreamerV3, TD-MPC2.

**Strengths**
- sample efficiency
- latent planning
- easier integration with predictive state abstraction

**Weaknesses**
- additional complexity
- model quality becomes a bottleneck

---

### Route C — imitation + RL
A common modern recipe:
1. pretrain with demonstrations
2. fine-tune with RL

**Strengths**
- faster start than RL from scratch
- better exploration in manipulation
- more realistic path for physical tasks

---

### Route D — RL inside a learned world model
A newer route that treats the learned world as the environment.

**Strengths**
- reduced real interaction cost
- can bootstrap from real data
- promising bridge between VLA and policy improvement

**Weaknesses**
- world-model errors can induce reward hacking or brittle optimization

---

## Frontier Watchlist (2025–2026)

| Work | Why it matters | Links |
|---|---|---|
| World-Gymnast (2026) | RL fine-tuning of a robot policy inside an action-conditioned video world model | [paper](https://arxiv.org/abs/2602.02454) · [project](https://world-gymnast.github.io/) |
| MuJoCo Playground (2025) | open-source, MJX-based robot RL stack with strong sim-to-real orientation | [project](https://playground.mujoco.org/) · [report](https://playground.mujoco.org/assets/playground_technical_report.pdf) |
| Seed GR-RL (2025) | real-world RL post-training of a generalist VLA for dexterous manipulation | [official](https://seed.bytedance.com/en/gr_rl) · [technical report](https://seed.bytedance.com/public_papers/gr-rl-going-dexterous-and-precise-for-long-horizon-robotic-manipulation) |
| FLARE (2025) | lightweight joint policy + latent future modeling from NVIDIA GEAR | [project](https://research.nvidia.com/labs/gear/flare/) |
| V-JEPA 2 (2025) | not an RL method alone, but important for the predictive-model side of future RL stacks | [paper](https://ai.meta.com/research/publications/v-jepa-2-self-supervised-video-models-enable-understanding-prediction-and-planning/) |
| RSL-RL ecosystem (2025+) | practically important because it underlies multiple modern training stacks | [repo](https://github.com/leggedrobotics/rsl_rl) |

---

## Classical Backbone

| Work | Why start here | Links |
|---|---|---|
| PPO | standard baseline for on-policy continuous control | [paper](https://arxiv.org/abs/1707.06347) |
| SAC | canonical off-policy continuous-control method | [paper](https://arxiv.org/abs/1801.01290) |
| DreamerV3 | broad and practical world-model RL reference | [project](https://danijar.com/project/dreamerv3/) · [code](https://github.com/danijar/dreamerv3) |
| TD-MPC2 | strong modern model-based RL for continuous control | [project](https://www.tdmpc2.com/) · [code](https://github.com/nicklashansen/tdmpc2) |
| Learning to Walk in 20 Minutes | persuasive real-world RL locomotion reference | [paper](https://www.roboticsproceedings.org/rss19/p056.pdf) |
| OpenAI Dactyl / Rubik’s Cube | dexterous manipulation through RL, sim-to-real, and domain randomization | [Learning Dexterity](https://openai.com/index/learning-dexterity/) · [Rubik’s Cube](https://openai.com/index/solving-rubiks-cube/) |

---

## Stacks, Benchmarks, and Frameworks Worth Knowing

### Simulation-first RL stacks
- [Isaac Lab](https://isaac-sim.github.io/IsaacLab/)
- [MuJoCo Playground](https://playground.mujoco.org/)
- [legged_gym](https://github.com/leggedrobotics/legged_gym)
- [RSL-RL](https://github.com/leggedrobotics/rsl_rl)

### Dataset / imitation / offline hybrids
- [robomimic](https://robomimic.github.io/)
- [LeRobot](https://huggingface.co/docs/lerobot/index)
- [BridgeData V2](https://rail-berkeley.github.io/bridgedata/)

### Benchmarks to pair with RL
- [Meta-World](https://meta-world.github.io/)
- [LIBERO](https://libero-project.github.io/main.html)
- [CALVIN](https://github.com/mees/calvin)
- [BEHAVIOR-1K](https://behavior.stanford.edu/index.html)

---

## Reading Ladders

### Ladder A — locomotion
1. PPO / SAC basics  
2. legged_gym  
3. Isaac Lab  
4. MuJoCo Playground  
5. compare against model-based alternatives like TD-MPC2

**Goal**  
Understand why RL still dominates for agile and repeated-control settings.

---

### Ladder B — manipulation
1. robomimic / LeRobot  
2. strong imitation baseline  
3. RL fine-tuning only after BC is competent  
4. compare reward design and recovery gains

**Goal**  
Use RL where it adds precision and robustness, not where it replaces a good demonstration pipeline.

---

### Ladder C — VLA post-training
1. OpenVLA / Octo baseline  
2. fixed task family + reward  
3. World-Gymnast or GR-RL-style post-training ideas

**Goal**  
Study how RL improves pre-trained robot policies instead of training from scratch.

---

## Build Paths

### Build Path A — benchmarked simulation control
PPO / SAC / TD-MPC2 → Meta-World or MuJoCo tasks → scaling experiments.

**Best for**
- newcomers to RL
- ablation-heavy research
- reproducible comparisons

---

### Build Path B — legged or humanoid RL
legged_gym / Isaac Lab / MuJoCo Playground → policy transfer → real robot.

**Best for**
- locomotion
- sim-to-real control
- robotics-heavy RL

---

### Build Path C — manipulation refinement
Behavior-cloning or VLA baseline → reward shaping / sparse reward → RL fine-tuning on precision failures.

**Best for**
- dexterous tasks
- long-horizon refinement
- real-robot post-training

---

## What to inspect when a robotics RL paper claims success

- how much real-world interaction is used
- whether the reward is hand-engineered, learned, or VLM-based
- whether recovery behavior is shown, not just nominal success
- whether deployment latency and stability are discussed
- whether the baseline imitation policy is strong enough
- whether the paper optimizes the whole task, or only a narrow subskill

---

## Common Failure Modes

- RL is used where a good BC baseline would have solved the problem more cheaply
- reward design quietly encodes the solution
- sim-to-real claims depend on narrow dynamics randomization
- real-world fine-tuning is too expensive to be reusable
- model-based claims omit world-model error analysis
- long-horizon success is inflated by easier initializations or resets

---

## Open Questions

- What is the right interface between RL and VLA systems?
- How much real-world interaction is actually necessary once pretrained policies become stronger?
- Can VLM-based or world-model-based reward signals be made reliable enough for large-scale robot RL?
- Will real-world RL become practical for general manipulation, or remain a specialist refinement stage?
- How should RL credit assignment work when failures come from perception, not only control?

---

## Closing Thought

RL becomes most interesting in embodied AI when it is not treated as an isolated algorithmic badge, but as a **system decision**:

> where should the agent improve, against which signal, and with what cost of interaction?
