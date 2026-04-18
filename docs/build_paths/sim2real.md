# Build Path: Sim-to-Real

## Summary

- Audience: readers who already have a simulation result and want to transfer it.
- Outcome: a system that survives calibration drift, latency, and sensing mismatch.
- Prerequisites: one working simulation baseline, basic robot control, logging discipline.

## Minimum stack

| Layer | Recommended choice |
|---|---|
| Simulator | Isaac Lab, MuJoCo Playground, or ManiSkill |
| Real system | low-cost arm or mobile manipulator |
| Toolkit | LeRobot, ROS2, hardware driver stack |
| Evaluation | fixed task script with repeated trials and reset protocol |

## Reading core

1. sim-to-real papers from locomotion and dexterity
2. [MuJoCo Playground](https://playground.mujoco.org/)
3. [Isaac Lab](https://isaac-sim.github.io/IsaacLab/)
4. [LeRobot](https://huggingface.co/docs/lerobot/index)

## Execution plan

### Week 1-2

- Reproduce the policy in simulation with deterministic logs.
- Measure observation latency, action rate, and reset assumptions.

### Week 3-4

- Transfer to hardware with simplified tasks and safety guardrails.
- Log every failure with camera, action, and timestamp traces.

### Week 5-8

- Add domain randomization, calibration repair, or residual correction.
- Re-evaluate with a stricter real-world protocol.

## Failure modes

- treating simulator choice as the only transfer problem
- ignoring observation delay and control bandwidth
- overstating transfer by evaluating on easy initializations only

## Success check

A credible sim-to-real result explains what changed between sim and hardware, how that gap was handled, and where transfer still breaks.

## Next step

Read [Simulators](../resources/simulators.md), [Frameworks](../resources/frameworks.md), and [RL roadmap](../roadmap/rl.md).
