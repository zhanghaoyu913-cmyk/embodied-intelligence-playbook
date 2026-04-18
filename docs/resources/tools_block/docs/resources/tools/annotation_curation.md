# Annotation and Curation

> This file covers **how to label, inspect, clean, and manage data for embodied AI**.

## Quick selector

| Problem | Best first choices |
|---|---|
| image and video annotation | CVAT |
| flexible multi-modal labeling | Label Studio |
| dataset inspection, slicing, and QA | FiftyOne |

---

## 1. CVAT

- **What it is**: a strong annotation platform for image, video, and 3D annotation.
- **Best for**: vision-heavy dataset production, team labeling, quality control, long video annotation workflows.
- **Why embodied AI people use it**: useful for masks, boxes, object trajectories, frame-by-frame correction, and team-managed labeling.
- **Official links**
  - Docs: https://docs.cvat.ai/
  - Homepage: https://www.cvat.ai/

## 2. Label Studio

- **What it is**: an open-source data labeling tool with flexible project configuration.
- **Best for**: custom annotation workflows, multimodal tasks, API-driven labeling loops, model-assisted pre-labeling.
- **Why use it**: useful when your labeling task is not just “draw boxes” but something more custom.
- **Official links**
  - Docs: https://labelstud.io/guide/

## 3. FiftyOne

- **What it is**: a visual dataset curation, exploration, and evaluation platform.
- **Best for**: dataset QA, embedding-based inspection, prediction comparison, video exploration, slice analysis.
- **Why embodied AI people use it**: useful when you already have data and predictions and want to inspect failure cases, compare labels, or curate subsets.
- **Official links**
  - Docs: https://docs.voxel51.com/

---

## Practical guidance

### If you are collecting a new robot dataset
Use:
- CVAT or Label Studio for annotation
- FiftyOne for QA and slicing

### If your project has custom task schemas
Use:
- Label Studio

### If your bottleneck is data inspection rather than labeling
Use:
- FiftyOne

---

## Common failure modes

- spending too long hand-labeling when model-assisted pre-labeling is possible
- using a flexible labeling tool but no quality-control process
- failing to inspect class imbalance and bad slices before training
- not preserving coordinate or timestamp metadata for robot data
