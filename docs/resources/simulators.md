# Simulators

Simulation is not a branding choice. It is a choice about throughput, task shape, and how much transfer pain you are willing to absorb later.

## Simulator matrix

| Simulator / stack | Strongest use case | Throughput | Physics / scene realism | Best for | Links |
|---|---|---|---|---|---|
| MuJoCo | clean continuous control | high | medium | RL baselines, control, model-based RL | [official](https://mujoco.org/) |
| MuJoCo Playground | modern MJX robot learning | high | medium | RL stacks with fast iteration and robot task focus | [project](https://playground.mujoco.org/), [code](https://github.com/google-deepmind/mujoco_playground) |
| Isaac Lab | large-scale robot learning on Isaac Sim | medium-high | high | locomotion, humanoids, sim-to-real, robot training | [docs](https://isaac-sim.github.io/IsaacLab/), [code](https://github.com/isaac-sim/IsaacLab) |
| ManiSkill | manipulation-focused GPU simulation | high | medium-high | manipulation benchmarks and reproducible training | [project](https://maniskill.ai/) |
| SAPIEN | articulated objects and interaction geometry | medium | high for object interaction | affordance, articulation, part-aware manipulation | [project](https://sapien.ucsd.edu/) |
| Habitat | navigation and embodied perception | high | medium-high for scene reasoning | embodied navigation and scene understanding | [project](https://aihabitat.org/) |
| OmniGibson / BEHAVIOR stack | household environments and human-centered activity | low-medium | high | household embodied tasks and BEHAVIOR-aligned work | [project](https://behavior.stanford.edu/index.html) |
| Meta-World | controlled multi-task manipulation suite | high | low-medium | RL and imitation baselines | [project](https://meta-world.github.io/) |
| Gazebo | ROS-centric integration | medium | medium | system integration and deployment workflows | [official](https://gazebosim.org/) |

## Task-level routing

| If you want to study... | Start here |
|---|---|
| locomotion or humanoid RL | Isaac Lab, MuJoCo Playground |
| tabletop manipulation | ManiSkill, Meta-World |
| articulated-object interaction | SAPIEN |
| navigation | Habitat |
| household embodied activity | OmniGibson / BEHAVIOR |
| ROS-centric deployment rehearsal | Gazebo |

## Practical rules

- Pick the simulator based on the training loop, not the name.
- If you want fast ablations, prefer `MuJoCo`, `Meta-World`, or `ManiSkill`.
- If you want whole-body or hardware-adjacent scaling, prefer `Isaac Lab`.
- If you care about parts, handles, and articulated geometry, prefer `SAPIEN`.
- Cross-reference this page with [Benchmarks](benchmarks.md), [Frameworks](frameworks.md), and [Sim-to-Real build path](../build_paths/sim2real.md).
