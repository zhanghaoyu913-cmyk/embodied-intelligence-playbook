<p align="center">
  <img src="../../assets/figures/banner_vla.svg" alt="VLA banner" width="100%"/>
</p>

# Vision-Language-Action

> **A VLA system is a promise:** that seeing and understanding can become doing.

<p align="center">
  <img src="../../assets/figures/flow_vla.svg" alt="VLA system flow" width="92%"/>
</p>

---

## Topic Mood

Vision-Language-Action is one of the most visible faces of embodied AI because it speaks in a language many people intuitively understand:

- the robot sees a scene
- the user gives an instruction
- the robot performs an action

But the hard part is never only multimodality. The hard part is making the chain from **instruction → grounding → action** remain coherent under uncertainty, latency, contact, and embodiment mismatch.

---

## What is this topic really about?

At its core, VLA asks:

- How should language change what the robot attends to?
- How should perception become task-relevant rather than merely descriptive?
- How should action be represented so that it is both expressive and controllable?
- How much reasoning should happen inside the model, and how much should remain external?

---

## Core technical routes

### Route A — language-conditioned behavior cloning
Fastest way to get a working baseline.

### Route B — pretrained vision-language backbone + action head
Useful when semantics are the bottleneck.

### Route C — hierarchical VLA
Separate high-level reasoning from low-level control.

### Route D — large-scale robot pretraining
Best when you care about reuse across tasks and embodiments.

---

## 2025–2026 frontier watchlist

| Work | Why it matters | Links |
|---|---|---|
| Gemini Robotics (2025) | Google DeepMind’s frontier multimodal robotics model family | [official](https://deepmind.google/models/gemini-robotics/) |
| Gemini Robotics-ER 1.6 (2026) | explicit embodied reasoning layer for planning and success detection | [official](https://deepmind.google/models/gemini-robotics/gemini-robotics-er/) |
| Gemini Robotics On-Device (2026) | on-device fine-tunable VLA entry point | [official](https://deepmind.google/models/gemini-robotics/gemini-robotics-on-device/) |
| Helix (2025) | Figure’s generalist humanoid VLA system | [official](https://www.figure.ai/helix) · [news](https://www.figure.ai/news/helix) |
| Helix 02 (2026) | full-body autonomy extension for humanoid control | [official](https://www.figure.ai/news/helix-02) |
| GR00T N1 / N1.5 / N1.6 (2025) | NVIDIA’s open humanoid foundation-model line | [GR00T](https://developer.nvidia.com/isaac/gr00t) · [N1 paper](https://arxiv.org/abs/2503.14734) · [N1.5](https://research.nvidia.com/labs/gear/gr00t-n1_5/) · [N1.6](https://research.nvidia.com/labs/gear/gr00t-n1_6/) |
| RynnBrain (2026) | Alibaba DAMO’s embodied foundation model + planning/navigation variants | [github](https://github.com/alibaba-damo-academy/RynnBrain) |
| Seed GR-3 (2025) | ByteDance Seed’s large-scale VLA model | [official](https://seed.bytedance.com/GR3) |
| OneTwoVLA / UniVLA (ICLR 2026) | recent reasoning-and-acting unification | [openreview](https://openreview.net/forum?id=tWMfhoP3as) |

---

## Compact classic foundation

| Work | Why it matters | Links |
|---|---|---|
| RT-1 | early large-scale transformer policy for robotics | [project](https://robotics-transformer1.github.io/) |
| RT-2 | vision-language-action transfer from internet-scale semantics | [project](https://robotics-transformer2.github.io/) |
| PaLM-E | major multimodal foundation-model milestone for embodied reasoning | [project](https://palm-e.github.io/) |
| OpenVLA | open-source 7B VLA baseline with real adoption | [project](https://openvla.github.io/) · [code](https://github.com/openvla/openvla) |
| Open X-Embodiment | standardized large-scale robot dataset + RT-X ecosystem | [project](https://robotics-transformer-x.github.io/) · [code](https://github.com/google-deepmind/open_x_embodiment) |
| Octo | open-source generalist robot policy | [project](https://octo-models.github.io/) · [code](https://github.com/octo-models/octo) |
| π0 | strong foundation-policy milestone from Physical Intelligence | [official](https://www.physicalintelligence.company/blog/pi0) |

---

## Supporting datasets and stacks

- [BridgeData V2](https://rail-berkeley.github.io/bridgedata/)
- [Mobile ALOHA](https://src.stanford.edu/demo/moble-aloha)
- [ACT / ALOHA code](https://github.com/tonyzhaozh/act)
- [CALVIN](https://github.com/mees/calvin)
- [LIBERO](https://libero-project.github.io/main.html)
- [LeRobot](https://huggingface.co/docs/lerobot/index)

---

## What to verify in any VLA paper

1. What does language actually control?
2. What is the action interface?
3. How is closed-loop recovery handled?
4. What changes when the robot embodiment changes?
5. Is the gain semantic, motor, or both?

---

## Practical entry sequence

### Want the open-source route?
Open X-Embodiment → Octo / OpenVLA → BridgeData V2 / LeRobot → task-specific fine-tuning.

### Want the frontier industry route?
Gemini Robotics / Helix / GR00T / RynnBrain / Seed GR-3.

### Want a research project topic?
Compare VLA systems along three axes:
- action representation
- embodiment transfer
- recovery after off-nominal execution

---

## Closing Thought

The strongest VLA systems are not just those that **sound** intelligent. They are the ones that make language matter precisely where action becomes hard.
