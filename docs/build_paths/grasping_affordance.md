# Build Path: Grasping + Affordance

## Summary

- Audience: readers who want to connect perception with executable interaction.
- Outcome: a pipeline that predicts useful contacts or actionable regions and tests them in downstream tasks.
- Prerequisites: RGB-D or point-cloud basics, coordinate frames, simple robot execution loop.

## Minimum stack

| Layer | Recommended choice |
|---|---|
| Benchmark | GraspNet or PartNet-Mobility depending on task |
| Simulator | SAPIEN or ManiSkill |
| Framework | Contact-GraspNet, VGN, or an affordance-point predictor |
| Hardware | RGB-D camera plus simple arm if doing real-world validation |

## Reading core

1. [GraspNet](https://graspnet.net/)
2. [Contact-GraspNet](https://contact-graspnet.github.io/)
3. [Where2Act](https://cs.stanford.edu/~kaichun/where2act/)
4. [AdaAfford](https://hyperplane-lab.github.io/AdaAfford/)

## Execution plan

### Week 1-2

- Reproduce one grasping baseline or one actionable-region baseline.
- Visualize predicted contacts or regions.

### Week 3-4

- Convert predictions into robot commands.
- Measure the gap between prediction quality and execution success.

### Week 5-8

- Add task conditioning: downstream place, open, pour, or articulated interaction.
- Compare geometry-only, affordance-only, and joint approaches.

## Failure modes

- using benchmark scores that do not reflect downstream task success
- skipping controller and perception calibration issues
- claiming affordance quality without execution evidence

## Success check

A convincing result shows that the chosen contact or region improves downstream action, not only offline heatmap quality.

## Next step

Read [Grasping roadmap](../roadmap/grasping.md), [Affordance roadmap](../roadmap/affordance.md), and [Benchmarks](../resources/benchmarks.md).
