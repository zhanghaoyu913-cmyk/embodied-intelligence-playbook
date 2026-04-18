# Benchmarks

This page is the benchmark-first entry point for the atlas. Use it when the question is not "what paper should I read?" but "what evaluation world should I build against?"

## Quick selector

| If you want to study... | Start here | Why |
|---|---|---|
| long-horizon language-conditioned manipulation | [CALVIN](https://github.com/mees/calvin) | strong closed-loop manipulation benchmark with instruction grounding |
| lifelong and compositional robot learning | [LIBERO](https://libero-project.github.io/main.html) | good for transfer, sequential learning, and policy comparison |
| household-scale embodied tasks | [BEHAVIOR-1K](https://behavior.stanford.edu/index.html) | closest to human-centered activity breadth |
| clean tabletop control baselines | [Meta-World](https://meta-world.github.io/) | fast RL and imitation benchmarking |
| GPU-scale manipulation simulation | [ManiSkill](https://maniskill.ai/) | strong engineering path for manipulation research |
| cluttered-scene parallel-jaw and 6-DoF grasping | [GraspNet](https://graspnet.net/) | standard benchmark ecosystem for modern grasping |
| articulated-object and part interaction | [PartNet-Mobility](https://sapien.ucsd.edu/browse) | useful for affordance and mechanism manipulation |
| house-like mobile manipulation and task suites | [RoboCasa](https://robocasa.ai/) | strong bridge between simulation tasks and policy evaluation |

## Benchmark matrix

| Benchmark | Primary task family | Modality | Embodiment | Evaluation style | Code maturity | Best fit | When not to use |
|---|---|---|---|---|---|---|---|
| CALVIN | long-horizon manipulation | RGB, language, proprioception | tabletop arm | task success over sequences | high | VLA, imitation, long-horizon control | not ideal for whole-body or humanoid work |
| LIBERO | lifelong and compositional manipulation | RGB, language, state | tabletop arm | transfer across task suites | high | continual learning, generalist policy studies | less useful if you need realistic household physics breadth |
| BEHAVIOR-1K | household activities | rich scene semantics, interaction signals | household embodied agents | activity-level completion | medium | human-centered embodied task planning | heavy if you only need fast iteration on tabletop skills |
| Meta-World | multi-task manipulation | state and RGB variants | robotic arm | reward and success metrics | high | RL baselines, controlled ablations | too narrow for realistic household deployment claims |
| ManiSkill | manipulation and robot skill learning | RGB-D, state, point cloud | multiple manipulation embodiments | benchmark suites + simulator-native tasks | high | GPU-scale sim manipulation and reproducible training | not a substitute for real-robot integration |
| GraspNet | 6-DoF grasp detection | RGB-D, point cloud | parallel-jaw grasping | grasp accuracy and success | high | cluttered-scene grasping | not enough if downstream task success is the true objective |
| PartNet-Mobility | articulated object interaction | geometry, part structure | object-centric | part/action outcome evaluation | high | affordance, articulation, mechanism reasoning | not a full task benchmark by itself |
| RoboCasa | household mobile manipulation tasks | vision, language, state | household robot stacks | task completion in simulated homes | medium | simulation-first mobile manipulation | ecosystem still smaller than CALVIN or LIBERO for broad reproduction |

## Task-to-benchmark routing

| Task goal | Recommended primary benchmark | Good companions |
|---|---|---|
| open-source VLA baseline | CALVIN | LIBERO, BridgeData V2 |
| generalist manipulation transfer | LIBERO | CALVIN, Open X-Embodiment |
| part-aware interaction | PartNet-Mobility | GAPartNet, SAPIEN |
| grasp detection | GraspNet | DexGraspNet, TransCG |
| RL baseline comparison | Meta-World | ManiSkill, MuJoCo Playground |
| mobile manipulation and household tasks | RoboCasa | BEHAVIOR-1K, OmniGibson |

## Goal-to-stack quick selector

| Goal | Benchmark | Dataset | Simulator | Framework |
|---|---|---|---|---|
| open VLA reproduction | CALVIN | BridgeData V2 | ManiSkill or native benchmark stack | OpenVLA or Octo |
| BC-first manipulation baseline | LIBERO | robomimic data or LeRobot datasets | ManiSkill | robomimic or LeRobot |
| model-based control study | Meta-World | task-native rollouts | MuJoCo or MuJoCo Playground | DreamerV3 or TD-MPC2 |
| grasping pipeline | GraspNet | GraspNet | SAPIEN | Contact-GraspNet or VGN |
| articulation and affordance | PartNet-Mobility | GAPartNet or PartManip | SAPIEN | affordance or part-aware pipeline |

## Full task-to-stack matrix

| Task | Benchmark | Dataset | Simulator | Framework |
|---|---|---|---|---|
| open-source VLA baseline | CALVIN | BridgeData V2 | ManiSkill or benchmark-native stack | OpenVLA or Octo |
| compositional manipulation transfer | LIBERO | robomimic data or LeRobot datasets | ManiSkill | robomimic, Octo, or OpenVLA |
| household embodied tasks | BEHAVIOR-1K or RoboCasa | BEHAVIOR assets and task suites | OmniGibson / BEHAVIOR stack | system-specific policy stack |
| RL baseline comparison | Meta-World | task-native rollouts | MuJoCo or MuJoCo Playground | PPO, SAC, DreamerV3, or TD-MPC2 |
| grasp detection | GraspNet | GraspNet | SAPIEN | Contact-GraspNet, GPD, or VGN |
| articulated affordance | PartNet-Mobility | GAPartNet or PartManip | SAPIEN | affordance or part-aware policy stack |

## Research-question entry points

| Research question | Best entry points |
|---|---|
| does language help control or only semantics | CALVIN, OpenVLA, VLA roadmap |
| does predictive state improve action | Meta-World, DreamerV3, World Models roadmap |
| does RL help after imitation | GR-RL, LIBERO, RL roadmap |
| do affordances improve downstream action | PartManip, Affordance roadmap, Grasping + Affordance build path |
| what stack is most buildable for a newcomer | Real Robot build path, LeRobot, Benchmarks page |

## Practical rule

Pick the smallest benchmark that still measures the failure mode you care about. Most projects become unmanageably slow because they start from the largest environment rather than the most diagnostic one.
