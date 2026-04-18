<div align="center">

<img src="assets/figures/hero_overview.svg" alt="Embodied Intelligence Playbook banner" width="100%"/>

# Embodied Intelligence Playbook

**A curated open-source playbook for embodied intelligence**  
**roadmaps, papers, practical checklists, visual maps, and reproducible resources**

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Curated-4F7DF3)]()
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)]()

</div>

---

## What is this?

**Embodied Intelligence Playbook** is a structured research-and-practice atlas for embodied AI.

It is designed to be more than a paper index. The goal is to make the field **navigable**, **buildable**, and **memorable**:

- **navigable**, because major directions are organized as readable roadmaps rather than loose bookmarks
- **buildable**, because each topic is tied to concrete system questions, project paths, implementation cues, and benchmark choices
- **memorable**, because the repository uses visual structure, topic-specific styling, and compact conceptual diagrams

---

## Visual Field

<p align="center">
  <img src="assets/figures/embodied_wordcloud.svg" alt="Embodied intelligence word cloud" width="92%"/>
</p>

<p align="center">
  <img src="assets/figures/topic_constellation.svg" alt="Embodied AI topic constellation" width="92%"/>
</p>

---

## Quick Start

### Start from the big picture
- [Overview](docs/roadmap/overview.md)

### Choose a core direction
- [Vision-Language-Action](docs/roadmap/vla.md)
- [World Models](docs/roadmap/world_model.md)
- [Manipulation](docs/roadmap/manipulation.md)
- [Grasping](docs/roadmap/grasping.md)
- [Affordance Learning](docs/roadmap/affordance.md)

### Explore practical resources
- [Datasets](docs/resources/datasets.md)
- [Simulators](docs/resources/simulators.md)
- [Frameworks](docs/resources/frameworks.md)

### Keep notes in a consistent format
- [Paper Note Template](docs/templates/paper_note_template.md)

---

## Topic Gallery

| Topic | Core Question | What you will find |
|---|---|---|
| Vision-Language-Action | How do perception and language become executable action? | model archetypes, grounding problems, control bottlenecks, practical VLA stacks |
| World Models | How should an embodied agent represent and predict a changing world? | latent-dynamics control, 3D world models, planning bridges, failure modes |
| Manipulation | How do robots complete tasks under contact and uncertainty? | benchmark map, policy families, teleoperation stacks, long-horizon build paths |
| Grasping | How does a robot choose and verify stable, task-appropriate interaction? | proposal–scoring–execution logic, point-cloud pipelines, datasets, evaluation |
| Affordance Learning | What actions are possible on an object, where, and why? | functional semantics, interaction regions, articulated objects, grounding methods |

---

## Paper Directory

### By topic
- [VLA](docs/paper_lists/by_topic/vla.md)
- [World Models](docs/paper_lists/by_topic/world_model.md)
- [Manipulation](docs/paper_lists/by_topic/manipulation.md)
- [Grasping](docs/paper_lists/by_topic/grasping.md)
- [Affordance](docs/paper_lists/by_topic/affordance.md)

### By conference
- [ICRA](docs/paper_lists/by_conference/icra.md)
- [RSS](docs/paper_lists/by_conference/rss.md)
- [CoRL](docs/paper_lists/by_conference/corl.md)
- [CVPR](docs/paper_lists/by_conference/cvpr.md)
- [ICCV](docs/paper_lists/by_conference/iccv.md)
- [ICLR](docs/paper_lists/by_conference/iclr.md)
- [ICML](docs/paper_lists/by_conference/icml.md)

### By journal
- [RA-L](docs/paper_lists/by_journal/ral.md)
- [T-RO](docs/paper_lists/by_journal/tro.md)

---

## Resource Directory

- [Datasets](docs/resources/datasets.md)
- [Simulators](docs/resources/simulators.md)
- [Frameworks](docs/resources/frameworks.md)

---

## Suggested Reading Paths

### Path A — new to embodied AI
1. Read [Overview](docs/roadmap/overview.md)
2. Pick one roadmap page
3. Use the roadmap to identify the key sub-problems, benchmarks, and starter projects
4. Track your notes with the [Paper Note Template](docs/templates/paper_note_template.md)

### Path B — already building systems
1. Start from [Manipulation](docs/roadmap/manipulation.md) or [Grasping](docs/roadmap/grasping.md)
2. Cross-link with [Affordance Learning](docs/roadmap/affordance.md)
3. Bring in [World Models](docs/roadmap/world_model.md) when planning, prediction, or data efficiency becomes the bottleneck

### Path C — foundation-model style robotics
1. Start from [Vision-Language-Action](docs/roadmap/vla.md)
2. Pair it with [World Models](docs/roadmap/world_model.md)
3. Use [Datasets](docs/resources/datasets.md) and [Frameworks](docs/resources/frameworks.md) to choose a practical stack

---

## Repository Design

```text
embodied-intelligence-playbook/
├── README.md
├── assets/
│   └── figures/
├── docs/
│   ├── roadmap/
│   ├── resources/
│   ├── paper_lists/
│   │   ├── by_conference/
│   │   ├── by_journal/
│   │   └── by_topic/
│   └── templates/
└── .github/
```

### Design notes
- `roadmap/` contains the conceptual and strategic pages
- `resources/` gathers operational material for building and reproducing
- `paper_lists/` organizes reading by topic, venue, and journal
- `assets/figures/` stores original visuals created specifically for this repository

---

## Principles for Growth

This repository grows under five principles:

- **clarity over clutter**
- **cohesion over noise**
- **practice over trend-chasing**
- **curation over exhaustiveness**
- **structure before scale**

---

## Contributing

This project welcomes high-quality contributions:

- roadmap improvements
- paper summaries
- visual topic maps
- reproduction notes
- resource curation
- issue-driven improvements to structure

Please see [CONTRIBUTING.md](CONTRIBUTING.md).

---

## License

This project is released under the [MIT License](LICENSE).
