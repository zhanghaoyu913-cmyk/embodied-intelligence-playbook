<div align="center">

<img src="assets/figures/hero_overview.svg" alt="Embodied Intelligence Playbook banner" width="100%"/>

# Embodied Intelligence Playbook

**A curated open-source playbook for embodied intelligence**  
**roadmaps, papers, practical checklists, visual maps, and reproducible resources**

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-V1%20Design%20Edition-4F7DF3)]()
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)]()

</div>

---

## What is this?

**Embodied Intelligence Playbook** is a structured research-and-practice atlas for embodied AI.

It is designed to be more than a paper index. The goal is to make the field **navigable**, **buildable**, and **memorable**:

- **navigable**, because major directions are organized as readable roadmaps rather than loose bookmarks
- **buildable**, because each topic is tied to concrete system questions, project paths, and implementation cues
- **memorable**, because the repository uses visual structure, topic-specific styling, and compact conceptual diagrams

---

## Why this repository feels different

Many repositories are broad collections. This one tries to become a **designed entry point**.

It is built around four ideas:

1. **Direction before detail**  
   First understand the shape of a topic, then dive into papers.

2. **Practice before accumulation**  
   A smaller, better-structured set of materials is more useful than a giant uncurated list.

3. **Visual memory matters**  
   Readers remember diagrams, pathways, and conceptual landmarks better than raw links.

4. **A repository should feel like a work**  
   A good first version should already feel intentional, coherent, and worth returning to.

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
| Vision-Language-Action | How do perception and language become executable action? | model archetypes, grounding problems, control bottlenecks, project paths |
| World Models | How should an embodied agent represent and predict a changing world? | latent-state thinking, dynamics views, planning bridges, failure modes |
| Manipulation | How do robots complete tasks under contact and uncertainty? | task structure, interaction loops, control challenges, build-first advice |
| Grasping | How does a robot choose and verify stable, task-appropriate interaction? | proposal–scoring–execution logic, geometry cues, practical metrics |
| Affordance Learning | What actions are possible on an object, where, and why? | functional semantics, interaction regions, task grounding, representation choices |

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
│   └── templates/
└── .github/
```

### Design notes
- `roadmap/` contains the conceptual and strategic pages
- `resources/` gathers operational material for building and reproducing
- `paper_lists/` is the future home for venue-based and topic-based reading collections
- `assets/figures/` stores original visuals created specifically for this repository

---

## Current V1 Focus

The first design edition centers on five thematic roadmaps:

- **Vision-Language-Action**
- **World Models**
- **Manipulation**
- **Grasping**
- **Affordance Learning**

This is deliberate. A sharp first version is better than a wide but shallow one.

---

## Suggested Reading Path

### Path A — new to embodied AI
1. Read [Overview](docs/roadmap/overview.md)
2. Pick one roadmap page
3. Use the page to identify key sub-problems
4. Start taking notes with the [Paper Note Template](docs/templates/paper_note_template.md)

### Path B — already building systems
1. Start from [Manipulation](docs/roadmap/manipulation.md) or [Grasping](docs/roadmap/grasping.md)
2. Cross-link with [Affordance Learning](docs/roadmap/affordance.md)
3. Bring in [World Models](docs/roadmap/world_model.md) when planning or prediction becomes the bottleneck

### Path C — interested in foundation-model style robotics
1. Start from [Vision-Language-Action](docs/roadmap/vla.md)
2. Pair it with [World Models](docs/roadmap/world_model.md)
3. Track how representation, instruction, and action interface with control and embodiment

---

## Principles for Future Growth

This repository will grow under these principles:

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
