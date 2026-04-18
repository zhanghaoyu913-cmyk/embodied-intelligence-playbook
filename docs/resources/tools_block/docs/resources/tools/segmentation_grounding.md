# Segmentation and Grounding

> This file covers **what to use when you need masks, text grounding, or strong visual backbones**.

## Problem map

| Problem | Best first choices |
|---|---|
| promptable masks on images | SAM, SAM 2.1, SAM 3 |
| promptable masks on videos | SAM 2.1, SAM 3 / SAM 3.1 |
| text-conditioned detection | Grounding DINO, Grounding DINO 1.5, OWLv2 |
| text-conditioned detection + masks | Grounded SAM, Grounded SAM 2 |
| unified prompt-based vision tasks | Florence-2 |
| universal visual backbone features | DINOv3 |

---

## 1. Promptable segmentation

### SAM
- **What it is**: the original Segment Anything Model.
- **Best for**: point/box-prompted image masks, classical mask generation, broad zero-shot segmentation.
- **Input / output**: RGB image + points/boxes → masks.
- **Why use it**: still the cleanest baseline when you only need image masks.
- **When not to use it**: long videos, text-conditioned concepts, or heavy open-vocabulary tracking.

**Official links**
- Project: https://segment-anything.com/
- Code: https://github.com/facebookresearch/segment-anything

### SAM 2 / SAM 2.1
- **What it is**: unified promptable segmentation for images and videos.
- **Best for**: video object segmentation, interactive refinement, image/video unification.
- **Input / output**: image or video + points/boxes/masks → masks / tracked masks.
- **Why embodied AI people use it**: it is a very practical bridge between static masks and temporal mask propagation.
- **When not to use it**: if you need explicit open-vocabulary concept segmentation from text as the primary interface.

**Official links**
- Research/blog: https://ai.meta.com/research/sam2/
- Code: https://github.com/facebookresearch/sam2

### SAM 3 / SAM 3.1
- **What it is**: concept-aware promptable segmentation for images and videos with text and exemplar prompting.
- **Best for**: open-vocabulary concept segmentation, image/video segmentation with text prompts, multi-object tracking with newer checkpoints.
- **Input / output**: image or video + text / points / boxes / masks / exemplars → masks, boxes, scores, tracked outputs.
- **Why use it**: this is the current strongest official Meta line when you want “segment this concept” rather than only “segment this clicked region”.
- **When not to use it**: if you want the lightest setup or the most mature deployment ecosystem; SAM 2.1 can still be simpler.

**Official links**
- Research page: https://ai.meta.com/research/sam3/
- Blog: https://ai.meta.com/blog/segment-anything-model-3/
- Code: https://github.com/facebookresearch/sam3

### HQ-SAM
- **What it is**: a high-quality refinement variant for better mask boundaries.
- **Best for**: fine boundaries, cleaner object edges.
- **Why use it**: useful when original SAM masks are slightly too coarse.
- **Official links**
  - Code: https://github.com/SysCV/sam-hq

---

## 2. Open-vocabulary detection and grounding

### Grounding DINO
- **What it is**: open-world / text-conditioned object detection.
- **Best for**: “find the drawer handle”, “find the mug”, “find the red cup”.
- **Input / output**: image + text query → boxes, labels, confidence.
- **Why embodied AI people use it**: it is one of the most direct ways to turn language into object proposals before segmentation, pose estimation, or planning.
- **When not to use it**: if you already have a closed label set and a stable detector.

**Official links**
- Code: https://github.com/IDEA-Research/GroundingDINO

### Grounding DINO 1.5
- **What it is**: the stronger newer line from IDEA Research.
- **Best for**: improved open-vocabulary detection compared with older Grounding DINO usage patterns.
- **When to prefer it**: when you want a more up-to-date text-grounded detector without changing your pipeline logic.

**Official links**
- API/examples: https://github.com/IDEA-Research/Grounding-DINO-1.5-API
- Main repo notes: https://github.com/IDEA-Research/GroundingDINO

### OWLv2
- **What it is**: zero-shot / open-vocabulary object detection from Google’s OWL-ViT line.
- **Best for**: fast text-conditioned detection baselines, image-guided detection, open-vocabulary experiments.
- **Why use it**: a strong alternative when you want a detector-first workflow.
- **When not to use it**: when your main workflow depends on the Grounding DINO + SAM family integration.

**Useful links**
- Scenic OWL-ViT / OWLv2 code path: https://github.com/google-research/scenic/tree/main/scenic/projects/owl_vit
- HF model support: https://huggingface.co/docs/transformers/model_doc/owlv2

---

## 3. Detection + segmentation pipelines

### Grounded SAM
- **What it is**: Grounding DINO + SAM.
- **Best for**: text → box → mask workflows.
- **Why it matters**: one of the most common “open-vocabulary segmentation” recipes in practice.
- **Official links**
  - Repo: https://github.com/IDEA-Research/grounded-segment-anything

### Grounded SAM 2
- **What it is**: Grounding DINO combined with SAM 2 for open-world tracking and segmentation.
- **Best for**: text-conditioned video object tracking / segmentation.
- **Why it matters**: practical if your pipeline starts from language and needs temporal propagation.

**Useful links**
- Grounding DINO repo notes: https://github.com/IDEA-Research/GroundingDINO

---

## 4. Unified visual prompting models

### Florence-2
- **What it is**: a prompt-based vision foundation model from Microsoft.
- **Best for**: captioning, detection, segmentation, OCR-like prompting, region understanding, “one model for many visual prompts”.
- **Input / output**: image + task prompt → structured visual outputs.
- **Why use it**: very useful as a compact “general visual interface” when you do not want many separate perception models.
- **When not to use it**: if you need the strongest specialized detector or the strongest specialized segmenter.

**Official links**
- HF model page: https://huggingface.co/microsoft/Florence-2-large

---

## 5. Strong visual backbones

### DINO / DINOv2 / DINOv3
- **What they are**: self-supervised visual backbones from Meta’s DINO line.
- **Best for**: feature extraction, retrieval, perception backbones, dense features, representation learning.
- **Why DINOv3 matters**: if your embodied stack needs stronger general-purpose features, DINOv3 is a more current backbone than earlier DINO generations.
- **How to use it in embodied AI**:
  - as a frozen image encoder
  - as a feature source for segmentation / detection heads
  - as a perception backbone for geometry, retrieval, or state estimation

**Official links**
- DINOv3 research page: https://ai.meta.com/research/dinov3/
- DINOv3 code: https://github.com/facebookresearch/dinov3
- DINO (original): https://github.com/facebookresearch/dino

---

## Practical decision guide

### If you need the simplest good image-mask baseline
Use:
- SAM

### If you need video masks and interactive propagation
Use:
- SAM 2.1 or SAM 3

### If you need text-conditioned localization
Use:
- Grounding DINO 1.5 or OWLv2

### If you need text-conditioned masks
Use:
- Grounding DINO 1.5 + SAM 2.1 / SAM 3

### If you need one prompt-based visual interface for many tasks
Use:
- Florence-2

### If you need a strong universal visual backbone
Use:
- DINOv3

---

## Common failure modes

- using a segmentation tool when the real bottleneck is detection
- using a detector when the real bottleneck is mask quality
- forgetting temporal consistency in videos
- assuming text grounding is equivalent to executable robot grounding
- treating backbone features as directly actionable without geometry or control logic

---

## Recommended embodied-AI mini stacks

### Open-vocabulary perception stack
Grounding DINO 1.5 + SAM 3 + DINOv3

### Video interaction stack
SAM 2.1 / SAM 3 + CoTracker3 + FoundationPose

### Compact general-purpose perception stack
Florence-2 + Depth Anything V2 + DINOv3
