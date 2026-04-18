<p align="center">
  <img src="../../assets/figures/banner_grasping.svg" alt="Grasping banner" width="100%"/>
</p>

# Grasping

> **Grasping is not only about contact.** It is about choosing contact that keeps the rest of the task possible.

<p align="center">
  <img src="../../assets/figures/flow_grasping.svg" alt="Grasping flow" width="92%"/>
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

A useful grasping system answers three questions together:

1. where can I contact the object
2. will that contact be stable
3. does that contact help the downstream task

That is why modern grasping is not only geometry estimation. It is also scene reasoning, task awareness, active perception, and execution monitoring.

---

## Why This Topic Matters

Grasping is the gateway between perception and physical interaction.

A weak grasping stack breaks everything downstream:

- pick-and-place becomes inconsistent
- articulation starts from the wrong contact
- long-horizon tasks fail before they begin
- policy quality is blamed for what is really contact failure

Good grasping is therefore not just about holding. It is about **holding in service of the next action**.

---

## Problem Decomposition

### 1. Candidate generation

Where are plausible contacts?

### 2. Stability estimation

Which candidates are likely to succeed physically?

### 3. Task awareness

Which grasp suits lifting, placing, pouring, cutting, handover, or articulation?

### 4. Scene uncertainty

How does the system handle occlusion, clutter, transparency, and partial depth?

### 5. Execution monitoring

Can it detect and repair failure during the approach or after contact?

---

## Core Technical Routes

### Route A: analytical and geometry-driven methods

Still useful as intuition and baseline.

Best for: interpretable contact reasoning and simple scenes.

### Route B: proposal plus ranking pipelines

Generate grasp candidates, then score them.

Best for: practical engineering stacks and debuggability.

### Route C: point-cloud end-to-end grasp prediction

Best for: modern RGB-D and 6-DoF grasping in cluttered scenes.

### Route D: implicit, volumetric, and reconstruction-aware grasping

Best for: richer geometry reasoning and single-view reconstruction settings.

### Route E: dexterous grasping

Best for: multi-finger hands and humanoid dexterity.

### Route F: active-perception and closed-loop grasping

Best for: partial observation, difficult clutter, and uncertainty-aware execution.

### Benchmark-to-system map

| Benchmark or resource | What it measures well | Closest deployable system use |
|---|---|---|
| GraspNet | cluttered-scene 6-DoF grasp prediction | warehouse or tabletop pick pipelines |
| DexGraspNet | dexterous contact modeling | multi-finger hand research |
| TransCG | transparent-object sensing robustness | household and industrial difficult-object handling |
| PartNet-Mobility | contact that serves articulation | drawers, doors, handles, mechanism interaction |

---

## Classical Backbone

| Work | Why it still matters | Labels |
|---|---|---|
| [GraspNet](https://graspnet.net/) | standard benchmark ecosystem for 6-DoF grasping | classical, benchmark |
| [Contact-GraspNet](https://contact-graspnet.github.io/) | influential point-cloud grasp estimation line | classical, open-source, reproducible |
| [AnyGrasp](https://graspnet.net/anygrasp.html) | practical real-time grasping system | classical, build-path |
| [GPD](https://github.com/atenpas/gpd) | classic proposal-and-ranking pipeline | classical, open-source, beginner-friendly, build-path |
| [VGN](https://github.com/ethz-asl/vgn) | strong volumetric clutter-grasping baseline | classical, open-source, reproducible |
| [GIGA](https://github.com/UT-Austin-RPL/GIGA) | implicit-geometry route into grasp prediction | classical, open-source, reproducible |
| [PointNetGPD](https://github.com/lianghongzhuo/PointNetGPD) | point-set grasp evaluation baseline | classical, open-source |
| [DexGraspNet](https://pku-epic.github.io/DexGraspNet/) | major dexterous grasp dataset | classical, benchmark |

---

## Frontier Watchlist (2025-2026)

Grasping has fewer headline foundation-model releases than VLA, so the real frontier is defined by what moves deployment quality, dexterity, and uncertainty handling.

| Work | Why it matters | Labels |
|---|---|---|
| [DexGraspNet 2.0](https://pku-epic.github.io/DexGraspNet2.0/) | larger cluttered dexterous benchmark | frontier-2025-2026, benchmark |
| [TransCG](https://graspnet.net/transcg) | difficult transparent-object grasping regime | frontier-2025-2026, benchmark |
| [Neural Graspness Fields](https://proceedings.neurips.cc/paper_files/paper/2024/file/4364fef031fdf7bfd9d1c9c56b287084-Paper-Conference.pdf) | active perception for grasp detection | frontier-2025-2026 |
| [Implicit Grasp Diffusion](https://openreview.net/forum?id=VUhlMfEekm) | diffusion-based grasp generation signal | frontier-2025-2026 |
| [ROS2 GPD wrappers](https://github.com/socrob/grasp_detection_ros2) | shows classical pipelines still matter in production-style integration | frontier-2025-2026, open-source, build-path |
| [GR00T](https://developer.nvidia.com/isaac/gr00t) | important adjacent signal because dexterous humanoid stacks need stronger grasping modules | frontier-2025-2026, industrial-signal |
| [GR-RL](https://seed.bytedance.com/en/gr_rl) | useful adjacent signal for dexterous refinement after initial contact skills | frontier-2025-2026, industrial-signal |
| [PartManip](https://pku-epic.github.io/PartManip/) | contact that serves articulated-object manipulation rather than only stable lift | frontier-2025-2026, build-path |

---

## Open-source Projects & Toolchains

| Project | Why it matters | Labels |
|---|---|---|
| [GraspNet baseline ecosystem](https://graspnet.net/) | benchmark, data, and baseline alignment | open-source, benchmark, build-path |
| [Contact-GraspNet](https://github.com/NVlabs/contact_graspnet) | strong point-cloud baseline | open-source, reproducible, build-path |
| [GPD](https://github.com/atenpas/gpd) | practical proposal stack | open-source, beginner-friendly, build-path |
| [VGN](https://github.com/ethz-asl/vgn) | volumetric grasping baseline | open-source, reproducible |
| [GIGA](https://github.com/UT-Austin-RPL/GIGA) | implicit geometry and grasp affordance | open-source, reproducible |
| [DexGraspNet](https://github.com/PKU-EPIC/DexGraspNet) | dexterous benchmark tooling | open-source, benchmark |
| [SAPIEN](https://sapien.ucsd.edu/) | articulation and scene interaction support | simulator, build-path |

---

## Datasets / Benchmarks / Simulators

| Resource | Why it matters | Best use |
|---|---|---|
| [GraspNet](https://graspnet.net/) | standard cluttered-scene benchmark | parallel-jaw and 6-DoF grasping |
| [DexGraspNet](https://pku-epic.github.io/DexGraspNet/) | dexterous grasp dataset | multi-finger grasping |
| [DexGraspNet 2.0](https://pku-epic.github.io/DexGraspNet2.0/) | harder dexterous clutter settings | frontier dexterity |
| [TransCG](https://graspnet.net/transcg) | transparent-object benchmark | sensing robustness |
| [PartNet-Mobility](https://sapien.ucsd.edu/browse) | articulation context for downstream contact choice | task-oriented grasping |
| [SAPIEN](https://sapien.ucsd.edu/) | simulator support for articulated interaction | sim-first grasping and articulation |

---

## Academic Labs & Company Systems

| Node | Why track it | Representative signals |
|---|---|---|
| Berkeley | grasping, manipulation, and robot learning depth | grasping and manipulation ecosystem |
| University of Washington | perception-to-grasping pipeline strength | Dieter Fox and embodied perception line |
| Carnegie Mellon | broad robotics systems and manipulation depth | systems-side interaction work |
| NVIDIA | dexterous and humanoid-adjacent manipulation stack | GR00T ecosystem |
| PKU EPIC ecosystem | dexterous and part-aware manipulation benchmarks | DexGraspNet, GAPartNet, PartManip |
| Stanford | grasping as part of larger household-manipulation systems | Mobile ALOHA, TidyBot context |

---

## Practical Build Paths

### Build Path A: practical parallel-jaw stack

Use GraspNet, Contact-GraspNet, or AnyGrasp with a simple pick-and-place controller.

### Build Path B: cluttered-scene research stack

Use VGN or GIGA on cluttered scenes, then add active perception or better uncertainty handling.

### Build Path C: task-oriented grasping stack

Combine contact prediction with task scoring so the selected grasp helps the next action, not only the lift.

### Build Path D: dexterous-hand route

Use DexGraspNet and DexGraspNet 2.0 to study multi-finger contact reasoning.

---

## Common Failure Modes

- stable grasps that block the downstream task
- point-cloud quality quietly determining most results
- clutter claims made on easy object families
- offline grasp ranking that does not survive controller integration
- transparent or reflective objects breaking the sensing stack

---

## Reading Sequence

### Beginner

1. GraspNet
2. Contact-GraspNet
3. AnyGrasp

Goal: understand benchmark assumptions and practical inference loops.

### Intermediate

1. GPD
2. VGN
3. GIGA

Goal: compare classical, volumetric, and implicit-geometry families.

### Advanced

1. DexGraspNet line
2. TransCG
3. active-perception grasping

Goal: move beyond stable lift toward uncertainty, dexterity, and downstream utility.

---

## Research Radar

Watch these questions now:

- how grasping should be scored jointly with downstream task success
- whether dexterous grasping becomes standard as humanoid stacks mature
- how much active perception should replace single-shot prediction
- where semantics genuinely help grasp choice rather than only object localization

---

## Open Questions

- How should grasping and manipulation be evaluated jointly?
- What is the best bridge between parallel-jaw and dexterous-hand pipelines?
- How uncertainty-aware should grasping systems become before contact?
- Can task-oriented grasping benchmarks become more standard than pure lift metrics?
- How much can VLA-style semantics materially help contact selection?

---

## Related Pages

- [Manipulation](manipulation.md)
- [Affordance](affordance.md)
- [Benchmarks](../resources/benchmarks.md)
- [Grasping + Affordance build path](../build_paths/grasping_affordance.md)
- [Academia Map](../maps/academia.md)
