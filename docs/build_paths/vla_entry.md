# Build Path: VLA Entry

## Summary

- Audience: readers who want a practical open-source entry into vision-language-action systems.
- Outcome: a small but real VLA baseline on a tabletop benchmark or low-cost robot.
- Prerequisites: basic PyTorch, robot observation/action conventions, one week of comfort with dataset loading.

## Minimum stack

| Layer | Recommended choice |
|---|---|
| Dataset | BridgeData V2 or LeRobot-hosted manipulation data |
| Benchmark | CALVIN or LIBERO |
| Framework | OpenVLA or Octo |
| Hardware | single GPU for simulation and fine-tuning; optional ALOHA / SO-101 style setup for real robot |

## Reading core

1. [Open X-Embodiment](https://robotics-transformer-x.github.io/)
2. [Octo](https://octo-models.github.io/)
3. [OpenVLA](https://openvla.github.io/)
4. [BridgeData V2](https://rail-berkeley.github.io/bridgedata/)

## Execution plan

### Week 1-2

- Reproduce inference with OpenVLA or Octo.
- Inspect action format, camera assumptions, and prompt interface.
- Run one benchmark demo end to end.

### Week 3-4

- Fine-tune on one narrow task family.
- Compare language-conditioned and task-ID-conditioned variants.
- Record failure cases around grounding and recovery.

### Week 5-8

- Add one of: wrist camera, better recovery loop, affordance prior, or RL-style post-training.
- Evaluate on holdout objects or scenes.

## Failure modes

- treating VLA as a prompt-only problem instead of an action-interface problem
- ignoring calibration and action scaling
- claiming generality from one narrow benchmark slice

## Success check

A successful first pass is not "general robot intelligence." It is a pipeline where you can explain:

- what the instruction changes
- how actions are represented
- how failures are detected

## Next step

Read [VLA roadmap](../roadmap/vla.md), [Benchmarks](../resources/benchmarks.md), and [Industry Map](../maps/industry.md).
