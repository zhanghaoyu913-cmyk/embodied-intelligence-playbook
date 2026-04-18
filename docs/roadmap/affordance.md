<p align="center">
  <img src="../../assets/figures/banner_affordance.svg" alt="Affordance banner" width="100%"/>
</p>

# Affordance Learning

> **Affordance is where semantics becomes executable.** It tells a robot not just what an object is, but what can be done with it, where, and for which task.

<p align="center">
  <img src="../../assets/figures/flow_affordance.svg" alt="Affordance flow" width="92%"/>
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

Affordance learning is the middle layer between perception and action.

It asks:

- what actions are possible on an object
- where the functional regions are
- how task context changes the answer
- how semantic understanding becomes executable constraint

Without affordance structure, a system can classify the object correctly and still touch the wrong place.

---

## Why This Topic Matters

Affordances convert visual understanding into **interaction structure**.

They matter whenever the robot must know:

- where to grasp
- where to pull or push
- which part is a handle, hinge, rim, or support
- how object-to-object relations constrain action
- how language changes what counts as relevant

That makes affordance learning central to grasping, articulation, tool use, and task-conditioned manipulation.

---

## Problem Decomposition

### 1. Representation granularity

Is the output:

- object-level
- part-level
- pixel-wise
- point-wise
- trajectory-level
- language-conditioned

### 2. Task dependence

Does the same region stay useful across different tasks?

### 3. Cross-category transfer

Can affordances transfer across object families?

### 4. Interaction dependence

Is learning passive, interactive, or hybrid?

### 5. Executability

Can the predicted affordance be turned into a contact frame or action without heavy glue code?

---

## Core Technical Routes

### Route A: dense visual affordance prediction

Predict pixel-wise or point-wise affordance labels.

Best for: grasping, pushing, pressing, and region selection.

### Route B: articulated-object actionable regions

Focus on handles, drawers, hinges, lids, and switches.

Best for: household manipulation and part-aware execution.

### Route C: interactive affordance learning

Learn affordances by trying actions, not only from labels.

Best for: discovering hidden kinematics and instance-specific adaptation.

### Route D: semantic correspondence and retrieval-based transfer

Reuse affordances across objects through feature matching and memory retrieval.

Best for: low-data settings and cross-category generalization.

### Route E: language-conditioned affordance

Let instructions change what counts as useful on an object.

Best for: VLA integration and semantic disambiguation.

### Route F: hierarchical affordance plus action models

Use affordance structure to guide action generation downstream.

Best for: manipulation stacks that need interpretable decomposition.

### Representation family matrix

| Representation | What it captures well | Weakness | Best use |
|---|---|---|---|
| pixel-wise affordance | dense visual regions | weak 3D executability | RGB interaction cues |
| point-wise affordance | 3D actionable regions | depends on geometry quality | point-cloud manipulation |
| part graph | articulated structure and relations | annotation heavy | mechanism interaction |
| language-conditioned affordance | task-dependent relevance | hard to execute without geometry | VLA-guided disambiguation |
| interactive affordance | instance-specific executability | expensive data loop | adaptation and hidden kinematics |

---

## Classical Backbone

| Work | Why it still matters | Labels |
|---|---|---|
| [AffordanceNet](https://arxiv.org/abs/1709.07326) | classical object-plus-affordance benchmark | classical, benchmark |
| [Where2Act](https://cs.stanford.edu/~kaichun/where2act/) | actionable-region prediction for articulated objects | classical, reproducible |
| [VAT-Mart](https://hyperplane-lab.github.io/vat-mart/) | interaction-for-perception affordance framework | classical |
| [AdaAfford](https://hyperplane-lab.github.io/AdaAfford/) | few-shot interaction for adapting affordance priors | classical, open-source, reproducible |
| [Robo-ABC](https://tea-lab.github.io/Robo-ABC/) | correspondence-based cross-category affordance transfer | classical, open-source, reproducible |
| [GAPartNet](https://pku-epic.github.io/GAPartNet/) | part-centric perception-manipulation bridge | classical, open-source, benchmark |
| [PartManip](https://pku-epic.github.io/PartManip/) | part-based manipulation benchmark line | classical, open-source, build-path |

---

## Frontier Watchlist (2025-2026)

| Work | Why it matters | Labels |
|---|---|---|
| [A0](https://a-embodied.github.io/A0/) | hierarchical affordance-aware model for general robotic manipulation | frontier-2025-2026 |
| [GLOVER++](https://arxiv.org/abs/2505.11865) | affordance learning from human behavior for manipulation | frontier-2025-2026 |
| [O3Afford](https://arxiv.org/abs/2509.06233) | one-shot 3D object-to-object affordance grounding | frontier-2025-2026 |
| [Learning Affordances at Inference-Time for VLA Models](https://arxiv.org/abs/2510.19752) | directly links affordance inference to VLA-time action decisions | frontier-2025-2026 |
| [PALM](https://arxiv.org/abs/2601.07060) | progress-aware policy learning built on affordance-oriented representations | frontier-2025-2026 |
| [RoboPCA](https://arxiv.org/pdf/2603.07691) | pose-centered affordance learning from human videos | frontier-2025-2026 |
| [PartManip](https://pku-epic.github.io/PartManip/) | part-aware execution as a bridge from affordance to task success | frontier-2025-2026, open-source, build-path |
| [RynnVLA-001](https://github.com/alibaba-damo-academy/RynnVLA-001) | useful adjacent signal for how open VLA stacks may absorb affordance modules | frontier-2025-2026, open-source |

---

## Open-source Projects & Toolchains

| Project | Why it matters | Labels |
|---|---|---|
| [AffordanceNet code](https://github.com/wliu88/affordance_net) | classical dense affordance baseline | open-source, benchmark |
| [AdaAfford](https://github.com/wangyian-me/AdaAffordCode) | adaptation-oriented affordance code | open-source, reproducible |
| [Robo-ABC](https://github.com/TEA-Lab/Robo-ABC) | transfer-based affordance pipeline | open-source, reproducible |
| [GAPartNet](https://github.com/PKU-EPIC/GAPartNet) | part-aware perception tooling | open-source, benchmark |
| [PartManip](https://github.com/PKU-EPIC/PartManip) | affordance-to-manipulation bridge | open-source, build-path |
| [SAPIEN](https://sapien.ucsd.edu/) | articulated-object simulation backbone | simulator, build-path |
| [Open3D](https://www.open3d.org/) | useful for 3D affordance visualization and geometry | build-path |

---

## Datasets / Benchmarks / Simulators

| Resource | Why it matters | Best use |
|---|---|---|
| [PartNet-Mobility](https://sapien.ucsd.edu/browse) | articulated geometry and part structure | actionable regions and mechanism interaction |
| [GAPartNet](https://pku-epic.github.io/GAPartNet/) | part segmentation and embodied perception | part-aware affordance reasoning |
| [PartManip](https://pku-epic.github.io/PartManip/) | benchmark line connecting parts to task execution | affordance-to-action evaluation |
| [AffordanceNet](https://github.com/wliu88/affordance_net) | classical dense affordance labels | RGB affordance prediction |
| [SAPIEN](https://sapien.ucsd.edu/) | articulated simulation | sim-first affordance studies |
| [ManiSkill](https://maniskill.ai/) | manipulation simulation where affordance signals can be tested downstream | task-level evaluation |

---

## Academic Labs & Company Systems

| Node | Why track it | Representative signals |
|---|---|---|
| Berkeley | perception, manipulation, and transfer depth | Robo-ABC-style transfer lines |
| Stanford | articulation and executable interaction focus | Where2Act |
| PKU EPIC ecosystem | part-level datasets and manipulation benchmarks | GAPartNet, PartManip |
| Zhejiang University ecosystem | humanoid and embodied platform growth | useful downstream system signal |
| Shanghai Jiao Tong University | embodied RL and control connections | useful for execution-facing affordance integration |
| Alibaba DAMO | open embodied systems where affordance modules may become deployable | RynnVLA line |

---

## Practical Build Paths

### Build Path A: dense 3D affordance map

Start with point-wise or pixel-wise affordance prediction, then convert regions into local action frames.

### Build Path B: articulated-object interaction

Use PartNet-Mobility, SAPIEN, and Where2Act or AdaAfford-style pipelines for drawers, doors, and handles.

### Build Path C: retrieval-based transfer

Build an affordance memory bank and test cross-category contact transfer.

### Build Path D: affordance-guided manipulation

Insert an affordance module ahead of a manipulation or VLA baseline and measure whether action quality improves.

---

## Common Failure Modes

- affordance maps that look plausible but are hard to execute
- category splits that make transfer look easier than it is
- language-conditioned affordance shown qualitatively without downstream gains
- part labels that do not improve actual robot action
- evaluation too detached from task success

---

## Reading Sequence

### Beginner

1. AffordanceNet
2. Where2Act
3. VAT-Mart

Goal: understand how affordance representations differ across dense labels, actionable points, and interaction-driven formulations.

### Intermediate

1. AdaAfford
2. Robo-ABC
3. GAPartNet
4. PartManip

Goal: study transfer, adaptation, and part-aware execution.

### Advanced

1. A0
2. GLOVER++
3. O3Afford
4. inference-time affordance for VLA

Goal: track how affordances are being pulled into general robotic policy stacks.

---

## Research Radar

Watch these questions now:

- what representation family best suits foundation-model robotics
- how affordances should be scored when downstream task success is the real target
- how much interaction data is needed for instance-specific affordance
- whether affordance becomes a standard module inside VLA systems

---

## Open Questions

- What is the right affordance representation for VLA-era robotics?
- How should object-to-object affordances be represented?
- When do affordance modules outperform stronger end-to-end policies?
- How should affordance quality be evaluated if downstream success is what matters?
- Can affordance reasoning scale across embodiments and tool-use settings?

---

## Related Pages

- [Grasping](grasping.md)
- [Manipulation](manipulation.md)
- [Benchmarks](../resources/benchmarks.md)
- [Grasping + Affordance build path](../build_paths/grasping_affordance.md)
- [Academia Map](../maps/academia.md)
