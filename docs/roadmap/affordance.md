<p align="center">
  <img src="../../assets/figures/banner_affordance.svg" alt="Affordance banner" width="100%"/>
</p>

# Affordance Learning

> **Affordance is where semantics becomes executable.** It tells a robot not just what an object is, but what can be done with it, where, and for which task.

<p align="center">
  <img src="../../assets/figures/flow_affordance.svg" alt="Affordance flow" width="92%"/>
</p>

---

## Topic Thesis

Affordance learning is the missing middle layer between perception and action.

It asks:
- what actions are possible on an object?
- where are the functional regions for those actions?
- how does the answer change with task context?
- how do semantic labels become executable robot constraints?

A perception system without affordances may identify the object correctly and still choose the wrong place to touch.

---

## Why it matters

Affordance representations help turn visual understanding into **actionable interaction structure**.

They matter whenever the robot must know:
- where to grasp
- where to pull or push
- which part is a handle, lid, rim, hinge, or support surface
- how object-to-object relationships affect action
- how language changes which region is relevant

Affordance is therefore central to:
- grasping
- articulated-object manipulation
- tool use
- part-based interaction
- task-conditioned action selection

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
Does the same object region mean the same thing across tasks?

### 3. Cross-category transfer
Can an affordance learned on one object family transfer to another?

### 4. Interaction dependence
Does the system learn only from observation, or also from trying actions?

### 5. Executability
Can the predicted affordance be converted into a grasp, push point, contact frame, or trajectory without manual glue code?

---

## Core Technical Routes

### Route A — dense visual affordance prediction
Predict pixel-wise or point-wise affordance labels.

**Good for**
- grasping
- pressing
- lifting
- region selection
- dense supervision settings

---

### Route B — articulated-object actionable regions
Focus on movable parts such as handles, doors, drawers, lids, and switches.

**Good for**
- household manipulation
- mechanism interaction
- part-aware policies

---

### Route C — interactive affordance learning
Learn affordances by trying actions, not only observing labels.

**Good for**
- discovering hidden kinematics
- richer generalization
- instance-specific adaptation

---

### Route D — semantic correspondence and retrieval-based transfer
Use feature matching or memory retrieval to transfer affordances to novel categories.

**Good for**
- low-data settings
- out-of-category generalization
- object-to-object or task-to-task reuse

---

### Route E — language-conditioned affordance
Let instructions change what counts as “useful” on an object.

**Good for**
- task-conditioned manipulation
- semantic disambiguation
- VLA integration

---

### Route F — hierarchical affordance + action models
Use affordances to guide lower-level action generation.

**Good for**
- manipulation stacks
- longer-horizon execution
- interpretable decomposition

---

## Frontier Watchlist (2025–2026)

| Work | Why it matters | Links |
|---|---|---|
| A0 (2025) | hierarchical affordance-aware model for general robotic manipulation | [paper](https://arxiv.org/abs/2504.12636) · [project](https://a-embodied.github.io/A0/) |
| GLOVER++ (2025) | learns affordances from human behaviors for robotic manipulation | [paper](https://arxiv.org/abs/2505.11865) |
| O$^3$Afford (2025) | one-shot 3D object-to-object affordance grounding for generalizable manipulation | [paper](https://arxiv.org/abs/2509.06233) |
| Learning Affordances at Inference-Time for VLA Models (2025) | directly connects affordance inference to VLA-time decision-making | [paper](https://arxiv.org/abs/2510.19752) |
| PALM (2026) | progress-aware policy learning built on affordance-oriented representations | [paper](https://arxiv.org/abs/2601.07060) |
| RoboPCA (2026) | pose-centered affordance learning from human videos for zero-shot manipulation | [paper](https://arxiv.org/pdf/2603.07691) |

---

## Classical Backbone

| Work | Why it matters | Links |
|---|---|---|
| AffordanceNet | classical object + affordance benchmark for dense RGB prediction | [paper](https://arxiv.org/abs/1709.07326) · [code](https://github.com/wliu88/affordance_net) |
| Where2Act | highly influential actionable-region prediction for articulated objects | [project](https://cs.stanford.edu/~kaichun/where2act/) |
| VAT-Mart | interaction-for-perception framework with action trajectories | [project](https://hyperplane-lab.github.io/vat-mart/) |
| AdaAfford | few-shot test-time interaction for adapting affordance priors | [project](https://hyperplane-lab.github.io/AdaAfford/) · [code](https://github.com/wangyian-me/AdaAffordCode) |
| Robo-ABC | semantic-correspondence route to cross-category affordance transfer | [project](https://tea-lab.github.io/Robo-ABC/) · [code](https://github.com/TEA-Lab/Robo-ABC) |
| GAPartNet | part-centric dataset and perception-manipulation bridge | [project](https://pku-epic.github.io/GAPartNet/) · [code](https://github.com/PKU-EPIC/GAPartNet) |
| PartManip | part-based manipulation benchmark and policy line | [project](https://pku-epic.github.io/PartManip/) · [code](https://github.com/PKU-EPIC/PartManip) |

---

## Datasets, Simulators, and Nearby Resources

### Core datasets and resources
- [PartNet-Mobility](https://sapien.ucsd.edu/browse)
- [SAPIEN](https://sapien.ucsd.edu/)
- [GAPartNet](https://pku-epic.github.io/GAPartNet/)
- [PartManip](https://pku-epic.github.io/PartManip/)
- [AffordanceNet](https://github.com/wliu88/affordance_net)

### Useful nearby toolchains
- [Open3D](https://www.open3d.org/)
- [PyTorch3D](https://pytorch3d.org/)
- [LeRobot](https://huggingface.co/docs/lerobot/index)

These are not affordance-specific, but they matter in practice when building 3D perception, interaction maps, and execution pipelines.

---

## Practical Reading Sequence

### Step 1 — learn the representation families
1. AffordanceNet  
2. Where2Act  
3. VAT-Mart  

**Goal**  
Understand how affordance prediction differs across pixel-wise, actionable-point, and interaction-centric formulations.

---

### Step 2 — study adaptation and transfer
1. AdaAfford  
2. Robo-ABC  
3. GAPartNet  
4. PartManip  

**Goal**  
Understand how affordances transfer across unseen categories, parts, and objects.

---

### Step 3 — inspect the 2025–2026 frontier
1. A0  
2. GLOVER++  
3. O³Afford  
4. Learning Affordances at Inference-Time for VLA Models  
5. PALM  
6. RoboPCA  

**Goal**  
Track how affordances are now being connected more tightly to manipulation, VLA, and policy learning.

---

## Build Paths

### Build Path A — dense 3D affordance map
Mesh or point cloud → dense point-wise affordance prediction → weighted center / PCA / local frame extraction → downstream robot action.

**Best for**
- grasping
- point-cloud manipulation
- geometric interaction studies

---

### Build Path B — articulated-object interaction
PartNet-Mobility / SAPIEN → Where2Act or AdaAfford-style pipeline → handle / hinge / drawer interaction.

**Best for**
- cabinets
- switches
- doors
- household articulated objects

---

### Build Path C — retrieval-based transfer
Create an affordance memory bank → retrieve by semantic and geometric features → transfer contact priors to new objects.

**Best for**
- scarce labeled data
- cross-category generalization
- out-of-category manipulation

---

### Build Path D — affordance-guided VLA / manipulation
Affordance module → VLA or manipulation policy → compare with a language-only or object-only baseline.

**Best for**
- testing whether affordances really improve downstream action
- task-conditioned interaction
- interpretability in manipulation stacks

---

## What to inspect in an affordance paper

- whether labels are part-based, pixel-based, point-wise, trajectory-based, or language-conditioned
- whether multiple affordances can overlap on one object
- whether the output can be turned into a robot action without heavy manual glue code
- whether the paper studies transfer across object categories
- whether the method depends on object-part supervision that is unrealistic at deployment time
- whether interaction data is required or only passive observation

---

## Common Failure Modes

- affordance maps look semantically plausible but are hard to execute
- cross-category transfer is overstated under easy category splits
- language-conditioned affordance is shown qualitatively but not connected to actual action gains
- the representation ignores object-to-object relations
- part labels are strong, but robot-side execution remains weak
- evaluation is separated too cleanly from downstream manipulation success

---

## Open Questions

- What is the right affordance representation for foundation-model robotics: dense maps, latent slots, or language-queryable memory?
- How should object-to-object affordances be represented for manipulation involving pairs or tool-object relations?
- Can affordance learning become a standard plug-in layer for VLA systems?
- How much interaction is needed to make affordance predictions truly instance-specific?
- How should affordance quality be measured when downstream success is the real target?

---

## Closing Thought

Affordance learning becomes truly valuable when it does not stop at annotation quality, but continues all the way to **action selection and execution geometry**.
