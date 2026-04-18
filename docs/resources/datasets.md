# Datasets

This page collects practical datasets and benchmark suites that repeatedly appear in embodied-intelligence work.

---

## Recommended first datasets by use case

| Goal | Start here |
|---|---|
| open generalist robot policies | [Open X-Embodiment](#open-x-embodiment) |
| accessible real-robot manipulation data | [BridgeData V2](#bridgedata-v2) |
| long-horizon language-conditioned manipulation | [CALVIN](#calvin) |
| transfer and lifelong-learning evaluation | [LIBERO](#libero) |
| simulated 6-DoF multi-task manipulation | [RLBench](#rlbench) |
| grasping in clutter | [GraspNet-1Billion](#graspnet-1billion) |
| articulated objects and affordance | [PartNet-Mobility](#partnet-mobility), [3D-AffordanceNet](#3d-affordancenet), [GAPartNet](#gapartnet) |

---

## Open X-Embodiment

Large-scale multi-lab real-robot dataset mixture; a core data source for recent generalist robot policy work.

- Why it matters: multi-embodiment, multi-dataset, large-scale open data
- Good for: VLA, generalist policies, embodiment transfer studies

Links:
- [Project](https://robotics-transformer-x.github.io/)
- [Code / dataset tooling](https://github.com/google-deepmind/open_x_embodiment)

---

## BridgeData V2

A practical large-scale manipulation dataset built around accessible low-cost robots.

- Why it matters: scalable, reproducible, language/goal-conditioned robot learning
- Good for: goal-conditioned BC, language-conditioned policies, low-cost real-robot research

Links:
- [Project](https://rail-berkeley.github.io/bridgedata/)
- [Code](https://github.com/rail-berkeley/bridge_data_v2)

---

## RoboNet

A classic multi-robot dataset for visual dynamics and transfer.

- Why it matters: one of the foundational multi-robot visual prediction datasets
- Good for: world models, inverse dynamics, visual prediction, transfer

Links:
- [Paper](https://arxiv.org/abs/1910.11215)
- [Code](https://github.com/SudeepDasari/RoboNet)

---

## CALVIN

Long-horizon language-conditioned manipulation benchmark.

- Why it matters: one of the clearest evaluation setups for chaining instructions over multiple steps
- Good for: long-horizon policies, language-conditioned control, evaluation under sequential execution

Links:
- [Project](https://calvin.cs.uni-freiburg.de/)
- [Code](https://github.com/mees/calvin)

---

## LIBERO

Lifelong and transfer-oriented robot-learning benchmark suite.

- Why it matters: good benchmark when the question is not only “can it do a task?” but also “can it transfer?”
- Good for: knowledge transfer, multi-task learning, continual/lifelong learning

Links:
- [Project](https://libero-project.github.io/main.html)
- [Datasets](https://libero-project.github.io/datasets)
- [Code](https://github.com/Lifelong-Robot-Learning/LIBERO)

---

## RLBench

Large-scale simulated manipulation benchmark based on CoppeliaSim / PyRep.

- Why it matters: standardized multi-task manipulation environment with many tasks and variations
- Good for: imitation learning, language-conditioned manipulation, 3D action-centric baselines

Links:
- [Website](https://sites.google.com/view/rlbench)
- [Code](https://github.com/stepjam/RLBench)

---

## FurnitureBench

Real-world furniture assembly benchmark.

- Why it matters: one of the strongest practical benchmarks for long-horizon manipulation
- Good for: dexterous long-horizon assembly, real-robot imitation learning, system integration

Links:
- [Project](https://clvrai.github.io/furniture-bench/)

---

## GraspNet-1Billion

Canonical cluttered-scene grasp benchmark for 6-DoF grasping.

- Why it matters: dense labels, real RGB-D scenes, mature evaluation ecosystem
- Good for: grasp generation, grasp scoring, 6D pose + grasp pipelines

Links:
- [Project](https://graspnet.net/)
- [Paper](https://openaccess.thecvf.com/content_CVPR_2020/papers/Fang_GraspNet-1Billion_A_Large-Scale_Benchmark_for_General_Object_Grasping_CVPR_2020_paper.pdf)

---

## PartNet-Mobility

Articulated-object asset collection with motion annotations.

- Why it matters: foundational for articulated-object affordance and manipulation work
- Good for: doors, drawers, lids, handles, articulated interaction

Links:
- [Browse assets](https://sapien.ucsd.edu/browse)
- [SAPIEN](https://sapien.ucsd.edu/)

---

## 3D-AffordanceNet

Point-cloud benchmark for object affordance understanding.

- Why it matters: a canonical 3D affordance benchmark with multiple affordance classes
- Good for: pointwise affordance prediction, 3D grounding, affordance transfer studies

Links:
- [Project](https://andlollipopde.github.io/3D-AffordanceNet/)
- [Paper](https://arxiv.org/abs/2103.16397)
- [Code](https://github.com/Gorilla-Lab-SCUT/AffordanceNet)

---

## GAPartNet

Part-centric interactive dataset focused on generalizable, actionable parts.

- Why it matters: bridges perception and manipulation at the part level
- Good for: part segmentation, articulated-object reasoning, cross-category manipulation

Links:
- [Project](https://pku-epic.github.io/GAPartNet/)
- [Code](https://github.com/PKU-EPIC/GAPartNet)

---

## VIMA-Bench

Prompt-centric manipulation benchmark that pairs well with VIMA-style work.

- Why it matters: useful for multimodal prompting and systematic generalization studies
- Good for: prompt-based manipulation, multimodal task specification

Links:
- [Benchmark code](https://github.com/vimalabs/vimabench)

---

## General 3D assets worth knowing

| Asset set | Use case | Link |
|---|---|---|
| YCB | standard tabletop objects | [Website](http://ycb-benchmarks.s3-website-us-east-1.amazonaws.com/) |
| PartNet | fine-grained part annotations for object understanding | [Website](https://partnet.cs.stanford.edu/) |
| Objaverse-XL | large-scale general 3D assets | [Dataset](https://huggingface.co/datasets/allenai/objaverse-xl) |

---

## How to choose a dataset

### Choose by supervision type
- demonstrations → BridgeData V2, Open X, FurnitureBench
- benchmark evaluation → CALVIN, LIBERO, RLBench
- grasp labels → GraspNet
- articulated affordance / part structure → PartNet-Mobility, GAPartNet, 3D-AffordanceNet

### Choose by embodiment
- general robot mixtures → Open X
- low-cost real robot → BridgeData V2, ALOHA-style data collection
- fixed simulated arm → CALVIN, RLBench, LIBERO
- articulated object focus → SAPIEN / PartNet-Mobility ecosystem

### Choose by research question
- generalist policy → Open X / Octo / OpenVLA
- long horizon → CALVIN / FurnitureBench
- transfer → LIBERO
- grasping → GraspNet
- affordance → 3D-AffordanceNet / GAPartNet / Where2Act ecosystem
