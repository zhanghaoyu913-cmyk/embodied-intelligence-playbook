# Tracking and Pose

> This file covers **what to use when you need temporal correspondence, point trajectories, or 6D object pose**.

## Quick selector

| Problem | Best first choices |
|---|---|
| point tracking across video | CoTracker3, TAPIR |
| sparse-to-dense temporal correspondence | CoTracker3 |
| object 6D pose estimation for novel objects | FoundationPose, MegaPose |
| object pose tracking over time | FoundationPose |
| pose from rendered comparison pipelines | MegaPose |

---

## 1. Point tracking and temporal correspondence

### CoTracker3
- **What it is**: a current strong point-tracking model for videos.
- **Best for**: dense / sparse point trajectories, temporal correspondence, motion cues, interaction traces.
- **Why embodied AI people use it**: point tracks are extremely useful for world-model supervision, trace learning, video-to-action hints, and interaction localization.
- **When not to use it**: if your real target is object-level pose rather than point trajectories.

**Official links**
- Repo: https://github.com/facebookresearch/co-tracker
- Project: https://cotracker3.github.io/

### TAPIR
- **What it is**: a strong point-tracking line from Google DeepMind’s TAP family.
- **Best for**: accurate point tracking and refinement over time.
- **Why use it**: a very solid alternative to CoTracker when you want strong point-level temporal modeling.

**Official links**
- Code: https://github.com/google-deepmind/tapnet

---

## 2. Object pose and 6D tracking

### FoundationPose
- **What it is**: unified 6D object pose estimation and tracking for model-based and model-free settings.
- **Best for**: robotic manipulation, pick-and-place, object alignment, instance-level object tracking.
- **Input / output**: image stream + CAD model or reference images → 6D pose and tracking.
- **Why embodied AI people use it**: it directly turns object perception into a signal usable by grasping and manipulation stacks.
- **When not to use it**: if you only need masks or category-level localization.

**Official links**
- Project: https://nvlabs.github.io/FoundationPose/
- Code: https://github.com/NVlabs/FoundationPose

### MegaPose
- **What it is**: pose estimation of novel objects via render-and-compare style methods.
- **Best for**: object-level pose with known geometry and synthetic-data-heavy pipelines.
- **Why use it**: still a very useful 6D pose reference line, especially for instance-level novel object pose.

**Official links**
- Project: https://megapose6d.github.io/
- Code: https://github.com/megapose6d/megapose6d

---

## Practical guidance

### If your goal is trace supervision or world-model training
Use:
- CoTracker3 or TAPIR

### If your goal is grasping or pose-conditioned manipulation
Use:
- FoundationPose or MegaPose

### If your goal is robust tracked masks + object pose
Use:
- SAM 3 / SAM 2.1 + FoundationPose

### If your goal is temporal video understanding rather than action
Use:
- CoTracker3 / TAPIR + Rerun

---

## Common failure modes

- using point tracking when object identity is what matters
- using 6D pose estimation when rough mask tracking would already solve the problem
- forgetting frame conventions and camera extrinsics
- using unstable object crops before pose estimation
- failing to visualize tracks and poses in the same coordinate frame

---

## Good combinations

### Video interaction analysis
SAM 3 + CoTracker3 + Rerun

### Object-centric manipulation
Grounding DINO 1.5 + SAM 3 + FoundationPose + MoveIt 2

### Trace-learning / cross-embodiment stack
CoTracker3 + TAPIR + DUSt3R / VGGT + Rerun
