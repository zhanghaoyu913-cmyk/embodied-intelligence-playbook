# Visualization and Debugging

> This file covers **how to inspect what your embodied stack is doing**.

## Quick selector

| Problem | Best first choices |
|---|---|
| experiment tracking and dashboards | Weights & Biases |
| multimodal robotics visualization | Rerun |
| simple training curves | TensorBoard |
| ROS-native visual debugging | RViz / Foxglove |

---

## 1. Weights & Biases (W&B)

- **What it is**: experiment tracking and dashboard tooling.
- **Best for**: training metrics, configuration management, run comparison, artifact tracking.
- **Why embodied AI people use it**: useful when you have many policy runs, hyperparameter variants, or long training jobs.
- **Official links**
  - Docs: https://docs.wandb.ai/models/track

## 2. Rerun

- **What it is**: a data platform and visualizer for Physical AI and multimodal time-varying data.
- **Best for**: synchronized visualization of images, point clouds, poses, tracks, tensors, timelines, and robot state.
- **Why use it**: one of the best tools right now for actually understanding embodied and robotics pipelines.
- **Official links**
  - Overview: https://rerun.io/docs/overview/what-is-rerun
  - Docs: https://rerun.io/docs/overview/resources

## 3. TensorBoard

- **What it is**: a standard lightweight dashboard for ML experiments.
- **Best for**: simple curves, histograms, debugging logs.
- **Useful links**
  - Docs: https://www.tensorflow.org/tensorboard

## 4. RViz / Foxglove

### RViz
- **What it is**: the classic ROS visualization tool.
- **Best for**: frames, robot state, point clouds, markers, planned trajectories.
- **Useful links**
  - ROS docs root: https://docs.ros.org/

### Foxglove
- **What it is**: a robotics visualization and observability tool.
- **Best for**: logs, topics, timelines, debugging distributed robot systems.
- **Useful links**
  - Homepage: https://foxglove.dev/

---

## Practical guidance

### If you mainly debug training
Use:
- W&B or TensorBoard

### If you mainly debug multimodal embodied pipelines
Use:
- Rerun

### If you mainly debug ROS-integrated robot systems
Use:
- RViz and/or Foxglove

---

## Common failure modes

- only logging scalar rewards and losing the actual failure context
- not synchronizing time across modalities
- never visualizing tracks, masks, or poses together
- debugging in notebooks when the system really needs timeline-aware tools
