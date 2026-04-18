# Frameworks

This page collects codebases that repeatedly show up in practical embodied-AI work.

## Policy learning and robot learning

| Framework | Use case | Links |
|---|---|---|
| OpenVLA | open-source VLA training and fine-tuning | [project](https://openvla.github.io/) · [code](https://github.com/openvla/openvla) |
| Octo | open-source generalist robot policy | [project](https://octo-models.github.io/) · [code](https://github.com/octo-models/octo) |
| robomimic | imitation learning and offline robot learning | [project](https://robomimic.github.io/) · [code](https://github.com/ARISE-Initiative/robomimic) |
| LeRobot | end-to-end open robotics toolkit in PyTorch | [docs](https://huggingface.co/docs/lerobot/index) · [code](https://github.com/huggingface/lerobot) |
| ACT | action-chunking implementation for real manipulation | [code](https://github.com/tonyzhaozh/act) |
| Diffusion Policy | diffusion-based manipulation policy baseline | [project](https://diffusion-policy.cs.columbia.edu/) |

## RL and control

| Framework | Use case | Links |
|---|---|---|
| DreamerV3 | world-model RL baseline | [code](https://github.com/danijar/dreamerv3) |
| TD-MPC2 | latent-planning model-based RL | [project](https://www.tdmpc2.com/) · [code](https://github.com/nicklashansen/tdmpc2) |
| legged_gym | rough-terrain locomotion and sim-to-real | [code](https://github.com/leggedrobotics/legged_gym) |
| Isaac Lab RL docs | RL workflows on Isaac Lab | [docs](https://isaac-sim.github.io/IsaacLab/main/source/overview/reinforcement-learning/index.html) |

## Grasping / affordance / object interaction

| Framework | Use case | Links |
|---|---|---|
| GraspNet baseline | 6-DoF grasp detection | [project](https://graspnet.net/) |
| Contact-GraspNet | point-cloud grasp estimation | [project](https://contact-graspnet.github.io/) · [code](https://github.com/NVlabs/contact_graspnet) |
| GPD | classic grasp proposal and scoring | [code](https://github.com/atenpas/gpd) |
| SAPIEN | articulated-object simulation and affordance-heavy manipulation | [project](https://sapien.ucsd.edu/) |

## How to pick

- **Want an open VLA baseline?** Use OpenVLA or Octo.
- **Want imitation / offline manipulation?** Use robomimic or LeRobot.
- **Want RL / model-based control?** Use DreamerV3, TD-MPC2, Isaac Lab, or MuJoCo Playground.
- **Want grasping?** Start with GraspNet or Contact-GraspNet.
