# Datasets

This page is organized first by **what kind of data you need**, then by **what you are trying to build**.

The practical split used here is:

1. **real-robot data** — the best starting point when you want policies that can actually transfer
2. **simulation / benchmark ecosystems** — the best starting point when you need scale, resetability, and controlled evaluation
3. **human / cross-embodiment signal** — increasingly important when you care about generalization, world models, or learning from heterogeneous videos
4. **task-specific data families** — grasping, affordance, articulated interaction, long-horizon manipulation, humanoids

---

## Quick selector

| If you want... | Start here |
|---|---|
| a generalist real-robot backbone | Open X-Embodiment, AgiBot World, RoboMIND |
| practical open manipulation data with a short build path | LeRobot datasets, BridgeData V2, robomimic |
| long-horizon language-conditioned manipulation | CALVIN, LIBERO |
| household embodied tasks and evaluation | BEHAVIOR-1K |
| grasping data | GraspNet, DexGraspNet, DexGraspNet 2.0 |
| articulated-object and affordance signal | PartNet-Mobility, GAPartNet, PartManip, AffordanceNet |
| humanoid or cross-embodiment signal | RoboMIND, AgiBot World, Open X-Embodiment |
| human manipulation and in-the-wild multimodal signal | WIYH |
| simulation-first embodied training | ManiSkill / SAPIEN, Meta-World, Isaac Lab, OmniGibson |

---

## A better way to read dataset pages

Before choosing a dataset, ask five questions:

1. **Is the data real, simulated, or human-only?**
2. **What is the action interface?**
3. **Does it include language, failures, or only successful demonstrations?**
4. **Is there a working code ecosystem around it?**
5. **Does it match my target embodiment and evaluation benchmark?**

---

# I. Real-robot data

These are the highest-value datasets when your end goal is deployment, adaptation, or realistic manipulation policies.

## 1. Generalist real-robot corpora

| Dataset | Type | Scale / coverage | Modalities | Best for | Links | Notes |
|---|---|---|---|---|---|---|
| Open X-Embodiment | real robot, multi-source | large cross-lab mixture across many robot families | RGB, proprioception, trajectories, language in parts of the ecosystem | open generalist policy training, cross-embodiment context | [project](https://robotics-transformer-x.github.io/) · [code](https://github.com/google-deepmind/open_x_embodiment) | still the most important open anchor for generalist robot-data training |
| AgiBot World | real robot, large-scale embodied data platform | 1M+ trajectories, open-source dataset + GO-1 foundation model ecosystem | vision, robot state, actions, task signals; extensible to dexterous and visuo-tactile settings | humanoid-scale data, Chinese embodied ecosystem, large-scale real data | [project](https://agibot-world.com/) · [GitHub](https://github.com/OpenDriveLab/AgiBot-World) · [paper](https://arxiv.org/abs/2503.06669) | strong new anchor if you want to track large-scale real embodied data beyond Open X |
| RoboMIND | real robot, multi-embodiment teleoperation | 107k trajectories, 479 tasks, 96 object classes, 4 embodiments, plus failure demos | multi-view observations, proprioception, language, failures | unified teleop data, cross-embodiment manipulation, humanoid signal | [project](https://x-humanoid-robomind.github.io/) · [dataset](https://huggingface.co/datasets/x-humanoid-robomind/RoboMIND) · [paper](https://arxiv.org/abs/2412.13877) | especially useful because it includes both embodiment diversity and failure data |
| BridgeData V2 | real robot manipulation | large manipulation corpus in Berkeley ecosystem | RGB, actions, task context | manipulation fine-tuning, open manipulation transfer | [project](https://rail-berkeley.github.io/bridgedata/) | one of the most useful practical open manipulation anchors |
| LeRobot datasets | real robot, practical hosted collections | growing practical collection | RGB, proprioception, teleop logs | builders who want a short path from data to training | [docs](https://huggingface.co/docs/lerobot/index) | strongest practical tooling path for small teams |

## 2. Practical manipulation and imitation data

| Dataset / ecosystem | Type | Coverage | Modalities | Best for | Links | Notes |
|---|---|---|---|---|---|---|
| robomimic datasets | real robot / benchmark ecosystem | standard manipulation tasks | demos, manipulation logs, observation/action pairs | imitation-learning baselines, reproducible comparisons | [project](https://robomimic.github.io/) | BC-first builders should almost always know this stack |
| Mobile ALOHA data ecosystem | real robot teleoperation | mobile manipulation, low-cost real setup | teleop trajectories, multi-camera data | teleop-centric manipulation learning | [project](https://src.stanford.edu/demo/moble-aloha) · [ACT code](https://github.com/tonyzhaozh/act) | influential because many practical low-cost real-robot paths trace back here |

---

# II. Simulation and benchmark ecosystems

These are not always "datasets" in the narrow sense, but they are where many embodied pipelines actually get trained, scaled, or evaluated.

## 1. Long-horizon and benchmark-first stacks

| Dataset / benchmark | Type | Coverage | Modalities | Best for | Links | Notes |
|---|---|---|---|---|---|---|
| CALVIN | benchmark + dataset | long-horizon language-conditioned tabletop tasks | RGB, language, proprioception | instruction-conditioned manipulation | [project](https://github.com/mees/calvin) | benchmark and dataset ecosystem together |
| LIBERO | benchmark suite | compositional and lifelong manipulation tasks | vision, state, task context | structured policy comparison | [project](https://libero-project.github.io/main.html) | strong benchmark for systematic comparison |
| BEHAVIOR-1K | environment + benchmark | broad household activities | rich scene and task semantics | household embodied evaluation | [project](https://behavior.stanford.edu/index.html) | environment-heavy but essential for household scope |
| Meta-World | benchmark suite | multi-task robot manipulation | state and control-centered task setups | RL and policy benchmarking | [project](https://meta-world.github.io/) | foundational benchmark for multi-task manipulation |

## 2. Simulation-first training ecosystems

| Ecosystem | Type | Coverage | Best for | Links | Notes |
|---|---|---|---|---|---|
| ManiSkill | simulator + task suite | manipulation in simulation | simulation-first training and evaluation | [project](https://maniskill.ai/) | one of the best simulation-first manipulation stacks |
| SAPIEN | simulator | articulated objects, interaction-rich scenes | articulated manipulation and affordance research | [project](https://sapien.ucsd.edu/) | deeply tied to PartNet-Mobility and related datasets |
| Isaac Lab | simulation / training framework | large-scale robot RL and embodied training | RL, humanoids, sim-to-real workflows | [project](https://isaac-sim.github.io/IsaacLab/) | best viewed as infrastructure tightly linked to data generation |
| OmniGibson | household simulation ecosystem | rich household tasks | household embodied agents and environment generation | [project](https://behavior.stanford.edu/omnigibson/) | naturally paired with BEHAVIOR |

---

# III. Human data and cross-embodiment signal

This category matters more than many newcomers expect. Even when the final policy is robot-only, human and cross-embodiment data increasingly matter for world models, visual priors, success judgment, and task abstraction.

| Dataset / signal source | Type | Coverage | Best for | Links | Notes |
|---|---|---|---|---|---|
| WIYH (World In Your Hands) | human manipulation, real-world, in-the-wild | 1000+ hours of human manipulation with multimodal annotations | human-centric embodied pretraining, spatial relation understanding, task completion reasoning | [project](https://wiyh.tars-ai.com/) · [paper](https://arxiv.org/abs/2512.24310) | strongest recent human-centric embodied dataset signal to track |
| TraceGen-style source videos | cross-embodiment video signal | human and cross-robot videos transformed into trace-space world modeling signal | world-model pretraining, cross-embodiment transfer, few-shot task learning | [paper](https://arxiv.org/abs/2511.21690) | less a standalone dataset page and more a reminder that heterogeneous videos are becoming useful supervision |
| Open X-Embodiment | robot multi-source | cross-lab, cross-robot mixture | embodiment transfer context | [project](https://robotics-transformer-x.github.io/) | still relevant here because embodiment diversity is part of its core value |
| RoboMIND | robot multi-embodiment teleop | four embodiments, failures, real manipulation | cross-embodiment learning on a unified collection protocol | [project](https://x-humanoid-robomind.github.io/) | one of the cleanest bridges between multi-embodiment data and practical robot learning |

---

# IV. Task-specific dataset families

## 1. Grasping and dexterity

| Dataset | Type | Coverage | Best for | Links | Notes |
|---|---|---|---|---|---|
| GraspNet | grasping benchmark | cluttered-scene parallel-jaw grasping | 6-DoF grasp detection | [project](https://graspnet.net/) | standard reference for grasping in clutter |
| DexGraspNet | synthetic dexterous grasp data | multi-finger hands | dexterous grasp modeling | [project](https://pku-epic.github.io/DexGraspNet/) | useful when parallel-jaw assumptions stop being enough |
| DexGraspNet 2.0 | cluttered dexterous grasp benchmark | dexterous hands in harder scenes | harder dexterous grasp studies | [project](https://pku-epic.github.io/DexGraspNet2.0/) | frontier dexterous benchmark signal |
| TransCG | difficult sensing grasp set | transparent-object grasping | robustness under hard sensing | [project](https://graspnet.net/transcg) | useful when you care about sensing failure, not only geometry |

## 2. Affordance and articulated interaction

| Dataset | Type | Coverage | Best for | Links | Notes |
|---|---|---|---|---|---|
| PartNet-Mobility | articulated object dataset | articulated geometry and part structure | hinges, handles, drawers, part-aware interaction | [browse](https://sapien.ucsd.edu/browse) | essential for affordance and articulated manipulation |
| GAPartNet | part-aware benchmark | part segmentation and structure | part-centric reasoning and execution | [project](https://pku-epic.github.io/GAPartNet/) | bridge between perception and interaction |
| PartManip | articulated manipulation benchmark | part-aware manipulation data | articulation-aware policies | [project](https://pku-epic.github.io/PartManip/) | useful if you want evaluation tied directly to manipulation |
| AffordanceNet | classical affordance benchmark | RGB affordance labels | dense affordance prediction | [code](https://github.com/wliu88/affordance_net) | classical baseline rather than a modern full embodied stack |

## 3. Humanoid and cross-embodiment signal

| Dataset | Type | Coverage | Best for | Links | Notes |
|---|---|---|---|---|---|
| RoboMIND | real robot, multi-embodiment | four embodiments + failures | humanoid and cross-embodiment manipulation signal | [project](https://x-humanoid-robomind.github.io/) | especially strong because collection protocol is unified |
| AgiBot World | large-scale real robot platform | humanoid-scale embodied data + GO-1 ecosystem | large-scale humanoid data watching | [project](https://agibot-world.com/) | key China-side dataset to track |
| Open X-Embodiment | large open mixture | cross-robot, cross-lab | embodiment transfer context | [project](https://robotics-transformer-x.github.io/) | still the broadest open generalist anchor |

---

# V. Suggested reading / building paths

## Path A — you want a practical small-team start
Start with:
1. LeRobot datasets
2. robomimic
3. BridgeData V2
4. one benchmark such as LIBERO or CALVIN

## Path B — you want generalist robot policy context
Start with:
1. Open X-Embodiment
2. BridgeData V2
3. Octo / OpenVLA / RT-X ecosystem
4. then compare against AgiBot World and RoboMIND

## Path C — you want humanoid or China-side embodied signal
Start with:
1. RoboMIND
2. AgiBot World
3. Unitree / AGIBOT / Open-X-Humanoid toolchains
4. then inspect what is open enough to actually reproduce

## Path D — you want affordance / articulated manipulation
Start with:
1. PartNet-Mobility
2. SAPIEN
3. GAPartNet / PartManip
4. then connect to grasping or manipulation policies

## Path E — you want world-model or cross-embodiment signal
Start with:
1. WIYH
2. TraceGen
3. Open X-Embodiment / RoboMIND
4. then ask what representation transfers across embodiments

---

# VI. Practical notes

- If you are new, choose the dataset that already matches your framework and benchmark.
- If your goal is a real robot, real data should dominate your final training and evaluation story.
- If your goal is a paper baseline, benchmark compatibility matters more than dataset prestige.
- If your goal is world models, do not ignore human and cross-embodiment signal.
- If your goal is humanoids, watch not only datasets but also the surrounding training toolchain.

## Cross-links

- [Benchmarks](benchmarks.md)
- [Frameworks](frameworks.md)
- [Simulators](simulators.md)
- [Industry Map](../maps/industry.md)
- [Academia Map](../maps/academia.md)
