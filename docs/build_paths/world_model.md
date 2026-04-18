# Build Path: World Model

## Summary

- Audience: readers interested in predictive state, planning, and sample efficiency.
- Outcome: a benchmarked predictive-control stack, not just a video predictor.
- Prerequisites: RL basics, latent-state modeling basics, comfort with benchmark-driven iteration.

## Minimum stack

| Layer | Recommended choice |
|---|---|
| Environment | MuJoCo Playground, Meta-World, or ManiSkill |
| Baseline | DreamerV3 or TD-MPC2 |
| Evaluation | fixed control task suite plus ablation on planning horizon |
| Hardware | single strong GPU is enough for first benchmark runs |

## Reading core

1. World Models
2. PlaNet
3. [DreamerV3](https://danijar.com/project/dreamerv3/)
4. [TD-MPC2](https://www.tdmpc2.com/)
5. [MuJoCo Playground](https://playground.mujoco.org/)

## Execution plan

### Week 1-2

- Reproduce DreamerV3 or TD-MPC2 on a clean benchmark.
- Log state prediction, reward prediction, and control metrics separately.

### Week 3-4

- Compare latent planning against a strong model-free or imitation baseline.
- Test where model error starts to damage decisions.

### Week 5-8

- Add one harder condition: longer horizon, partial observability, manipulation, or offline pretraining.
- Evaluate whether the world model improves action or only prediction.

## Failure modes

- optimizing reconstruction quality instead of decision value
- not separating model quality from planner quality
- using easy resets that hide compounding prediction error

## Success check

A useful result shows that the predictive model changes planning or sample efficiency in a measurable way, not only that it produces plausible rollouts.

## Next step

Read [World Models roadmap](../roadmap/world_model.md), [RL roadmap](../roadmap/rl.md), and [Simulators](../resources/simulators.md).
