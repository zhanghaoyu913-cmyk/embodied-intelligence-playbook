<p align="center">
  <img src="../../assets/figures/banner_grasping.svg" alt="Grasping banner" width="100%"/>
</p>

# Grasping

> **Grasping is not only about contact.** It is about choosing a contact that makes the next part of the task possible.

<p align="center">
  <img src="../../assets/figures/flow_grasping.svg" alt="Grasping flow" width="92%"/>
</p>

---

## Topic Thesis

A useful grasping system must answer three questions together:

1. **Where can I contact the object?**
2. **Will that grasp be stable?**
3. **Is it the right grasp for the downstream task?**

That is why modern grasping is not just geometry estimation.  
It is also:
- scene reasoning
- partial-observation handling
- task conditioning
- active perception
- execution monitoring

---

## Why grasping matters

Grasping is the gateway from perception to physical interaction.

A weak grasping stack causes downstream failures everywhere:
- pick-and-place becomes inconsistent
- articulated-object manipulation starts from the wrong contact
- pouring fails because the chosen grasp blocks the next action
- long-horizon manipulation fails before it begins

Good grasping is therefore not only about “holding”; it is about **holding in the service of a longer task**.

---

## Problem Decomposition

### 1. Candidate generation
Where are plausible contacts?

### 2. Stability estimation
Which candidates are likely to succeed?

### 3. Task awareness
Which grasp is compatible with:
- lifting
- placing
- pouring
- cutting
- handing over
- opening articulated objects

### 4. Scene uncertainty
How do we handle:
- occlusion
- clutter
- transparent objects
- partial depth
- deformable contact surfaces

### 5. Real-time execution
Can the system detect and correct failure during execution?

---

## Core Technical Routes

### Route A — analytical and geometry-driven methods
Still useful as intuition and baseline.

**Good for**
- simple scenes
- physically interpretable contacts
- grasp wrench / closure reasoning

---

### Route B — proposal + ranking pipelines
Generate candidates, then score them.

**Good for**
- practical engineering stacks
- integrating multiple cues
- strong debugging visibility

**Representative systems**
- GPD
- proposal-based 6-DoF pipelines

---

### Route C — point-cloud end-to-end grasp prediction
A major route for modern cluttered-scene grasping.

**Good for**
- RGB-D or point-cloud robotics
- 6-DoF grasp detection
- real-time scene-conditioned inference

**Representative systems**
- GraspNet baseline ecosystem
- Contact-GraspNet
- AnyGrasp

---

### Route D — implicit / volumetric / reconstruction-aware grasping
Blend geometry reconstruction with grasp scoring.

**Good for**
- single-view reconstruction
- cluttered scenes
- richer scene representation

**Representative systems**
- GIGA
- VGN and related TSDF-based methods

---

### Route E — dexterous grasping
Important when parallel-jaw assumptions break down.

**Good for**
- multi-finger hands
- dexterous manipulation
- future humanoid and hand-centric systems

---

### Route F — active perception and closed-loop grasping
Choose better views or update the grasp online.

**Good for**
- partial observation
- target-driven grasping
- real-world clutter removal

---

## Frontier Watchlist (2024–2026)

Grasping has fewer fully open 2025–2026 “headline foundation-model” releases than VLA, so this watchlist deliberately mixes recent high-value work from 2024 onward.

| Work | Why it matters | Links |
|---|---|---|
| DexGraspNet 2.0 (2024/2025) | large-scale synthetic benchmark for dexterous grasping in clutter | [project](https://pku-epic.github.io/DexGraspNet2.0/) · [code](https://github.com/PKU-EPIC/DexGraspNet2) |
| Active Perception for Grasp Detection via Neural Graspness Fields (2024) | pushes grasping beyond passive single-shot perception | [paper](https://proceedings.neurips.cc/paper_files/paper/2024/file/4364fef031fdf7bfd9d1c9c56b287084-Paper-Conference.pdf) |
| Implicit Grasp Diffusion (2024) | bridges dense local features with diffusion-based grasp generation | [openreview](https://openreview.net/forum?id=VUhlMfEekm) |
| Transparent-object grasping via TransCG | important for real-world difficult sensing regimes | [project](https://graspnet.net/transcg) |
| ROS2 GPD wrappers and modernized ecosystems (2025+) | signals continuing engineering relevance of classical pipelines | [repo](https://github.com/socrob/grasp_detection_ros2) |

---

## Canonical Resources

| Resource | Why it matters | Links |
|---|---|---|
| GraspNet | large-scale benchmark and baseline ecosystem for 6-DoF grasping | [project](https://graspnet.net/) |
| Contact-GraspNet | influential point-cloud-based 6-DoF grasp estimation | [project](https://contact-graspnet.github.io/) · [code](https://github.com/NVlabs/contact_graspnet) |
| AnyGrasp | practical real-time grasp detection system | [official](https://graspnet.net/anygrasp.html) |
| GPD | classic candidate-generation + ranking baseline | [code](https://github.com/atenpas/gpd) |
| VGN | real-time volumetric grasp detection in clutter | [code](https://github.com/ethz-asl/vgn) |
| GIGA | combines implicit geometry with grasp affordance prediction | [code](https://github.com/UT-Austin-RPL/GIGA) |
| DexGraspNet | large-scale dexterous grasp dataset | [project](https://pku-epic.github.io/DexGraspNet/) · [code](https://github.com/PKU-EPIC/DexGraspNet) |
| PointNetGPD | strong point-set-based grasp evaluation baseline | [code](https://github.com/lianghongzhuo/PointNetGPD) |

---

## Datasets and Benchmarks

### Core grasping resources
- [GraspNet](https://graspnet.net/)
- [DexGraspNet](https://pku-epic.github.io/DexGraspNet/)
- [DexGraspNet 2.0](https://pku-epic.github.io/DexGraspNet2.0/)
- [TransCG](https://graspnet.net/transcg)

### Useful nearby resources
- [PartNet-Mobility](https://sapien.ucsd.edu/browse)
- [SAPIEN](https://sapien.ucsd.edu/)
- [GAPartNet](https://pku-epic.github.io/GAPartNet/)

These are not grasp-only resources, but they matter when grasping must serve articulation, part interaction, or downstream manipulation.

---

## Practical Reading Sequence

### Step 1 — understand the benchmark
Start with:
1. GraspNet
2. Contact-GraspNet
3. AnyGrasp

**Goal**
Understand data representation, grasp metrics, and the difference between benchmark success and real-robot deployment.

---

### Step 2 — compare two families
- proposal-based / geometry-driven methods
- end-to-end learned point-cloud or volumetric methods

**Good comparisons**
- GPD vs Contact-GraspNet
- VGN vs GIGA

---

### Step 3 — go beyond stable grasping
Study:
- task-oriented grasping
- dexterous grasping
- active perception
- transparent-object grasping

---

## Build Paths

### Build Path A — practical parallel-jaw stack
Object segmentation → grasp proposal → geometric or learned scoring → controller → visualization.

**Suggested stack**
GraspNet / Contact-GraspNet / AnyGrasp + real-scene visualization.

---

### Build Path B — cluttered-scene research stack
RGB-D / point cloud → VGN or GIGA → evaluate on clutter removal → add active perception.

**Best for**
- research on scene uncertainty
- stronger geometry reasoning

---

### Build Path C — task-oriented grasping stack
Affordance map or task description → grasp candidate generation → joint task score + geometry score.

**Best for**
- manipulation pipelines
- pouring, handover, cutting, articulated tasks
- research that links grasping to downstream success

---

### Build Path D — dexterous-hand route
DexGraspNet → DexGraspNet 2.0 → multi-finger grasp modeling and contact reasoning.

**Best for**
- hand manipulation
- humanoid dexterity
- future grasp-to-manipulation integration

---

## What to inspect in any grasping result

- whether grasp success is evaluated only at lift time or also after the downstream task
- how partial observation is handled
- whether the method uses single-view or multi-view assumptions
- whether grasp width / orientation / collision are explicitly modeled
- whether the system is robust to scene clutter and transparent or reflective objects
- whether failed grasps are diagnosed or simply discarded

---

## Common Failure Modes

- stable grasps are proposed, but the grasp blocks the downstream task
- point-cloud quality quietly determines most of the result
- clutter performance is overstated with easy object sets
- candidate grasp ranking is good offline but poorly integrated with the controller
- transparent or reflective objects break the sensing stack
- grasp success is separated from task success too rigidly

---

## Open Questions

- How should grasping and manipulation be scored jointly, not separately?
- Can foundation-model semantics materially help grasp selection, or only object localization?
- What is the right bridge between parallel-jaw grasping and dexterous grasping?
- How much should grasping rely on active perception rather than single-shot inference?
- Can grasping systems become more self-aware about uncertainty and failure before contact?

---

## Closing Thought

The strongest grasp is not the one that merely holds.  
It is the one that **holds in the service of a longer action**.
