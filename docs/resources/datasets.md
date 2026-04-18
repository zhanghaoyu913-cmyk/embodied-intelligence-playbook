# Datasets

This page is organized by what a reader is trying to build, not only by dataset name.

## Quick selector

| If you want... | Start here |
|---|---|
| a generalist robot-data backbone | Open X-Embodiment, BridgeData V2 |
| practical open manipulation data | LeRobot datasets, robomimic data |
| long-horizon language-conditioned tasks | CALVIN, LIBERO |
| household and human-centered tasks | BEHAVIOR-1K |
| grasping data | GraspNet, DexGraspNet |
| articulated-object and affordance data | PartNet-Mobility, GAPartNet, PartManip |
| humanoid or cross-embodiment signal | RoboMIND, Open X-Embodiment |

## Generalist robot data

| Dataset | Scale | Embodiment coverage | Modalities | License / access | Code ecosystem | Best for | Notes |
|---|---|---|---|---|---|---|---|
| [Open X-Embodiment](https://robotics-transformer-x.github.io/) | large cross-lab mixture | many robot families | RGB, proprioception, action trajectories, language in parts of the ecosystem | open project ecosystem | RT-X and community loaders | robot foundation-policy training | strongest open ecosystem anchor for cross-embodiment policy work |
| [BridgeData V2](https://rail-berkeley.github.io/bridgedata/) | large manipulation corpus | manipulation robots and lab settings | RGB, action trajectories, task context | public project release | BridgeData tooling and Berkeley ecosystem | manipulation fine-tuning and benchmark-aligned training | one of the most useful open manipulation data anchors |
| [LeRobot datasets](https://huggingface.co/docs/lerobot/index) | growing hosted dataset collection | low-cost arms and practical setups | RGB, proprioception, teleop logs | Hugging Face-hosted access | LeRobot | practical small-to-medium reproduction | most useful for builders who want a clean tooling path |

## Manipulation and long-horizon task data

| Dataset / benchmark | Scale | Embodiment coverage | Modalities | License / access | Code ecosystem | Best for | Notes |
|---|---|---|---|---|---|---|---|
| [CALVIN](https://github.com/mees/calvin) | benchmark-scale long-horizon tasks | tabletop arm | RGB, language, proprioception | public benchmark project | CALVIN stack | instruction-conditioned long-horizon manipulation | benchmark and dataset ecosystem together |
| [LIBERO](https://libero-project.github.io/main.html) | benchmark suite with task families | tabletop arm | vision, state, task context | public benchmark project | LIBERO | compositional and lifelong manipulation | strong for structured policy comparison |
| [BEHAVIOR-1K](https://behavior.stanford.edu/index.html) | very broad household activity suite | household embodied agents | rich scene and task semantics | academic project access | OmniGibson / BEHAVIOR stack | household activity evaluation | environment-heavy but crucial for household scope |
| [robomimic datasets](https://robomimic.github.io/) | standard imitation datasets | manipulation arms | demonstrations and manipulation logs | public benchmark ecosystem | robomimic | imitation-learning baselines | strong for BC-first builders |

## Grasping and dexterity

| Dataset | Scale | Embodiment coverage | Modalities | License / access | Code ecosystem | Best for | Notes |
|---|---|---|---|---|---|---|---|
| [GraspNet](https://graspnet.net/) | benchmark-scale | parallel-jaw grasping | RGB-D, point cloud | public benchmark access | GraspNet baseline ecosystem | 6-DoF grasp detection | standard reference set for cluttered-scene grasping |
| [DexGraspNet](https://pku-epic.github.io/DexGraspNet/) | large synthetic dataset | dexterous hands | synthetic dexterous grasp data | public project release | DexGraspNet code | multi-finger grasp modeling | useful when parallel-jaw assumptions stop being enough |
| [DexGraspNet 2.0](https://pku-epic.github.io/DexGraspNet2.0/) | expanded cluttered benchmark | dexterous hands | cluttered dexterous grasp data | public project release | DexGraspNet 2.0 code | harder dexterous grasp studies | good frontier signal for dexterous manipulation |
| [TransCG](https://graspnet.net/transcg) | task-focused robustness set | grasping with difficult sensing | transparent-object grasping | public project release | GraspNet-adjacent | difficult sensing regimes | useful for robustness, not just easy picks |

## Affordance and articulated interaction

| Dataset | Scale | Embodiment coverage | Modalities | License / access | Code ecosystem | Best for | Notes |
|---|---|---|---|---|---|---|---|
| [PartNet-Mobility](https://sapien.ucsd.edu/browse) | large articulated object collection | object-centric interaction | articulated geometry and part structure | project-hosted access | SAPIEN ecosystem | hinges, handles, drawers, part-aware interaction | essential for affordance and articulated manipulation |
| [GAPartNet](https://pku-epic.github.io/GAPartNet/) | benchmark-scale part data | part-aware manipulation settings | part segmentation and structure | public project release | GAPartNet | part-centric reasoning and execution | bridge between perception and interaction |
| [PartManip](https://pku-epic.github.io/PartManip/) | benchmark-scale | articulated-object interaction | part-aware manipulation data | public project release | PartManip | articulation-aware policies | useful if you want evaluation tied to manipulation |
| [AffordanceNet](https://github.com/wliu88/affordance_net) | classical benchmark | RGB object interaction | RGB affordance labels | open code and benchmark assets | AffordanceNet code | dense affordance prediction | classical baseline rather than a modern full stack |

## Humanoid and cross-embodiment signal

| Dataset | Scale | Embodiment coverage | Modalities | License / access | Code ecosystem | Best for | Notes |
|---|---|---|---|---|---|---|---|
| [RoboMIND](https://x-humanoid-robomind.github.io/) | multi-embodiment corpus | humanoids and multiple robot forms | multimodal robot demonstrations | public project release | RoboMIND project | humanoid and cross-embodiment signal | good for watching China-side humanoid data curation |
| [Open X-Embodiment](https://robotics-transformer-x.github.io/) | very large open mixture | cross-lab, cross-robot | RGB, proprioception, action trajectories | open project ecosystem | RT-X ecosystem | embodiment transfer context | still the most important open generalist anchor |

## Multimodal teleoperation and practical collection

| Dataset | Scale | Embodiment coverage | Modalities | License / access | Code ecosystem | Best for | Notes |
|---|---|---|---|---|---|---|---|
| [LeRobot datasets](https://huggingface.co/docs/lerobot/index) | practical hosted collections | low-cost and practical arms | RGB, proprioception, teleop logs | hosted open access | LeRobot | builders who need a short path from data to training | strongest practical curation path for small teams |
| [Mobile ALOHA data ecosystem](https://src.stanford.edu/demo/moble-aloha) | system-specific but highly influential | mobile manipulation setups | teleop trajectories, multi-camera data | project-specific access | ACT / ALOHA ecosystem | teleoperation-centric manipulation learning | important because many low-cost real-robot stacks trace back here |

## Practical notes

- If you are new, choose the dataset that already matches your framework and benchmark.
- If you want generality, use Open X-Embodiment as context, but do not start there unless you already have infrastructure.
- If you want a fast practical path, LeRobot and BridgeData V2 are usually better entry points than the largest corpora.
- Cross-reference this page with [Benchmarks](benchmarks.md), [Frameworks](frameworks.md), and [Build Paths](../build_paths/).
