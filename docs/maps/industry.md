# Industry Map

This page tracks the company-side ecosystem for embodied AI. The goal is not to list names. The goal is to show where each company is strongest in the stack and what kind of public signal it emits.

## Company map

| Company | Type | Strongest stack layers | Bias | Signal type | Representative links | What to watch next |
|---|---|---|---|---|---|---|
| Google DeepMind | research lab / platform company | policy, reasoning, deployment tooling | algorithm + platform | model release, SDK, data ecosystem | [Gemini Robotics](https://deepmind.google/models/gemini-robotics/), [Gemini Robotics On-Device](https://deepmind.google/models/gemini-robotics/gemini-robotics-on-device/), [MuJoCo Playground](https://playground.mujoco.org/), [Open X-Embodiment](https://github.com/google-deepmind/open_x_embodiment) | whether the Gemini robotics stack becomes more open and benchmark-connected |
| Meta | research lab / platform company | state, predictive modeling, multimodal perception | algorithm | world-model and video-model research | [V-JEPA](https://ai.meta.com/research/vjepa/), [V-JEPA 2 paper](https://ai.meta.com/research/publications/v-jepa-2-self-supervised-video-models-enable-understanding-prediction-and-planning/), [V-JEPA 2 code](https://github.com/facebookresearch/vjepa2) | whether predictive video models cross into more explicit robot-control loops |
| NVIDIA | platform company | policy, simulation, humanoid platforms, data generation | platform + hardware | model release, simulator, synthetic data stack | [Isaac GR00T](https://developer.nvidia.com/isaac/gr00t), [GR00T N1 announcement](https://nvidianews.nvidia.com/news/nvidia-isaac-gr00t-n1-open-humanoid-robot-foundation-model-simulation-frameworks), [Isaac Lab](https://isaac-sim.github.io/IsaacLab/), [FLARE](https://research.nvidia.com/labs/gear/flare/) | how GR00T, Newton, and synthetic-motion tooling converge into a default humanoid stack |
| ByteDance Seed | research lab / platform company | VLA, post-training, dexterous manipulation | algorithm + system | model release, tech report, benchmark signal | [Seed Robotics](https://seed.bytedance.com/direction/robotics), [Seed GR-3](https://seed.bytedance.com/en/GR3), [GR-RL](https://seed.bytedance.com/en/gr_rl), [GR-RL report](https://seed.bytedance.com/public_papers/gr-rl-going-dexterous-and-precise-for-long-horizon-robotic-manipulation) | whether their VLA-plus-RL line becomes more open-source and benchmark-standardized |
| Alibaba DAMO Academy | research lab | unified VLA and world model, embodied tooling | algorithm + platform | open-source repo, technical report | [Alibaba DAMO GitHub](https://github.com/alibaba-damo-academy), [RynnVLA-001](https://github.com/alibaba-damo-academy/RynnVLA-001), [RynnVLA-002](https://github.com/alibaba-damo-academy/RynnVLA-002) | whether DAMO's open embodied repos consolidate into a stable public stack |
| Figure | robotics company | whole-body humanoid control and deployment storytelling | hardware + system | robot platform and model release | [Helix](https://www.figure.ai/helix), [Helix 02](https://www.figure.ai/news/helix-02) | whether Figure continues releasing system details beyond headline demos |
| Physical Intelligence | robotics company | generalist robot foundation-policy direction | algorithm + system | model framing and open research notes | [Physical Intelligence](https://www.pi.website/), [π0](https://www.pi.website/blog/pi0), [openpi](https://github.com/Physical-Intelligence/openpi) | whether the company exposes more buildable interfaces or open benchmarks |
| OpenAI | research lab | RL history, dexterity, sim-to-real precedent | algorithm | historical milestone and conceptual influence | [Learning Dexterity](https://openai.com/index/learning-dexterity/), [Solving Rubik's Cube](https://openai.com/index/solving-rubiks-cube/) | still important mostly as historical context unless robotics releases resume |
| Huawei | platform company | embodied systems strategy and infrastructure angle | platform | ecosystem and industry strategy signal | [Robots Empowered by AI Foundation Models and the Opportunities for 6G](https://www.huawei.com/en/huaweitech/future-technologies/robots-empowered-ai-foundation-models-6g) | how communications, cloud, and robotics infrastructure converge |
| Meituan | deployment company | real-world delivery and logistics robotics | deployment + system | deployed robotics platform | [Meituan Technology](https://tech.meituan.com/), [Autonomous Delivery Platform](https://developer.nvidia.com/downloads/embedded/success-stories/showcases/meituan) | useful if you care about deployment rather than benchmark-only success |
| GALBOT | startup | startup transfer from academia into embodied systems | system | startup signal | [GALBOT](https://www.galbot.com/), [About](https://www.galbot.com/about) | watch for how China-side academic startups productize embodied stacks |
| Unitree Robotics | robotics company / platform company | embodiment, locomotion, humanoid hardware, open tooling | hardware + platform | robot platform, open-source tooling, developer ecosystem | [Unitree](https://www.unitree.com/), [G1](https://www.unitree.com/g1), [Official Open Source](https://www.unitree.com/mobile/opensource), [G1-D End-to-End Platform](https://www.unitree.com/mobile/G1-D) | whether Unitree turns its low-cost humanoid + imitation/RL/data stack into the default open developer path |
| AGIBOT (智元机器人) | robotics company / platform company | embodiment, data ecosystem, humanoid deployment, VLA/ViLLA stack | platform + hardware | robot product line, dataset, research stack | [AGIBOT](https://www.agibot.com/), [Research](https://www.agibot.com/research), [AgiBot World & GO-1](https://agibot-world.com/blog/go1), [Challenge 2026](https://agibot-world.com/challenge2026) | whether AGIBOT can turn robot shipments + open data + foundation models into a stable public embodied stack |
| TARS / 它石智航 | robotics company / embodied AI startup | industrial manipulation, tactile-rich interaction, human-centric data, deployment | system + industrial deployment | dataset release, technical report, industrial application signal | [WiYH dataset](https://wiyh.tars-ai.com/), [WiYH paper](https://arxiv.org/abs/2512.24310), [TARS Jobs](https://tarsrobot.jobs.feishu.cn/), [industrial record report](https://pandaily.com/tars-s-a1-robot-earns-a-guinness-world-records-title-through-real-industrial-work) | whether TARS can make its industrial precision-manipulation line and embodied model stack more publicly reproducible |

## Signal reading guide

| Signal type | What it tells you |
|---|---|
| `model release` | frontier capability and direction of travel |
| `benchmark release` | whether a company is trying to shape evaluation norms |
| `robot platform` | hardware embodiment and deployment seriousness |
| `open-source stack` | whether you can realistically learn from or reproduce the work |
| `deployment system` | whether the company solves real operational constraints |

## Best company pages by question

| Question | Best companies to watch |
|---|---|
| where VLA is going | Google DeepMind, ByteDance Seed, NVIDIA, Physical Intelligence, Alibaba DAMO |
| where humanoid stacks are going | NVIDIA, Figure, Google DeepMind, Unitree, AGIBOT |
| where RL post-training is becoming practical | ByteDance Seed, NVIDIA, DeepMind-adjacent open stacks |
| where deployment constraints actually matter | Meituan, Huawei, Figure, TARS, AGIBOT |
| where open tooling is strongest | NVIDIA, Google DeepMind ecosystem, Alibaba DAMO, Unitree, Hugging Face LeRobot ecosystem |
| where China’s embodied deployment race is going | Unitree, AGIBOT, ByteDance Seed, TARS, Huawei, Meituan |
| where low-cost or more buildable humanoid developer paths are emerging | Unitree, AGIBOT, NVIDIA ecosystem |

## China-side embodied AI signal

The China-side ecosystem is especially worth watching when you care about:

- humanoid embodiment at scale
- industrial manipulation rather than demo-only success
- data collection pipelines tied to real factories and operations
- fast iteration between robot body, data engine, and embodied model

## How to use this page

- Use it with [Academia Map](academia.md) when deciding who to follow for a topic.
- Use it with [Frameworks](../resources/frameworks.md) and [Simulators](../resources/simulators.md) when deciding what is buildable now.
- Use it with each roadmap's `Academic Labs & Company Systems` section when you want topic-specific company signal rather than general ecosystem signal.
