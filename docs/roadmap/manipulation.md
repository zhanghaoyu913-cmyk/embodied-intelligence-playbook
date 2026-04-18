<p align="center">
  <img src="../../assets/figures/banner_manipulation.svg" alt="Manipulation banner" width="100%"/>
</p>

# Manipulation

> **Manipulation is where embodied AI stops being abstract.** It must touch, align, place, recover, and finish.

<p align="center">
  <img src="../../assets/figures/flow_manipulation.svg" alt="Manipulation flow" width="92%"/>
</p>

---

## What this topic covers

Manipulation includes:

- reaching and picking
- placing and reorienting
- opening, folding, assembling, wiping, pouring, tool use
- long-horizon household and workspace tasks
- recovery under occlusion, slippage, clutter, and contact uncertainty

---

## Why it is hard

Manipulation is where perception, state estimation, contact, and control all fail together if the system is brittle. A paper that looks strong in offline evaluation may still fail in real closed-loop execution because contact and error accumulation dominate.

---

## High-value project / paper clusters

### Open-source mobile and bimanual systems
- [Mobile ALOHA](https://src.stanford.edu/demo/moble-aloha)
- [ACT](https://github.com/tonyzhaozh/act)
- [TidyBot](https://src.stanford.edu/demo/house-heroes-the-tidy-taskforce)
- [TidyBot++](https://tidybot2.github.io/)

### Dataset-driven manipulation learning
- [BridgeData V2](https://rail-berkeley.github.io/bridgedata/)
- [Open X-Embodiment](https://robotics-transformer-x.github.io/)
- [robomimic](https://robomimic.github.io/)
- [LeRobot](https://huggingface.co/docs/lerobot/index)

### Benchmarks
- [CALVIN](https://github.com/mees/calvin)
- [LIBERO](https://libero-project.github.io/main.html)
- [BEHAVIOR-1K](https://behavior.stanford.edu/index.html)

---

## Recent and classic papers worth starting from

| Work | Why it matters | Links |
|---|---|---|
| Mobile ALOHA | low-cost, whole-body mobile manipulation with strong practical influence | [official](https://src.stanford.edu/demo/moble-aloha) |
| ACT | action chunking for imitation learning on real manipulation tasks | [code](https://github.com/tonyzhaozh/act) |
| Diffusion Policy | strong and influential policy parameterization for manipulation | [project](https://diffusion-policy.cs.columbia.edu/) |
| ICRT (ICRA 2025) | in-context imitation learning via next-token prediction | [project](https://icrt.dev) |
| OpenVLA | strong open VLA baseline for manipulation | [project](https://openvla.github.io/) |
| Octo | open-source generalist manipulation policy | [project](https://octo-models.github.io/) |

---

## Practical build sequences

### Low-cost real-robot route
Mobile ALOHA / SO-101 / LeRobot → teleop demonstrations → ACT / OpenVLA fine-tuning.

### Simulation-first route
Isaac Lab / MuJoCo Playground / ManiSkill → imitation baseline → RL or world-model refinement.

### Benchmark-first route
robomimic → CALVIN / LIBERO → BEHAVIOR-1K for longer horizons.

---

## What to inspect in manipulation results

- closed-loop success, not just offline action error
- contact recovery after slight perturbations
- whether failures are due to perception, grasping, or policy timing
- whether the task requires memory or only one-shot execution
- whether the system transfers across objects and layouts

---

## Closing Thought

Manipulation research becomes much more useful when every result is interpreted as a statement about **where the stack is brittle**: perception, contact, action interface, memory, or adaptation.
