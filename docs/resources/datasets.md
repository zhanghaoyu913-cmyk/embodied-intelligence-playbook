# Datasets

This page is organized by **what kind of signal you need** and **what you are trying to build**, not only by dataset name.

The core idea is simple:

- if you need **real robot execution signal**, start from real-robot corpora
- if you need **controlled comparison and benchmarking**, start from simulation and benchmark ecosystems
- if you need **human procedural priors or egocentric interaction**, use human-video corpora
- if you need **cross-embodiment transfer or world-model-style supervision**, pay attention to mixed trace and multi-embodiment datasets

---

## Quick selector

| If you want... | Start here |
|---|---|
| a generalist real-robot data backbone | Open X-Embodiment, DROID, AgiBot World |
| practical open manipulation data for building systems | BridgeData V2, LeRobot datasets, robomimic datasets |
| long-horizon language-conditioned manipulation | CALVIN, LIBERO |
| household and daily-life embodied tasks | BEHAVIOR-1K, OmniGibson |
| grasping data | GraspNet, DexGraspNet, DexGraspNet 2.0 |
| articulated-object and affordance data | PartNet-Mobility, GAPartNet, PartManip |
| humanoid or cross-embodiment signal | RoboMIND, Open X-Embodiment, AgiBot World |
| human procedural interaction priors | EPIC-KITCHENS, Ego4D, Something-Something V2 |
| mixed human + robot supervision for transferable world models | TraceForge-123K, WIYH |

---

## How to read this page

For each dataset or ecosystem, ask four questions:

1. **Where does the data come from?** real robot, simulation, human video, or a mixture?
2. **What is the supervision signal?** actions, language, traces, rewards, affordances, parts, or dense geometry?
3. **What kind of model benefits most from it?** VLA, imitation learning, RL, grasping, world model, affordance learning?
4. **How easy is it to build on top of?** Is there an official loader, benchmark suite, or code ecosystem?

---

# 1. Real-robot data

These are the highest-value datasets when your end goal is real deployment, manipulation transfer, teleoperation learning, or policy fine-tuning on physical systems.

## 1.1 Generalist and large-scale real-robot corpora

| Dataset | Type | Coverage | Modalities | Best for | Notes |
|---|---|---|---|---|---|
| [Open X-Embodiment](https://robotics-transformer-x.github.io/) | open real-robot mixture | cross-lab, cross-robot, multi-institution | RGB, proprioception, action trajectories, language in part of the ecosystem | robot foundation-policy pretraining, cross-embodiment context | strongest open ecosystem anchor for generalist robot learning |
| [DROID](https://droid-dataset.github.io/) | real-robot manipulation corpus | many scenes, many tasks, many collectors | robot trajectories, images, states, actions | open manipulation learning with broad real-world diversity | especially valuable because it couples data with a replicable collection platform |
| [AgiBot World](https://github.com/OpenDriveLab/AgiBot-World) | large-scale real-robot platform dataset | multi-scene, multi-skill, embodied manipulation | multimodal robot observations and trajectories | humanoid / embodied data scaling, China-side ecosystem tracking | important when watching large-scale homogeneous robot data pipelines |
| [RoboMIND](https://x-humanoid-robomind.github.io/) | multi-embodiment teleoperation dataset | multiple embodiments and task families | multi-view observations, proprioception, task descriptions, demonstrations | embodiment transfer and policy comparison across robot forms | very useful if you care about cross-embodiment rather than single-arm learning |

### Notes

- **Open X-Embodiment** is usually the best *reference backbone* when you want to understand the open generalist-robot data landscape.
- **DROID** is often the best answer when you want **diverse real-robot manipulation** with a strong practical data-collection story.
- **AgiBot World** matters because it signals how large-scale robot data collection is evolving in the China-side embodied ecosystem.
- **RoboMIND** matters because it makes **multi-embodiment transfer** a first-class concern rather than an afterthought.

## 1.2 Practical manipulation data for builders

| Dataset | Type | Coverage | Modalities | Best for | Notes |
|---|---|---|---|---|---|
| [BridgeData V2](https://rail-berkeley.github.io/bridgedata/) | real-robot manipulation corpus | multi-task, multi-environment tabletop manipulation | RGB, trajectories, goal context, language-compatible ecosystem | manipulation fine-tuning, open-vocabulary or goal-conditioned learning | one of the most useful open manipulation anchors for small-to-medium research teams |
| [LeRobot datasets](https://huggingface.co/docs/lerobot/index) | hosted practical dataset collection | low-cost arms and practical setups | RGB, proprioception, teleop logs | short path from data to training to deployment | strongest tooling path for people who want something buildable now |
| [robomimic datasets](https://robomimic.github.io/) | imitation-learning benchmark data | canonical manipulation tasks | demonstrations, states, images | behavior cloning, diffusion policy, imitation-learning baselines | excellent when you want a clean baseline before scaling up |
| [Mobile ALOHA / ACT ecosystem](https://src.stanford.edu/demo/moble-aloha) | system-centered real-robot data ecosystem | mobile manipulation and teleop-heavy workflows | multi-camera teleop trajectories and actions | learning from teleoperation, low-cost system building | more of a system ecosystem than a standalone dataset page, but highly influential |

### Notes

- If you are a **builder first**, do not begin with the biggest corpus.
- A more reliable path is often: **LeRobot / robomimic / BridgeData V2 → baseline policy → task-specific expansion**.
- BridgeData V2 is especially good when you want something more realistic than toy imitation datasets, but not as infrastructure-heavy as the largest mixtures.

---

# 2. Simulation and benchmark ecosystems

These are best when you need controlled evaluation, repeatable comparison, or large-scale training that would be too expensive on real robots.

## 2.1 Long-horizon and language-conditioned manipulation benchmarks

| Dataset / benchmark | Type | Coverage | Modalities | Best for | Notes |
|---|---|---|---|---|---|
| [CALVIN](https://github.com/mees/calvin) | benchmark + dataset ecosystem | long-horizon tabletop manipulation | RGB, language, proprioception | instruction-conditioned long-horizon manipulation | benchmark and training ecosystem are tightly coupled |
| [LIBERO](https://libero-project.github.io/main.html) | benchmark suite | task families for lifelong / compositional manipulation | vision, state, task context | compositional generalization and lifelong evaluation | strong choice for structured policy comparison |
| [Meta-World](https://meta-world.github.io/) | RL benchmark suite | many manipulation tasks in simulation | low-dimensional states, robot control loops | RL and meta-RL comparison | still a common control benchmark, though less visually rich |
| [ManiSkill](https://maniskill.ai/) | simulation benchmark and toolkit | visual manipulation tasks in physics simulation | RGB-D, states, physics interaction | sim-first manipulation and benchmark reproduction | strong when you want scalable simulated manipulation |

## 2.2 Household and embodied-environment ecosystems

| Dataset / ecosystem | Type | Coverage | Modalities | Best for | Notes |
|---|---|---|---|---|---|
| [BEHAVIOR-1K](https://behavior.stanford.edu/index.html) | benchmark ecosystem | broad household activities | rich semantic scenes and task structures | large-scope household embodied evaluation | environment-heavy but essential if you care about household realism |
| [OmniGibson](https://behavior.stanford.edu/omnigibson/) | simulation environment | household manipulation and embodied tasks | embodied simulation, 3D scenes, object semantics | household simulation and BEHAVIOR-compatible work | useful for researchers bridging world models, planning, and daily-life tasks |
| [SAPIEN](https://sapien.ucsd.edu/) | simulation engine | articulated-object interaction and robotics | 3D articulated scenes and interactions | articulated manipulation and affordance-heavy tasks | especially important for part-aware and affordance work |
| [Isaac Lab](https://isaac-sim.github.io/IsaacLab/) | simulator and training ecosystem | control, manipulation, locomotion, humanoids | simulation states, visual sensors, physics | large-scale simulation training and RL | more of a framework ecosystem, but too important not to note in the data stack |

### Notes

- **Simulation ecosystems** are not just “fake data.” They define what is benchmarked, what is easy to reproduce, and which algorithmic claims are actually comparable.
- If you care about **RL**, **control**, or **world-model planning**, you usually need these environments even if your final target is real robot deployment.

---

# 3. Human video and egocentric interaction data

These datasets are not robot-action logs, but they are increasingly important for learning procedural priors, egocentric interaction understanding, action-centric perception, and cross-embodiment world modeling.

## 3.1 Human egocentric and action-centric corpora

| Dataset | Type | Coverage | Modalities | Best for | Notes |
|---|---|---|---|---|---|
| [EPIC-KITCHENS](https://epic-kitchens.github.io/) | egocentric human video dataset | kitchen activities and object interactions | egocentric video, action labels, narrations | human procedural priors and interaction understanding | one of the most useful human-video anchors for embodied interaction |
| [Ego4D](https://ego4d-data.org/) | large egocentric dataset and benchmark suite | daily-life first-person activities | egocentric video, narrations, benchmark annotations | multimodal egocentric understanding and world-model pretraining | especially valuable if you care about human-centric embodied perception |
| [Something-Something V2](https://www.qualcomm.com/developer/software/something-something-v-2-dataset) | human action video dataset | fine-grained object-centric actions | video and temporal action labels | temporal reasoning about object interaction | useful when the goal is action-centric representation rather than robot execution |

### Notes

- These datasets do **not** give you robot torques or directly executable action trajectories.
- What they do give you is a richer prior over **how interaction unfolds over time**, especially in cluttered or egocentric settings.
- They are most valuable for **representation learning, world models, video pretraining, task semantics, and cross-embodiment reasoning**.

---

# 4. Mixed human + robot signal and cross-embodiment corpora

This is the category that has become much more important in 2025–2026.

These datasets or pipelines matter when you want to learn from **heterogeneous sources** rather than one robot, one embodiment, or one benchmark at a time.

## 4.1 Mixed-source and trace-oriented supervision

| Dataset / pipeline | Type | Coverage | Modalities | Best for | Notes |
|---|---|---|---|---|---|
| [TraceGen / TraceForge-123K](https://arxiv.org/abs/2511.21690) | mixed human + robot trace-supervision corpus | tabletop, egocentric, and in-the-wild videos | observation, trace, language triplets | cross-embodiment world modeling and transferable motion priors | important because it unifies heterogeneous videos into a common trace-space signal |
| [WIYH](https://wiyh.tars-ai.com/) | large-scale multimodal embodied dataset | real-world human manipulation and multimodal embodied interaction | multimodal human-operation signals, including tactile-oriented embodied context | human-to-robot transfer, industrial and real-world embodied priors | especially interesting because it pushes beyond pure VLA into richer multimodal embodied signal |
| [RoboMIND](https://x-humanoid-robomind.github.io/) | multi-embodiment robot corpus | multiple robot forms and tasks | multimodal robot demonstrations | embodiment transfer and multi-robot comparison | belongs here too because it emphasizes cross-embodiment structure |
| [Open X-Embodiment](https://robotics-transformer-x.github.io/) | open robot mixture | cross-lab and cross-robot | robot trajectories and multimodal observations | generalist robot transfer | still the most important open baseline context for embodiment diversity |

### Notes

- This category is where the old boundary between “video pretraining” and “robot learning” starts to blur.
- If your research question sounds like **“Can we transfer action structure across embodiments?”** or **“Can a world model learn from both human and robot videos?”**, this is the section to study first.

---

# 5. Task-specific dataset families

Not every project needs the largest mixture. Many projects benefit more from a dataset family that is tightly aligned with the target task.

## 5.1 Grasping and dexterity

| Dataset | Type | Coverage | Modalities | Best for | Notes |
|---|---|---|---|---|---|
| [GraspNet](https://graspnet.net/) | grasping benchmark | cluttered-scene 6-DoF grasping | RGB-D, point cloud, grasp annotations | grasp pose detection and cluttered-scene grasping | standard reference set for modern 6-DoF grasping |
| [DexGraspNet](https://pku-epic.github.io/DexGraspNet/) | synthetic dexterous grasp dataset | multi-finger robotic hands | synthetic grasp annotations and object geometry | dexterous grasp generation and evaluation | useful when parallel-jaw assumptions are too limiting |
| [DexGraspNet 2.0](https://pku-epic.github.io/DexGraspNet2.0/) | cluttered dexterous grasp benchmark | dexterous hands in harder cluttered scenes | synthetic clutter scenes and grasp labels | harder dexterous grasping studies | better frontier signal for dexterous grasping than older clean-scene setups |
| [TransCG](https://graspnet.net/transcg) | sensing-challenging grasping benchmark | transparent-object grasping | RGB-D / challenging perception signal | robustness in difficult visual conditions | useful when the hard part is sensing rather than contact alone |

## 5.2 Affordance and articulated-object interaction

| Dataset | Type | Coverage | Modalities | Best for | Notes |
|---|---|---|---|---|---|
| [PartNet-Mobility](https://sapien.ucsd.edu/browse) | articulated-object dataset | hinges, doors, drawers, handles, articulated parts | articulated object structure and mobility annotations | affordance reasoning and articulated interaction | essential for part-aware embodied interaction |
| [GAPartNet](https://pku-epic.github.io/GAPartNet/) | part-level benchmark | part segmentation and interaction-relevant object structure | geometry, parts, segmentation annotations | part-aware manipulation and perception | bridges perception and interaction nicely |
| [PartManip](https://pku-epic.github.io/PartManip/) | articulated manipulation benchmark | cross-category part manipulation | point cloud observations and interaction annotations | articulation-aware policy learning | especially useful if you want evaluation tied directly to manipulation |
| [AffordanceNet](https://github.com/wliu88/affordance_net) | classical affordance benchmark | object affordance prediction | RGB affordance labels | dense affordance prediction baselines | classical and still useful for historical grounding |

---

# 6. Dataset families by research objective

Sometimes the easiest way to choose data is not by source type, but by **what you are trying to build**.

## 6.1 If you are building a VLA system

Start with:

- [Open X-Embodiment](https://robotics-transformer-x.github.io/)
- [DROID](https://droid-dataset.github.io/)
- [BridgeData V2](https://rail-berkeley.github.io/bridgedata/)
- [LeRobot datasets](https://huggingface.co/docs/lerobot/index)
- [CALVIN](https://github.com/mees/calvin)

Best when you want:

- instruction grounding
- multi-task manipulation
- open training recipes
- task fine-tuning on practical robot setups

## 6.2 If you are building a world model

Start with:

- [Ego4D](https://ego4d-data.org/)
- [EPIC-KITCHENS](https://epic-kitchens.github.io/)
- [TraceGen / TraceForge-123K](https://arxiv.org/abs/2511.21690)
- [RoboMIND](https://x-humanoid-robomind.github.io/)
- [Open X-Embodiment](https://robotics-transformer-x.github.io/)

Best when you want:

- future prediction
- cross-embodiment transfer
- egocentric priors
- observation-to-dynamics abstraction rather than direct policy cloning

## 6.3 If you are building a manipulation stack

Start with:

- [BridgeData V2](https://rail-berkeley.github.io/bridgedata/)
- [robomimic](https://robomimic.github.io/)
- [LeRobot datasets](https://huggingface.co/docs/lerobot/index)
- [CALVIN](https://github.com/mees/calvin)
- [LIBERO](https://libero-project.github.io/main.html)

Best when you want:

- behavior cloning baselines
- practical training pipelines
- long-horizon manipulation comparison
- reproducible benchmark-first experimentation

## 6.4 If you are building grasping or dexterity systems

Start with:

- [GraspNet](https://graspnet.net/)
- [DexGraspNet](https://pku-epic.github.io/DexGraspNet/)
- [DexGraspNet 2.0](https://pku-epic.github.io/DexGraspNet2.0/)
- [PartNet-Mobility](https://sapien.ucsd.edu/browse)

Best when you want:

- 6-DoF grasping
- dexterous grasping
- clutter robustness
- part-aware interaction priors

## 6.5 If you are studying affordance and articulated interaction

Start with:

- [PartNet-Mobility](https://sapien.ucsd.edu/browse)
- [GAPartNet](https://pku-epic.github.io/GAPartNet/)
- [PartManip](https://pku-epic.github.io/PartManip/)
- [AffordanceNet](https://github.com/wliu88/affordance_net)

Best when you want:

- part reasoning
- functional-region prediction
- articulated-object manipulation
- geometry-aware interaction learning

---

# 7. Suggested build paths

## Path A — practical real-robot builder

Start with:

1. LeRobot datasets
2. robomimic or BridgeData V2
3. one practical manipulation benchmark
4. task-specific fine-tuning on your own robot

Good when you want the shortest path to something buildable.

## Path B — generalist policy learner

Start with:

1. Open X-Embodiment
2. DROID
3. BridgeData V2
4. CALVIN / LIBERO for evaluation and adaptation

Good when you care about generalization rather than one robot only.

## Path C — world-model and cross-embodiment researcher

Start with:

1. Ego4D / EPIC-KITCHENS
2. TraceGen / TraceForge-123K
3. RoboMIND / Open X-Embodiment
4. simulation or downstream manipulation tasks for control validation

Good when the goal is state abstraction, prediction, and transfer.

## Path D — grasping and affordance specialist

Start with:

1. GraspNet
2. DexGraspNet or DexGraspNet 2.0
3. PartNet-Mobility / GAPartNet / PartManip
4. downstream manipulation tasks

Good when contact choice and interaction geometry are central.

---

# 8. Practical notes

- If you are new, choose the dataset that already matches your **framework** and **evaluation benchmark**.
- If you want fast progress, do **not** start from the largest cross-lab corpus.
- If you want to study **world models**, do not restrict yourself to robot-only data.
- If you want to study **deployment**, prefer real-robot datasets with strong tooling over visually impressive but hard-to-use corpora.
- If you want **cross-embodiment transfer**, look specifically for datasets that mix robot types, collection sites, or human and robot sources.

---

# 9. Recommended cross-links

Use this page together with:

- [Benchmarks](benchmarks.md)
- [Frameworks](frameworks.md)
- [Simulators](simulators.md)
- [Manipulation](../roadmap/manipulation.md)
- [Grasping](../roadmap/grasping.md)
- [Affordance Learning](../roadmap/affordance.md)
- [World Models](../roadmap/world_model.md)
- [Reinforcement Learning](../roadmap/rl.md)

---

# 10. One guiding rule

The best dataset is usually **not** the biggest one.

It is the one whose:

- signal matches your problem,
- tooling matches your stack,
- benchmark matches your claim,
- and embodiment matches your eventual deployment target.
