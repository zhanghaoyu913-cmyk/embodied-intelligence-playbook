# Reconstruction and Scene Building

> This file covers **how to turn images into scene structure, camera poses, pointmaps, and viewable 3D assets**.

## Quick selector

| Problem | Best first choices |
|---|---|
| classical image-based reconstruction | COLMAP |
| learned reconstruction from sparse views | DUSt3R, MASt3R |
| more integrated geometry inference | VGGT |
| quick radiance-field-like visual scene representation | 3D Gaussian Splatting |

---

## 1. Classical reconstruction

### COLMAP
- **What it is**: a general-purpose structure-from-motion and multi-view stereo pipeline.
- **Best for**: classical reconstruction, camera pose estimation, reproducible image-based geometry pipelines.
- **Why use it**: still one of the most important reconstruction baselines and often the cleanest way to establish a reliable reference pipeline.
- **When not to use it**: when you want fast learned geometry from a handful of unposed views without much tuning.

**Official links**
- Project / docs: https://colmap.github.io/

---

## 2. Learned reconstruction lines

### DUSt3R
- **What it is**: learned 3D reconstruction using pointmaps.
- **Best for**: sparse unposed views, fast scene understanding, easy geometry extraction.
- **Official links**
  - Code: https://github.com/naver/dust3r

### MASt3R
- **What it is**: matching in 3D built on the DUSt3R family.
- **Best for**: stronger matching and geometric consistency.
- **Official links**
  - Code: https://github.com/naver/mast3r

### MUSt3R
- **What it is**: multiview memory-based extension of the DUSt3R family.
- **Best for**: online or longer multiview geometry settings.
- **Official links**
  - Code: https://github.com/naver/must3r

### VGGT
- **What it is**: a feed-forward geometry transformer that infers multiple 3D attributes of a scene.
- **Best for**: direct camera/geometry/track estimation from one or many views.
- **Official links**
  - Code: https://github.com/facebookresearch/vggt

---

## 3. Scene representations

### 3D Gaussian Splatting
- **What it is**: a fast scene representation and rendering method for radiance-field-style reconstruction.
- **Best for**: visualization, scene capture, rapid rendering, digital-twin-style demos.
- **Why embodied AI people use it**: useful when you want a scene representation that is easier to render and inspect than heavier NeRF pipelines.
- **When not to use it**: if your primary need is stable metric reconstruction or control-ready geometry.

**Official links**
- Project: https://repo-sam.inria.fr/fungraph/3d-gaussian-splatting/

---

## Practical guidance

### If you need a trusted baseline
Use:
- COLMAP

### If you want the easiest learned 3D route
Use:
- DUSt3R

### If matching quality matters a lot
Use:
- MASt3R

### If you want a more integrated geometry transformer
Use:
- VGGT

### If you mainly need a visual 3D asset
Use:
- 3D Gaussian Splatting

---

## Common failure modes

- using a rendering-oriented scene representation as if it were directly control-ready geometry
- assuming sparse-view learned reconstruction gives metric-consistent scenes automatically
- ignoring global alignment and coordinate conventions
- forgetting that scene reconstruction quality depends heavily on viewpoint coverage

---

## Good combinations

### Classical geometry stack
COLMAP + Rerun

### Learned geometry stack
DUSt3R / MASt3R + VGGT + Rerun

### Digital twin / visual demo stack
COLMAP or DUSt3R + 3D Gaussian Splatting
