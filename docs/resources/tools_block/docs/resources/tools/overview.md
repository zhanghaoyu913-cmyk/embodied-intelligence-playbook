# Tools for Embodied AI

> This toolbox is organized by **what you are trying to build**, not only by tool names.

## How to use this section

Use this directory in two passes:

1. **Start from the problem**  
   “I need masks”, “I need metric depth”, “I need 6D pose”, “I need to reconstruct a scene”, “I need a simulator”, “I need to connect to ROS 2”.
2. **Then choose a stack**  
   After you know the task, jump to [recommended_stacks.md](recommended_stacks.md) for a practical combination of tools.

---

## File map

| File | Focus |
|---|---|
| [segmentation_grounding.md](segmentation_grounding.md) | segmentation, grounding, open-vocabulary perception |
| [depth_geometry.md](depth_geometry.md) | depth estimation, geometry priors, multiview geometry |
| [tracking_pose.md](tracking_pose.md) | point tracking, temporal correspondence, 6D object pose |
| [reconstruction_scene.md](reconstruction_scene.md) | scene reconstruction, pointmaps, splatting, assets |
| [annotation_curation.md](annotation_curation.md) | labeling, curation, dataset inspection |
| [simulation_learning.md](simulation_learning.md) | simulators, robot-learning stacks, imitation/RL frameworks |
| [planning_deployment.md](planning_deployment.md) | ROS 2, motion planning, deployment glue |
| [visualization_debugging.md](visualization_debugging.md) | experiment tracking, multimodal debugging, logging |
| [recommended_stacks.md](recommended_stacks.md) | suggested end-to-end tool combinations |

---

## Quick selector by problem

| If you need... | Start here | Typical tools |
|---|---|---|
| object masks from points / boxes / text | [segmentation_grounding.md](segmentation_grounding.md) | SAM 2.1, SAM 3, Grounding DINO 1.5, Grounded SAM 2 |
| text-conditioned object detection | [segmentation_grounding.md](segmentation_grounding.md) | Grounding DINO 1.5, OWLv2, Florence-2 |
| strong general-purpose visual features | [segmentation_grounding.md](segmentation_grounding.md) | DINOv3, Florence-2 |
| monocular depth or metric depth | [depth_geometry.md](depth_geometry.md) | Depth Anything V2, UniDepth, UniDepth V2 |
| point tracks across video | [tracking_pose.md](tracking_pose.md) | CoTracker3, TAPIR |
| object pose and 6D tracking | [tracking_pose.md](tracking_pose.md) | FoundationPose, MegaPose |
| multiview reconstruction or pointmaps | [reconstruction_scene.md](reconstruction_scene.md) | COLMAP, DUSt3R, MASt3R, VGGT |
| a fast scene representation for visualization | [reconstruction_scene.md](reconstruction_scene.md) | 3D Gaussian Splatting |
| labeling and data QA | [annotation_curation.md](annotation_curation.md) | CVAT, Label Studio, FiftyOne |
| simulation and robot learning | [simulation_learning.md](simulation_learning.md) | Isaac Lab, ManiSkill 3, Habitat 3.0, robomimic, LeRobot |
| motion planning and robot middleware | [planning_deployment.md](planning_deployment.md) | ROS 2, MoveIt 2 |
| multimodal visualization and experiment tracking | [visualization_debugging.md](visualization_debugging.md) | Rerun, W&B |

---

## Suggested reading order

### If you mainly care about VLA or perception-heavy manipulation
1. [segmentation_grounding.md](segmentation_grounding.md)
2. [depth_geometry.md](depth_geometry.md)
3. [tracking_pose.md](tracking_pose.md)
4. [recommended_stacks.md](recommended_stacks.md)

### If you mainly care about world models / trace learning / spatial understanding
1. [tracking_pose.md](tracking_pose.md)
2. [depth_geometry.md](depth_geometry.md)
3. [reconstruction_scene.md](reconstruction_scene.md)
4. [visualization_debugging.md](visualization_debugging.md)

### If you mainly care about training and deployment
1. [simulation_learning.md](simulation_learning.md)
2. [planning_deployment.md](planning_deployment.md)
3. [visualization_debugging.md](visualization_debugging.md)
4. [recommended_stacks.md](recommended_stacks.md)

---

## One practical rule

Do not choose tools by leaderboard alone.

Choose them by:
- what they take as input
- what they output
- whether they can fit your data format
- whether they can be integrated into your existing stack
- whether they are stable enough for repeated use
