# Recommended Tool Stacks

> These are not the only valid stacks. They are **practical starting points**.

## 1. Fast prototyping stack

**Use when**: you want a quick perception-to-training prototype.

- Florence-2
- SAM 2.1 or SAM 3
- Depth Anything V2
- CVAT
- LeRobot
- W&B
- Rerun

**Why this works**
- easy prompting
- easy masks
- easy depth prior
- short path from data to training

---

## 2. Open-vocabulary manipulation stack

**Use when**: language-conditioned object grounding matters.

- Grounding DINO 1.5
- SAM 3
- FoundationPose
- MoveIt 2
- Rerun

**Why this works**
- language → boxes
- boxes/text → masks
- masks/object → pose
- pose → motion planning

---

## 3. World-model / trace-learning stack

**Use when**: you care about temporal structure and cross-embodiment signals.

- DINOv3
- CoTracker3
- TAPIR
- DUSt3R or VGGT
- Rerun
- Isaac Lab

**Why this works**
- strong visual features
- strong temporal tracks
- geometry priors
- simulator support
- timeline-friendly visualization

---

## 4. Manipulation research stack

**Use when**: your main target is manipulation benchmarks and imitation/RL.

- SAM 2.1 / SAM 3
- FoundationPose
- ManiSkill 3
- robomimic
- LeRobot
- MoveIt 2
- W&B

**Why this works**
- perception
- pose
- manipulation simulator
- imitation baseline
- practical real-robot path
- deployment bridge

---

## 5. Humanoid / embodied simulation stack

**Use when**: you care about humanoids, HRI, or embodied simulation at scale.

- Isaac Lab
- Habitat 3.0
- Rerun
- W&B
- ROS 2

**Why this works**
- strong learning framework
- strong humanoid/HRI simulator
- experiment and systems visibility

---

## 6. Data-engineering stack

**Use when**: your bottleneck is annotation and dataset quality.

- CVAT
- Label Studio
- FiftyOne
- Florence-2 or Grounding DINO 1.5 for pre-labeling
- Rerun for multimodal inspection

**Why this works**
- flexible annotation
- quality control
- prediction-assisted labeling
- better dataset slicing and QA
