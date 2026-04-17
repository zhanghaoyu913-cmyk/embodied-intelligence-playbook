# Simulators

Simulation is not only a convenience layer. In embodied AI, the simulator often determines what can be learned, measured, debugged, and transferred.

## Common simulator roles

- collecting interaction data
- training control or policy models
- testing long-horizon task execution
- validating physical intuition
- stress-testing failure cases before real-world deployment

## Major evaluation dimensions

When comparing simulators, the important questions are usually:

- How good is the physical fidelity?
- How convenient is scene and asset creation?
- How fast is large-scale rollout?
- How easy is visual rendering and camera control?
- How painful is integration with robot learning code?

## Planned coverage

This page will later compare options such as:

- MuJoCo
- Isaac Sim
- Habitat
- ManiSkill
- PyBullet
- Gazebo

with emphasis on **use case fit**, not only feature lists.
