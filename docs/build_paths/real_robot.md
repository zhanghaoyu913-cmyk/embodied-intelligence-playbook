# Build Path: Real Robot

## Summary

- Audience: readers who want the most practical low-cost path into embodied AI.
- Outcome: a small real robot pipeline with honest constraints and repeatable evaluation.
- Prerequisites: basic Linux or robotics tooling, camera calibration, patience with hardware failure.

## Minimum stack

| Layer | Recommended choice |
|---|---|
| Hardware | SO-101 / LeRobot-style arm, ALOHA-style setup, or equivalent low-cost tabletop system |
| Data | teleoperation demonstrations |
| Software | LeRobot, ACT, robomimic, ROS2 where needed |
| Benchmark | a narrow in-house task family plus one public benchmark mindset |

## Reading core

1. [Mobile ALOHA](https://src.stanford.edu/demo/moble-aloha)
2. [ACT](https://github.com/tonyzhaozh/act)
3. [LeRobot](https://huggingface.co/docs/lerobot/index)
4. [robomimic](https://robomimic.github.io/)

## Execution plan

### Week 1-2

- Calibrate cameras and action scaling.
- Collect a tiny demonstration set.
- Reproduce a behavior-cloning baseline.

### Week 3-4

- Harden the data loop: reset, logging, naming, failure tags.
- Fine-tune on one narrow skill such as pick-place, drawer open, or peg insertion.

### Week 5-8

- Add a second camera, recovery logic, or language-conditioning.
- Measure generalization to new object instances or layouts.

## Failure modes

- underestimating calibration and dataset hygiene
- chasing frontier models before baseline execution is stable
- evaluating only cherry-picked trials

## Success check

A good first real-robot result is a pipeline you can rerun tomorrow with similar behavior, not a single successful video.

## Next step

Read [Manipulation roadmap](../roadmap/manipulation.md), [VLA roadmap](../roadmap/vla.md), and [Datasets](../resources/datasets.md).
