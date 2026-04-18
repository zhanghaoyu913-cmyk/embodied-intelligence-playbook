<p align="center">
  <img src="../../assets/figures/banner_vla.svg" alt="VLA banner" width="100%"/>
</p>

# Vision-Language-Action

> **A VLA system is a promise:** that seeing and understanding can become doing.

<p align="center">
  <img src="../../assets/figures/flow_vla.svg" alt="VLA system flow" width="92%"/>
</p>

---

## Topic Thesis

Vision-Language-Action (VLA) is not just multimodality.  
It is the attempt to make the chain

**instruction → grounding → action → recovery**

stay coherent when the robot is operating in the real world.

A VLA paper becomes practically valuable when it answers three questions together:

1. What does language actually change?
2. How is action represented?
3. What happens after the first mistake?

---

## Why this topic matters

VLA became the most visible face of embodied AI because it offers a compelling interface:

- the robot sees a scene
- a human gives a language instruction
- the robot acts

But the real significance is deeper. VLA systems sit at the point where:
- vision must become task-relevant rather than descriptive
- language must select goals, constraints, and disambiguation cues
- action must remain controllable under latency, contact, and embodiment mismatch
- policy learning must move from one robot to many

That is why VLA is both a model-design problem and a system-integration problem.

---

## Problem Decomposition

### 1. Instruction grounding
How does the model decide which parts of the scene matter for the current command?

### 2. Action representation
How are robot actions emitted?
- joint targets
- end-effector deltas
- chunked trajectories
- tokenized actions
- high-level skills + low-level controller

### 3. Closed-loop execution
How does the system recover when:
- an object is occluded
- a grasp slips
- the scene has changed
- the target is ambiguous

### 4. Cross-embodiment transfer
What stays fixed when moving from one robot to another?
- backbone
- language interface
- policy head
- controller
- calibration / retargeting layer

### 5. Data scaling
How much can generalization be bought with:
- more robot trajectories
- internet video
- human video
- simulation
- synthetic or world-model-generated data

---

## Core Technical Routes

### Route A — language-conditioned behavior cloning
The fastest way to build a working baseline.

**Best for**
- low-cost setups
- direct task imitation
- limited robot embodiments

**Typical examples**
- ACT-style learning on teleoperated demonstrations
- language-conditioned visuomotor transformers

---

### Route B — pretrained vision-language backbone + action head
A common route when semantic grounding is the bottleneck.

**Best for**
- open-vocabulary instructions
- compositional object descriptions
- transferring semantics from internet-scale models

**Key tradeoff**
Strong semantics do not automatically imply strong motor control.

---

### Route C — large-scale robot pretraining
This route tries to build a reusable robot prior across embodiments, labs, and tasks.

**Best for**
- cross-task generalization
- fine-tuning with few demonstrations
- benchmarking foundation-policy behavior

**Canonical stack**
Open X-Embodiment → Octo / OpenVLA → downstream fine-tuning.

---

### Route D — hierarchical VLA
Separate high-level reasoning from low-level control.

**Best for**
- long-horizon tasks
- systems where action precision and symbolic planning both matter
- cases where a single monolithic model is hard to debug

---

### Route E — on-device and whole-body VLA
A rapidly growing route in 2025–2026.

**Best for**
- low-latency deployment
- humanoids and mobile manipulators
- settings where cloud-only execution is too brittle or too slow

---

## Frontier Watchlist (2025–2026)

| Work | Why it matters | Links |
|---|---|---|
| Gemini Robotics (2025) | high-profile frontier VLA family from Google DeepMind | [official](https://deepmind.google/models/gemini-robotics/) |
| Gemini Robotics-ER 1.6 (2026) | embodied reasoning layer focused on spatial logic, planning, and success detection | [official](https://deepmind.google/models/gemini-robotics/gemini-robotics-er/) |
| Gemini Robotics On-Device (2026) | signals a serious move toward deployable, on-robot VLA execution | [overview](https://ai.google.dev/gemini-api/docs/robotics-overview) |
| Helix (2025) | Figure’s generalist humanoid VLA framing of perception, movement, and reasoning | [official](https://www.figure.ai/helix) |
| Helix 02 (2026) | full-body extension from upper-body control to room-scale autonomy | [official](https://www.figure.ai/news/helix-02) |
| GR00T N1 (2025) | NVIDIA’s open humanoid foundation-model line enters the public ecosystem | [paper](https://research.nvidia.com/publication/2025-03_nvidia-isaac-gr00t-n1-open-foundation-model-humanoid-robots) |
| GR00T N1.5 / N1.6 (2025) | stronger post-training and real-robot performance on humanoid manipulation | [N1.5](https://research.nvidia.com/labs/gear/gr00t-n1_5/) · [N1.6](https://research.nvidia.com/labs/gear/gr00t-n1_6/) |
| Seed GR-3 (2025) | ByteDance’s large-scale VLA with strong emphasis on real-world generalization | [official](https://seed.bytedance.com/GR3) · [report](https://seed.bytedance.com/public_papers/gr-3-technical-report) |
| RynnBrain (2026) | DAMO’s open embodied foundation-model ecosystem and benchmark entry | [github](https://github.com/alibaba-damo-academy/RynnBrain) |
| OneTwoVLA / UniVLA (ICLR 2026) | representative of the push toward unified reasoning-and-acting VLA models | [OneTwoVLA](https://openreview.net/forum?id=tWMfhoP3as) · [UniVLA](https://openreview.net/forum?id=PklMD8PwUy) |

---

## Classical Backbone

| Work | Why it remains important | Links |
|---|---|---|
| RT-1 | early large-scale transformer policy for robotics | [project](https://robotics-transformer1.github.io/) |
| RT-2 | explicit transfer from internet-scale semantics to robotic control | [project](https://robotics-transformer2.github.io/) |
| PaLM-E | major milestone for embodied multimodal reasoning | [project](https://palm-e.github.io/) |
| Open X-Embodiment | largest open real-robot dataset release and RT-X ecosystem anchor | [project](https://robotics-transformer-x.github.io/) |
| Octo | open generalist robot policy and an excellent reproduction reference | [project](https://octo-models.github.io/) · [code](https://github.com/octo-models/octo) |
| OpenVLA | open 7B VLA baseline with immediate practical relevance | [project](https://openvla.github.io/) · [code](https://github.com/openvla/openvla) |
| π0 | generalist policy framing from Physical Intelligence | [official](https://www.physicalintelligence.company/blog/pi0) |
| VIMA | an influential formulation for multimodal prompting and robot manipulation | [project](https://vimalabs.github.io/) |

---

## Open-source Projects, Datasets, and Toolchains

### Datasets and data ecosystems
- [Open X-Embodiment](https://robotics-transformer-x.github.io/)
- [BridgeData V2](https://rail-berkeley.github.io/bridgedata/)
- [CALVIN](https://github.com/mees/calvin)
- [LIBERO](https://libero-project.github.io/main.html)
- [BEHAVIOR-1K](https://behavior.stanford.edu/index.html)

### Open-source model / training stacks
- [Octo](https://github.com/octo-models/octo)
- [OpenVLA](https://github.com/openvla/openvla)
- [ACT / ALOHA](https://github.com/tonyzhaozh/act)
- [LeRobot](https://huggingface.co/docs/lerobot/index)
- [robomimic](https://robomimic.github.io/)

### Real-robot system references
- [Mobile ALOHA](https://src.stanford.edu/demo/moble-aloha)
- [TidyBot++](https://tidybot2.github.io/)
- [SO-101 / LeRobot hardware docs](https://huggingface.co/docs/lerobot/so101)

---

## A practical VLA reading ladder

### Level 1 — learn the open backbone
1. Open X-Embodiment  
2. Octo  
3. OpenVLA  
4. BridgeData V2  

**Goal**  
Understand data format, action representation, and fine-tuning assumptions.

---

### Level 2 — understand system design choices
1. RT-1  
2. RT-2  
3. PaLM-E  
4. π0  

**Goal**  
Compare where semantics enter, how action is represented, and how deployment differs.

---

### Level 3 — inspect the 2025–2026 frontier
1. Gemini Robotics / ER 1.6  
2. Helix / Helix 02  
3. GR00T N1.x  
4. Seed GR-3  
5. RynnBrain  

**Goal**  
Identify what changed:
- more embodiment coverage
- stronger whole-body control
- explicit reasoning layers
- better post-training and adaptation

---

## Build Paths

### Build Path A — open-source manipulation VLA
Open X-Embodiment → OpenVLA / Octo → BridgeData V2 or LeRobot → real-robot fine-tuning.

**Best for**
- lab projects
- benchmark work
- open-source friendly reproduction

---

### Build Path B — low-cost real-robot route
LeRobot / SO-101 / ALOHA-style setup → ACT baseline → language conditioning → limited VLA fine-tuning.

**Best for**
- first embodied project
- budget-constrained real hardware
- quick iteration

---

### Build Path C — frontier system analysis route
Gemini Robotics / Helix / GR00T / Seed GR-3 → compare:
- action interface
- embodiment transfer
- on-device vs cloud
- recovery behavior
- full-body vs manipulator-only control

**Best for**
- research surveying
- thesis design
- system-comparison writeups

---

## What to verify in any VLA paper

1. **What does language actually control?**  
   Goal selection, object grounding, trajectory refinement, safety constraints, or all of them?

2. **What is the action interface?**  
   Continuous actions, tokenized actions, chunks, skills, or planner calls?

3. **How is recovery handled?**  
   Replanning, reactive correction, self-verification, or no explicit mechanism?

4. **What changes when the embodiment changes?**  
   A model that works on one embodiment but needs a full retrain on another is less general than it looks.

5. **Is the gain semantic or motor?**  
   Some models improve instruction understanding but not actual physical reliability.

---

## Common Failure Modes

- language looks strong, but motor execution is brittle
- impressive demos hide narrow action interfaces
- cross-embodiment transfer is overstated
- evaluation focuses on nominal runs rather than recovery
- more semantics are added without a reliable controller underneath
- closed-loop latency is ignored

---

## Open Questions

- How much of VLA should be unified in one network, and how much should remain modular?
- Can on-device models become good enough for fast, safe closed-loop deployment?
- What is the right pretraining mix: robot trajectories, human video, simulation, or world-model-generated data?
- How should VLA systems represent memory over long-horizon tasks?
- Can a single model truly span language, perception, manipulation, and full-body mobility without collapsing into unreadable engineering complexity?

---

## Closing Thought

The strongest VLA systems are not the ones that merely **sound** intelligent.  
They are the ones that make language matter precisely where action becomes hard.
