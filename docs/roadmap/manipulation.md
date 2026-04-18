<p align="center">
  <img src="../../assets/figures/banner_manipulation.svg" alt="Manipulation banner" width="100%"/>
</p>

# Manipulation

> **Manipulation is where embodied AI stops being abstract.** The system has to touch, align, place, recover, and finish.

<p align="center">
  <img src="../../assets/figures/flow_manipulation.svg" alt="Manipulation flow" width="92%"/>
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

Manipulation is the clearest test of whether an embodied system actually works.

It is the point where:

- perception mistakes become contact failures
- timing mistakes become slippage
- weak state representations become task collapse
- brittle policies reveal themselves immediately

A manipulation system is judged by whether it **finishes the task** under clutter, contact, uncertainty, and drift.

---

## Why This Topic Matters

Manipulation is the integration point for almost the whole stack:

- perception
- calibration
- action representation
- force and contact dynamics
- memory
- recovery logic

It is also the place where impressive offline metrics often fail to survive reality.

---

## Problem Decomposition

### 1. Task family

Is the task:

- tabletop or mobile
- single-arm or bimanual
- rigid or articulated
- short-horizon or long-horizon
- tolerant or precision-critical

### 2. Observation

What does the policy actually see?

- fixed RGB
- wrist RGB
- depth
- point cloud
- proprioception
- language
- tactile cues

### 3. Action interface

What is emitted?

- joints
- end-effector deltas
- action chunks
- trajectories
- subskills

### 4. Recovery

Can the system detect and repair:

- bad grasps
- object shifts
- missed subgoals
- controller lag

### 5. Generalization

Does the method survive new objects, layouts, tasks, and embodiments?

---

## Core Technical Routes

### Route A: behavior cloning and imitation learning

Still the fastest route to useful manipulation baselines.

Best for: teleoperated data and low-cost real robots.

### Route B: diffusion policies

Strong when the task admits multiple valid action sequences.

Best for: robust visuomotor control.

### Route C: in-context and foundation-style manipulation

Treat manipulation as sequence modeling over large sensorimotor corpora.

Best for: generalist policy comparison and few-shot adaptation.

### Route D: mobile and whole-body manipulation

Extend from fixed-base control to room-scale embodied systems.

Best for: household tasks and humanoid/mobile-manipulator systems.

### Route E: planning plus policy hybrids

Use explicit subgoal or planner structure when a single policy is too opaque.

Best for: long-horizon and interpretable execution.

### Representative systems matrix

| System | Main strength | Action style | Best use |
|---|---|---|---|
| ACT | action chunking | chunked low-level action | low-cost real-robot baselines |
| Diffusion Policy | multimodal action generation | diffusion over action sequences | robust tabletop control |
| Mobile ALOHA | practical mobile manipulation system | teleop plus imitation | buildable real-robot path |
| TidyBot++ | integrated household manipulation stack | mobile manipulation system loop | open system reference |
| Octo | generalist policy baseline | foundation-style policy | reproducible comparison |
| OpenVLA | open VLA manipulation baseline | direct visuomotor control | language-conditioned experiments |
| pi0 | integrated generalist robot policy | general-purpose policy stack | frontier system analysis |
| Helix 02 | full-body humanoid manipulation | whole-body action sequence | industrial whole-body signal |

---

## Classical Backbone

| Work | Why it still matters | Labels |
|---|---|---|
| [ACT](https://github.com/tonyzhaozh/act) | practical action-chunking baseline | classical, open-source, reproducible, beginner-friendly, build-path |
| [Mobile ALOHA](https://src.stanford.edu/demo/moble-aloha) | low-cost mobile manipulation with outsized practical impact | classical, build-path |
| [Diffusion Policy](https://diffusion-policy.cs.columbia.edu/) | influential policy parameterization for visuomotor control | classical |
| [OpenVLA](https://openvla.github.io/) | open VLA baseline heavily used in manipulation workflows | classical, open-source, reproducible |
| [Octo](https://octo-models.github.io/) | open generalist robot policy | classical, open-source, reproducible |
| [pi0](https://www.physicalintelligence.company/blog/pi0) | general-purpose robot policy framing | classical, industrial-signal |
| [robomimic](https://robomimic.github.io/) | practical imitation-learning baseline ecosystem | classical, open-source, beginner-friendly, build-path |
| [BridgeData V2](https://rail-berkeley.github.io/bridgedata/) | important manipulation data anchor | classical, open-source |

---

## Frontier Watchlist (2025-2026)

| Work | Why it matters | Labels |
|---|---|---|
| [ICRT](https://icrt.dev/) | in-context imitation learning over sensorimotor trajectories | frontier-2025-2026 |
| [Helix 02](https://www.figure.ai/news/helix-02) | full-body autonomy signal, not only tabletop control | frontier-2025-2026, industry-system, industrial-signal |
| [Gemini Robotics](https://deepmind.google/models/gemini-robotics/) | broader reasoning-to-manipulation frontier push | frontier-2025-2026, industrial-signal |
| [Isaac GR00T N1](https://developer.nvidia.com/isaac/gr00t) | humanoid manipulation and platform signal | frontier-2025-2026, industrial-signal |
| [Seed GR-3](https://seed.bytedance.com/GR3) | generalist manipulation with large-scale VLA framing | frontier-2025-2026, industrial-signal |
| [GR-RL](https://seed.bytedance.com/en/gr_rl) | dexterous RL refinement for long-horizon manipulation | frontier-2025-2026, industrial-signal |
| [RynnVLA-001](https://github.com/alibaba-damo-academy/RynnVLA-001) | open embodied release from a major industrial lab | frontier-2025-2026, open-source, reproducible |
| [TidyBot++](https://tidybot2.github.io/) | open mobile-manipulation system with strong documentation | frontier-2025-2026, open-source, build-path |

---

## Open-source Projects & Toolchains

| Project | Why it matters | Labels |
|---|---|---|
| [robomimic](https://robomimic.github.io/) | strongest BC-first baseline stack | open-source, reproducible, beginner-friendly, build-path |
| [LeRobot](https://huggingface.co/docs/lerobot/index) | clean path from data to low-cost hardware | open-source, beginner-friendly, build-path |
| [ACT](https://github.com/tonyzhaozh/act) | practical real-robot imitation baseline | open-source, reproducible, build-path |
| [OpenVLA](https://github.com/openvla/openvla) | open VLA comparison baseline | open-source, reproducible |
| [Octo](https://github.com/octo-models/octo) | open generalist policy baseline | open-source, reproducible |
| [Diffusion Policy](https://diffusion-policy.cs.columbia.edu/) | strong manipulation-policy family | open-source |
| [TidyBot++ docs](https://tidybot2.github.io/docs/) | unusually useful system-level documentation | industry-system, build-path |

---

## Datasets / Benchmarks / Simulators

| Resource | Why it matters | Best use |
|---|---|---|
| [CALVIN](https://github.com/mees/calvin) | long-horizon language-conditioned manipulation | VLA and closed-loop evaluation |
| [LIBERO](https://libero-project.github.io/main.html) | compositional and lifelong manipulation | transfer and continual-learning studies |
| [BEHAVIOR-1K](https://behavior.stanford.edu/index.html) | household-scale activity breadth | system-level generalization |
| [Meta-World](https://meta-world.github.io/) | controlled baseline tasks | fast algorithm comparison |
| [BridgeData V2](https://rail-berkeley.github.io/bridgedata/) | practical demonstration corpus | imitation and fine-tuning |
| [ManiSkill](https://maniskill.ai/) | scalable manipulation simulation | benchmark-first and sim-first work |

---

## Academic Labs & Company Systems

| Node | Why track it | Representative signals |
|---|---|---|
| Stanford | home and mobile manipulation systems | Mobile ALOHA, TidyBot, BEHAVIOR |
| Berkeley | manipulation learning and robot data | BridgeData, Octo ecosystem |
| Columbia | diffusion-policy and visuomotor manipulation line | Diffusion Policy |
| Carnegie Mellon | broad manipulation and robotics systems depth | embodied systems labs |
| Figure | whole-body and humanoid manipulation system signal | Helix line |
| NVIDIA | humanoid platform plus simulator infrastructure | GR00T, Isaac Lab |
| ByteDance Seed | VLA plus RL refinement for dexterous manipulation | GR-3, GR-RL |
| Alibaba DAMO | open embodied systems worth tracking | RynnVLA line |

---

## Practical Build Paths

### Build Path A: low-cost real robot route

Use [Real Robot build path](../build_paths/real_robot.md) with ACT, LeRobot, or robomimic on one narrow skill family.

### Build Path B: simulation-first route

Use ManiSkill or Meta-World with a strong BC or diffusion baseline before adding frontier complexity.

### Build Path C: benchmark-first route

Use CALVIN or LIBERO to compare a small set of policy families under consistent evaluation.

### Build Path D: foundation-policy comparison route

Compare OpenVLA, Octo, and a simpler imitation baseline on the same task family.

---

## Common Failure Modes

- impressive offline scores with weak real-world calibration
- grasp failures hidden inside manipulation claims
- no recovery loop for partial task completion
- controller and action-rate issues treated as model issues
- overclaiming generality from narrow object families

---

## Reading Sequence

### Beginner

1. robomimic
2. ACT
3. Mobile ALOHA

Goal: build intuition for execution loops before chasing model scale.

### Intermediate

1. Diffusion Policy
2. OpenVLA
3. Octo
4. BridgeData V2

Goal: compare policy parameterizations and data assumptions.

### Advanced

1. ICRT
2. Helix line
3. GR00T line
4. GR-RL

Goal: inspect whole-body, in-context, and post-training trends.

---

## Research Radar

Watch these questions now:

- how much whole-body manipulation changes model design
- whether in-context robot learning becomes a standard baseline
- how far low-cost hardware can go with strong data loops
- what role RL should play after imitation or VLA pretraining

---

## Open Questions

- What is the best action interface for long-horizon manipulation?
- When do diffusion policies outperform chunked action models in practice?
- How should manipulation benchmarks measure recovery rather than single-pass success?
- Can whole-body and tabletop manipulation share one policy trunk?
- What is the minimum real-robot data needed once pretraining becomes stronger?

---

## Related Pages

- [VLA](vla.md)
- [Grasping](grasping.md)
- [Benchmarks](../resources/benchmarks.md)
- [Real Robot build path](../build_paths/real_robot.md)
- [Sim-to-Real build path](../build_paths/sim2real.md)
