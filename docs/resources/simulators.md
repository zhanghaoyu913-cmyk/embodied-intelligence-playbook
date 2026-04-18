# Simulators

Simulation is not a single choice. It is a decision about physics fidelity, throughput, tooling, and how much sim-to-real glue you are willing to write.

## Core simulators and training stacks

| Simulator / stack | Strength | Links |
|---|---|---|
| MuJoCo | fast and widely used continuous-control physics | [official](https://mujoco.org/) |
| MuJoCo Playground | modern GPU-accelerated robot learning with MJX | [project](https://playground.mujoco.org/) · [code](https://github.com/google-deepmind/mujoco_playground) |
| Isaac Lab | large-scale robot learning on top of Isaac Sim | [docs](https://isaac-sim.github.io/IsaacLab/) · [code](https://github.com/isaac-sim/IsaacLab) |
| ManiSkill | manipulation-focused benchmarks and GPU simulation | [project](https://maniskill.ai/) |
| Habitat | embodied navigation and scene understanding | [project](https://aihabitat.org/) |
| OmniGibson | realistic household and human-centered embodied simulation | [project](https://behavior.stanford.edu/index.html) |
| PyBullet | lightweight and accessible starting point | [official](https://pybullet.org/wordpress/) |
| Gazebo | ROS-centric systems integration and deployment workflows | [official](https://gazebosim.org/) |

## Quick pairing guide

- **Locomotion / humanoids / RL at scale** → Isaac Lab, MuJoCo Playground
- **Mobile manipulation / household tasks** → BEHAVIOR-1K / OmniGibson, ManiSkill
- **Navigation and embodied perception** → Habitat
- **ROS-heavy integration** → Gazebo

## Practical rule

Pick the simulator based on the *training loop* you need, not the simulator brand alone.
