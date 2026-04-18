<p align="center">
  <img src="../../assets/figures/banner_manipulation.svg" alt="Manipulation banner" width="100%"/>
</p>

# Manipulation

> **Manipulation is where embodied AI stops being abstract.** It must touch, align, place, recover, and finish.

<p align="center">
  <img src="../../assets/figures/flow_manipulation.svg" alt="Manipulation flow" width="92%"/>
</p>

---

## Topic Thesis

Manipulation is the clearest test of whether an embodied system actually works.

It is the place where:
- perception mistakes become contact failures
- timing errors become slippage or collisions
- poor state representations become task collapse
- brittle policies reveal themselves immediately

A manipulation system is not judged by how well it predicts the next action token, but by whether it **finishes** the task under clutter, contact, uncertainty, and drift.

---

## What this topic covers

Manipulation includes:
- reaching and picking
- placing and reorienting
- opening, wiping, pouring, stacking, assembling
- articulated-object operation
- bimanual coordination
- mobile manipulation
- long-horizon household and workspace tasks
- recovery under occlusion, clutter, contact uncertainty, and partial failure

---

## Why it is hard

Manipulation is hard because it couples nearly everything:
- perception
- calibration
- action representation
- contact dynamics
- memory
- timing
- recovery

A paper may look excellent in offline evaluation and still fail on real hardware because:
- the grasp was slightly wrong
- the object moved after contact
- the instruction was underspecified
- the controller lagged
- the scene changed between observation and actuation

---

## Problem Decomposition

### 1. Task decomposition
Is the task:
- one-shot or long-horizon?
- single-arm, dual-arm, or mobile?
- rigid, articulated, or deformable?
- precision-oriented or forgiving?

### 2. Observation
What does the policy actually see?
- fixed cameras
- wrist cameras
- depth
- point cloud
- proprioception
- language
- tactile cues

### 3. Action interface
What is the policy output?
- joint actions
- end-effector deltas
- chunks
- waypoints
- skill selection
- language-conditioned action tokens

### 4. Recovery
Can the policy notice and repair:
- bad grasps
- occlusions
- slight object shifts
- delayed action completion
- partial task completion

### 5. Generalization
Does the method transfer across:
- layouts
- objects
- tasks
- robot embodiments

---

## Core Technical Routes

### Route A — behavior cloning and imitation learning
Still the fastest route to useful manipulation baselines.

**Best for**
- teleoperated data
- structured task families
- low-cost real-robot projects

**Representative methods**
- ACT
- behavior-cloning transformer stacks
- imitation-first pipelines in robomimic and LeRobot

---

### Route B — diffusion policies
A major route for robust visuomotor control.

**Best for**
- multimodal action distributions
- manipulation with multiple valid solutions
- strong benchmark performance

**Representative methods**
- Diffusion Policy
- downstream diffusion-style action modeling in later generalist stacks

---

### Route C — in-context and foundation-style manipulation
Treat manipulation as sequence modeling over large sensorimotor corpora.

**Best for**
- few-shot adaptation
- prompting with demonstrations
- studying generalist robot policies

**Representative methods**
- ICRT
- Octo
- OpenVLA
- π0

---

### Route D — mobile and whole-body manipulation
A growing route where the robot must not only manipulate, but navigate and coordinate its body.

**Best for**
- household tasks
- room-scale autonomy
- humanoid and mobile-manipulator systems

---

### Route E — planning + policy hybrid stacks
Useful when one network is too opaque or too brittle.

**Best for**
- long-horizon tasks
- tasks with subgoal structure
- settings where explicit planning still matters

---

## Frontier Watchlist (2025–2026)

| Work | Why it matters | Links |
|---|---|---|
| ICRT (ICRA 2025) | in-context imitation learning via next-token prediction on sensorimotor trajectories | [project](https://icrt.dev/) |
| Helix 02 (2026) | full-body autonomy from pixels on a humanoid, not only upper-body tabletop control | [official](https://www.figure.ai/news/helix-02) |
| Gemini Robotics (2025) | pushes manipulation into the broader reasoning-and-embodiment frontier | [official](https://deepmind.google/models/gemini-robotics/) |
| GR00T N1.x (2025) | tracks the humanoid manipulation foundation-model trend from NVIDIA | [N1](https://research.nvidia.com/publication/2025-03_nvidia-isaac-gr00t-n1-open-foundation-model-humanoid-robots) · [N1.6](https://research.nvidia.com/labs/gear/gr00t-n1_6/) |
| Seed GR-3 / GR-RL (2025) | strong industrial line spanning generalist manipulation to dexterous RL refinement | [GR-3](https://seed.bytedance.com/GR3) · [GR-RL](https://seed.bytedance.com/en/gr_rl) |
| RynnBrain (2026) | embodied foundation-model ecosystem with benchmark orientation | [github](https://github.com/alibaba-damo-academy/RynnBrain) |
| LeRobot ecosystem growth (2025–2026) | practical open tooling for real-world data, policies, and low-cost hardware | [docs](https://huggingface.co/docs/lerobot/index) |
| TidyBot++ (2025) | open-source mobile manipulation system with reproducible hardware/software docs | [project](https://tidybot2.github.io/) · [docs](https://tidybot2.github.io/docs/) |

---

## Classical Backbone

| Work | Why it matters | Links |
|---|---|---|
| ACT | action chunking remains one of the most practical imitation-learning baselines | [code](https://github.com/tonyzhaozh/act) |
| Mobile ALOHA | low-cost mobile manipulation with major practical influence | [official](https://src.stanford.edu/demo/moble-aloha) |
| Diffusion Policy | very strong and influential policy parameterization for visuomotor manipulation | [project](https://diffusion-policy.cs.columbia.edu/) |
| OpenVLA | open-source VLA baseline with real adoption in manipulation work | [project](https://openvla.github.io/) |
| Octo | open-source generalist robot policy | [project](https://octo-models.github.io/) |
| π0 | general-purpose robot policy framing from Physical Intelligence | [official](https://www.physicalintelligence.company/blog/pi0) |
| robomimic | practical foundation for imitation-learning experiments | [project](https://robomimic.github.io/) |
| BridgeData V2 | important manipulation data ecosystem | [project](https://rail-berkeley.github.io/bridgedata/) |

---

## Benchmarks, Datasets, and Open Stacks

### Benchmarks
- [CALVIN](https://github.com/mees/calvin)
- [LIBERO](https://libero-project.github.io/main.html)
- [BEHAVIOR-1K](https://behavior.stanford.edu/index.html)
- [Meta-World](https://meta-world.github.io/)

### Data ecosystems
- [Open X-Embodiment](https://robotics-transformer-x.github.io/)
- [BridgeData V2](https://rail-berkeley.github.io/bridgedata/)
- [LeRobot datasets](https://huggingface.co/docs/lerobot/index)

### Useful open-source stacks
- [robomimic](https://robomimic.github.io/)
- [LeRobot](https://huggingface.co/docs/lerobot/index)
- [Isaac Lab](https://isaac-sim.github.io/IsaacLab/)
- [MuJoCo Playground](https://playground.mujoco.org/)
- [ManiSkill](https://maniskill.ai/)

---

## Build Paths

### Build Path A — low-cost real-robot route
Mobile ALOHA / SO-101 / LeRobot hardware → collect teleop data → ACT baseline → OpenVLA or Octo fine-tuning.

**Best for**
- teams that want to touch hardware quickly
- low-cost or lab-scale real-robot work
- first practical project

---

### Build Path B — simulation-first route
Isaac Lab / MuJoCo Playground / ManiSkill → behavior cloning baseline → diffusion or RL refinement.

**Best for**
- early algorithm iteration
- safer debugging
- large-scale training

---

### Build Path C — benchmark-first route
robomimic → CALVIN / LIBERO → BEHAVIOR-1K for longer horizons.

**Best for**
- paper reproduction
- ablation-heavy research
- systematic comparison

---

### Build Path D — foundation-policy comparison route
OpenVLA vs Octo vs ICRT vs π0-style systems → compare:
- action interface
- data needs
- embodiment transfer
- recovery quality

**Best for**
- thesis work
- strong survey writing
- research framing

---

## What to inspect in manipulation results

- closed-loop success, not only offline action error
- robustness after slight perturbations
- recovery after grasp drift or object displacement
- whether failure comes from perception, grasping, or policy timing
- whether the task requires memory or only one-shot execution
- whether the method transfers across objects and layouts

---

## Common Failure Modes

- a strong grasping module is missing, but the paper blames “policy” only
- language instructions are used, but task grounding remains fragile
- long-horizon tasks are demonstrated without enough failure analysis
- high success rates come from narrow reset conditions
- mobile manipulation claims ignore navigation and base-positioning errors
- real-world deployment hides calibration and latency assumptions

---

## Reading Sequence

### Beginner
1. ACT  
2. Mobile ALOHA  
3. robomimic  
4. BridgeData V2

### Intermediate
1. Diffusion Policy  
2. OpenVLA  
3. Octo  
4. CALVIN / LIBERO

### Advanced
1. ICRT  
2. π0  
3. Helix 02  
4. BEHAVIOR-1K and long-horizon system evaluation

---

## Open Questions

- What is the right balance between monolithic foundation policies and modular skill stacks?
- How should manipulation systems remember partial progress over long horizons?
- Can low-cost data collection pipelines remain competitive as foundation policies scale?
- What is the most reusable action interface across robot embodiments?
- How should manipulation be evaluated beyond headline success rates?

---

## Closing Thought

Manipulation research becomes much more useful when every result is interpreted as a statement about **where the stack is brittle**:

perception, contact, action interface, memory, or adaptation.
