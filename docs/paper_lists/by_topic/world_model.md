# World Model Paper & Project List

## 2025–2026 frontier

- **[DreamZero / World Action Models are Zero-shot Policies](https://dreamzero0.github.io/)** — 2026 preprint; WAM built on a video diffusion backbone for zero-shot robotic policies and cross-embodiment transfer.
- **[Fast-WAM](https://yuantianyuan01.github.io/FastWAM/)** — 2026 preprint; asks whether WAMs need test-time future imagination or mainly benefit from video co-training during training.
- **[GigaWorld-Policy](https://arxiv.org/abs/2603.17240)** — 2026 preprint; action-centered WAM with optional future-video generation for faster action decoding.
- **[Enhancing Policy Learning with World-Action Model](https://arxiv.org/abs/2603.28955)** — 2026 preprint; action-regularized world model with inverse dynamics for CALVIN manipulation tasks.
- **[ParticleFormer](https://proceedings.mlr.press/v305/huang25c.html)** — CoRL 2025; 3D point-cloud world model for multi-object and multi-material manipulation.
- **[PIN-WM](https://www.roboticsproceedings.org/rss21/p153.pdf)** — RSS 2025; physics-informed world model for non-prehensile manipulation.
- **[World Model Implanting](https://proceedings.mlr.press/v267/yoo25a.html)** — ICML 2025; test-time adaptation of embodied agents through world-model insertion.
- **[Multi-Stage Manipulation with Demonstration-Augmented Reward, Policy, and World Model Learning](https://proceedings.mlr.press/v267/escoriza25a.html)** — ICML 2025; combined demos, reward learning, policy learning, and world models.
- **V-JEPA 2** — https://ai.meta.com/research/vjepa/
- **V-JEPA 2 paper** — https://ai.meta.com/research/publications/v-jepa-2-self-supervised-video-models-enable-understanding-prediction-and-planning/
- **World-Gymnast** — https://arxiv.org/abs/2602.02454
- **World-Gymnast project** — https://world-gymnast.github.io/
- **Robotic World Model** — https://github.com/leggedrobotics/robotic_world_model

## World-Action Model lens

WAM-style work should be tracked separately from generic world models because it asks a sharper system question: can the same model learn future visual dynamics and action sequences tightly enough to improve control?

Use this lens when comparing:

- whether future prediction is used only for representation learning or also at inference time
- whether action tokens influence video generation, video tokens influence action prediction, or the dependency is deliberately causal
- whether the benefit shows up in closed-loop control, cross-embodiment transfer, or only visual prediction quality

## Compact classic foundation

- **DreamerV3** — https://danijar.com/project/dreamerv3/
- **DreamerV3 code** — https://github.com/danijar/dreamerv3
- **TD-MPC2** — https://www.tdmpc2.com/
- **TD-MPC2 code** — https://github.com/nicklashansen/tdmpc2
