# Frameworks

This page is organized by execution role: what codebase helps you build which layer of the embodied stack.

## Policy learning and robot learning

| Framework | Best for | Ecosystem maturity | Real-world friendliness | Links |
|---|---|---|---|---|
| OpenVLA | open VLA fine-tuning and evaluation | medium-high | medium | [project](https://openvla.github.io/), [code](https://github.com/openvla/openvla) |
| Octo | generalist policy experimentation | high | medium | [project](https://octo-models.github.io/), [code](https://github.com/octo-models/octo) |
| robomimic | imitation learning and offline robot learning | high | high | [project](https://robomimic.github.io/), [code](https://github.com/ARISE-Initiative/robomimic) |
| LeRobot | practical end-to-end robotics toolkit | high | high | [docs](https://huggingface.co/docs/lerobot/index), [code](https://github.com/huggingface/lerobot) |
| ACT | action-chunking baselines for real manipulation | medium | high | [code](https://github.com/tonyzhaozh/act) |
| Diffusion Policy | strong visuomotor manipulation baseline family | medium | medium | [project](https://diffusion-policy.cs.columbia.edu/) |

## RL and control

| Framework | Best for | Ecosystem maturity | Real-world friendliness | Links |
|---|---|---|---|---|
| DreamerV3 | world-model RL experiments | high | low-medium | [code](https://github.com/danijar/dreamerv3) |
| TD-MPC2 | latent-planning model-based RL | medium-high | medium | [project](https://www.tdmpc2.com/), [code](https://github.com/nicklashansen/tdmpc2) |
| RSL-RL | legged and robot RL training loops | high | medium-high | [repo](https://github.com/leggedrobotics/rsl_rl) |
| legged_gym | locomotion and rough-terrain training | high | medium-high | [code](https://github.com/leggedrobotics/legged_gym) |
| Isaac Lab RL stack | simulator-scale robot RL | high | medium-high | [docs](https://isaac-sim.github.io/IsaacLab/main/source/overview/reinforcement-learning/index.html) |
| MuJoCo Playground | modern MJX-based robot RL | medium-high | medium | [project](https://playground.mujoco.org/), [code](https://github.com/google-deepmind/mujoco_playground) |

## Sim-to-real and deployment glue

| Framework / stack | Best for | Ecosystem maturity | Real-world friendliness | Links |
|---|---|---|---|---|
| ROS2 | robot middleware and deployment integration | high | high | [official](https://docs.ros.org/en/rolling/index.html) |
| Isaac Lab | simulation-to-training bridge | high | medium-high | [docs](https://isaac-sim.github.io/IsaacLab/) |
| LeRobot | low-cost hardware and data loop | high | high | [docs](https://huggingface.co/docs/lerobot/index) |
| MuJoCo Playground | clean RL-to-transfer loop for certain robots | medium-high | medium | [project](https://playground.mujoco.org/) |

## Grasping, affordance, and object interaction

| Framework | Best for | Ecosystem maturity | Real-world friendliness | Links |
|---|---|---|---|---|
| GraspNet baseline ecosystem | grasp detection and evaluation | high | medium | [project](https://graspnet.net/) |
| Contact-GraspNet | point-cloud grasp estimation | high | medium-high | [project](https://contact-graspnet.github.io/), [code](https://github.com/NVlabs/contact_graspnet) |
| GPD | proposal-and-ranking grasping stacks | high | high | [code](https://github.com/atenpas/gpd) |
| VGN | volumetric grasping | medium | medium | [code](https://github.com/ethz-asl/vgn) |
| SAPIEN | articulated interaction and part-aware simulation | high | medium | [project](https://sapien.ucsd.edu/) |

## Whole-body and humanoid signal

| Stack | Best for | Ecosystem maturity | Real-world friendliness | Links |
|---|---|---|---|---|
| Isaac Lab + GR00T ecosystem | humanoid policy and simulation stack watching | medium-high | medium | [Isaac Lab](https://isaac-sim.github.io/IsaacLab/), [Isaac GR00T](https://developer.nvidia.com/isaac/gr00t) |
| MuJoCo Playground | robot RL including humanoid-oriented tasks | medium-high | medium | [project](https://playground.mujoco.org/) |
| LeRobot hardware docs | low-cost embodied hardware entry | high | high | [docs](https://huggingface.co/docs/lerobot/index) |

## Practical pick rules

- If you need a first real build, start with `LeRobot`, `robomimic`, or `ACT`.
- If you need an open VLA comparison, use `OpenVLA` and `Octo`.
- If you need RL scale, use `Isaac Lab`, `MuJoCo Playground`, or `RSL-RL`.
- If you need grasping or articulation, start with `GraspNet`, `Contact-GraspNet`, and `SAPIEN`.
