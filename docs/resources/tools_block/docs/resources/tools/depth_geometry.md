# Depth and Geometry

> This file covers **what to use when you need depth, metric geometry, multiview priors, or stronger scene understanding from images**.

## Quick selector

| Problem | Best first choices |
|---|---|
| fast monocular depth | Depth Anything V2 |
| monocular metric depth | UniDepth, UniDepth V2 |
| strong learned geometry from multiple views | DUSt3R, MASt3R, VGGT |
| a strong SSL visual backbone for downstream geometry | DINOv3 |
| panoramic depth | DAP (Depth Any Panoramas) |

---

## 1. Monocular depth

### Depth Anything V2
- **What it is**: a strong general-purpose monocular depth estimator.
- **Best for**: quick depth priors from RGB, scene geometry hints, robotics preprocessing, visualization.
- **Input / output**: RGB image → dense depth map.
- **Why embodied AI people use it**: it is easy to integrate and often gives useful geometric structure even when you do not have depth sensors.
- **When not to use it**: if you need calibrated metric depth as the primary objective or very strict scale consistency.

**Official links**
- Project: https://depth-anything-v2.github.io/
- Code: https://github.com/DepthAnything/Depth-Anything-V2

### UniDepth
- **What it is**: universal monocular metric depth estimation.
- **Best for**: metric depth when scale matters more than “just some depth structure”.
- **Why use it**: stronger fit when robotic geometry or downstream measurement matters.
- **Official links**
  - Code: https://github.com/lpiccinelli-eth/UniDepth

### UniDepth V2
- **What it is**: the newer line of UniDepth.
- **Best for**: updated metric depth with a simpler and stronger current setup.
- **Why use it**: if you specifically care about metric depth, this is more current than stopping at the original release.

**Official links**
- Repo / V2 notes: https://github.com/lpiccinelli-eth/UniDepth

### DAP (Depth Any Panoramas)
- **What it is**: panoramic depth estimation.
- **Best for**: 360° scenes, wide-FOV embodied logging, panoramic robotics capture.
- **Official links**
  - Code: https://github.com/Insta360-Research-Team/DAP

---

## 2. Learned multiview geometry

### DUSt3R
- **What it is**: learned geometric 3D vision with pointmaps and multiview alignment.
- **Best for**: reconstructing scenes from a few unposed views, quick geometry from image collections.
- **Why embodied AI people use it**: it is a very practical bridge from raw images to 3D structure when classical calibration pipelines are too heavy.
- **When not to use it**: when you need a battle-tested classical SfM pipeline for production-style reconstruction.

**Official links**
- Code: https://github.com/naver/dust3r

### MASt3R
- **What it is**: a related learned matching / geometry line built on top of the DUSt3R family.
- **Best for**: stronger matching and geometric grounding across views.
- **Why use it**: useful if DUSt3R-style geometry is already in your stack and you want a more matching-oriented variant.

**Official links**
- Code: https://github.com/naver/mast3r

### MUSt3R
- **What it is**: an extension of the DUSt3R family for online multiview prediction with memory.
- **Best for**: larger view collections, online multiview geometry.
- **Official links**
  - Code: https://github.com/naver/must3r

### VGGT
- **What it is**: Visual Geometry Grounded Transformer.
- **Best for**: direct inference of camera parameters, point maps, depth maps, and point tracks from one or many views.
- **Why use it**: very strong if you want a more integrated learned geometry system rather than manually chaining separate estimators.

**Official links**
- Code: https://github.com/facebookresearch/vggt

---

## 3. Backbones that matter for geometry

### DINOv3
- **What it is**: a strong self-supervised visual backbone.
- **Best for**: feature extraction for geometry, perception, matching, and downstream heads.
- **Why include it here**: even when it is not a geometry model by itself, it is exactly the kind of backbone many embodied stacks use before depth, pose, or reconstruction heads.

**Official links**
- Research page: https://ai.meta.com/research/dinov3/
- Code: https://github.com/facebookresearch/dinov3

---

## Practical guidance

### If you want “good enough depth quickly”
Use:
- Depth Anything V2

### If metric scale matters
Use:
- UniDepth / UniDepth V2

### If you want to recover geometry from sparse unposed images
Use:
- DUSt3R or MASt3R

### If you want a more integrated learned geometry model
Use:
- VGGT

### If you want a strong backbone to build on
Use:
- DINOv3

---

## Common failure modes

- treating monocular depth as perfectly metric
- assuming learned geometry is always more stable than classical SfM
- using depth maps directly as world state without checking calibration quality
- forgetting that good geometry still does not solve action representation or control

---

## Good combinations

### Fast perception prior
DINOv3 + Depth Anything V2

### Metric depth path
DINOv3 + UniDepth V2

### Learned reconstruction path
VGGT or DUSt3R / MASt3R + Rerun

### World-model preprocessing path
CoTracker3 + VGGT / DUSt3R + Rerun
