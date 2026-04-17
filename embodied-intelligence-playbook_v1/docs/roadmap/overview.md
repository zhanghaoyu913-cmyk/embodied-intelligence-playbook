<p align="center">
  <img src="../../assets/figures/banner_overview.svg" alt="Overview banner" width="100%"/>
</p>

# Overview

> **Embodied intelligence is not a single capability.**  
> It is the coordination of perception, language, memory, action, control, and physical consequence.

---

## Field Character

Embodied AI becomes interesting the moment a system can no longer hide behind static prediction.  
The world pushes back. Objects move, friction matters, occlusion breaks certainty, instructions are ambiguous, and actions have irreversible consequences.

That is why embodied intelligence sits at the intersection of several traditions at once:

- computer vision
- machine learning
- robotics
- control
- planning
- human-computer interaction
- simulation and physical modeling

The field is not just about building agents that **see** or **speak**.  
It is about building agents that can **form internal structure about the world and use it while acting inside the world**.

---

## A Compact Mental Model

Embodied AI can be read through five recurring layers:

| Layer | Main question | Typical bottleneck |
|---|---|---|
| Perception | What is present in the scene? | ambiguity, partial observation, viewpoint shift |
| Representation | What internal structure should be remembered? | brittle abstractions, poor generalization |
| Decision | What should happen next? | weak planning, shallow reasoning |
| Control | How do desired actions become motion? | instability, precision, latency |
| Interaction outcome | What changed after the action? | contact uncertainty, cascading failures |

A strong embodied system does not only optimize one layer well.  
It **couples** these layers without allowing one of them to become the hidden failure source.

---

## Visual Map

<p align="center">
  <img src="../../assets/figures/topic_constellation.svg" alt="Embodied AI constellation" width="92%"/>
</p>

---

## The Five Curated Axes in This Repository

### 1. Vision-Language-Action
This axis asks how perception and language can be transformed into grounded behavior.  
It is where instruction following, multimodal reasoning, and action policies begin to converge.

### 2. World Models
This axis asks what kind of internal world representation lets an agent predict, imagine, plan, and transfer.  
It is where state abstraction, latent dynamics, and long-horizon structure come into focus.

### 3. Manipulation
This axis asks how robots actually complete tasks under physical interaction.  
It centers on task decomposition, contact, robustness, and task-conditioned motion.

### 4. Grasping
This axis asks how a robot establishes stable and task-suitable contact with objects.  
It is a deceptively small problem with deep geometric and functional consequences.

### 5. Affordance Learning
This axis asks what can be done to an object, where, and under what purpose.  
It is one of the most natural bridges between visual understanding and action semantics.

---

## Three Ways to Read the Field

### Lens A — the systems lens
Under this view, embodied AI is about **stack design**:

- sensors
- scene understanding
- representation
- decision logic
- control interface
- feedback loop

This lens is useful when you want to build a working system.

### Lens B — the representation lens
Under this view, embodied AI is about **what must be represented explicitly or implicitly**:

- object state
- agent state
- task state
- interaction possibilities
- uncertainty
- temporal evolution

This lens is useful when you want to understand why one model generalizes and another collapses.

### Lens C — the evaluation lens
Under this view, embodied AI is about **what success actually means**:

- one-step success
- long-horizon stability
- recovery ability
- transfer across scenes or embodiments
- efficiency of data, compute, and annotation

This lens matters because many systems look strong until the metric becomes realistic.

---

## Core Tensions That Keep Reappearing

| Tension | What it means |
|---|---|
| Rich models vs controllable systems | expressive models are useful, but often harder to stabilize in closed-loop control |
| Generality vs precision | a model that does many tasks may still fail at fine motor execution |
| Prediction vs intervention | generating future observations is not the same as knowing how to change them |
| Scale vs interpretability | larger systems often gain breadth while losing tractability |
| Simulation speed vs physical realism | fast iteration can conflict with contact fidelity and transfer value |

Understanding embodied AI means learning how different papers choose sides in these trade-offs.

---

## Typical Failure Modes Across the Field

A useful way to read embodied work is to ask **where failure enters first**.

### Perception-first failure
The system never formed a reliable understanding of the scene.

### Representation-first failure
The system saw the input, but stored the wrong internal abstraction.

### Decision-first failure
The system understood the state, but selected an action sequence that does not compose.

### Control-first failure
The plan is fine in theory, but motion execution is too brittle.

### Interaction-first failure
The robot touches the world, and the world immediately reveals the hidden assumptions.

---

## A Practical Reading Strategy

### Stage 1 — learn the map
Read topic roadmaps to understand vocabulary, task families, and design choices.

### Stage 2 — follow one buildable thread
Pick one of:
- VLA for multimodal policy design
- world models for prediction and planning
- manipulation for task execution
- grasping for interaction primitives
- affordance learning for perception-to-action semantics

### Stage 3 — connect neighboring topics
Good embodied research rarely stays inside one neat box.

Examples:
- grasping often benefits from affordance reasoning
- manipulation often needs robust grasping
- VLA models often need world-model style structure
- world models become much more meaningful when attached to action

### Stage 4 — let evaluation shape your understanding
Always ask how a method behaves:
- under partial observation
- under contact
- over longer horizons
- under embodiment change
- after the first failure

---

## Recommended Starting Points

| You are interested in… | Start here |
|---|---|
| multimodal instruction-following robots | [Vision-Language-Action](vla.md) |
| planning, prediction, and latent dynamics | [World Models](world_model.md) |
| building practical robot task systems | [Manipulation](manipulation.md) |
| stable contact and task-oriented interaction | [Grasping](grasping.md) |
| functional understanding of objects and regions | [Affordance Learning](affordance.md) |

---

## Open Questions Worth Caring About

- What should be represented explicitly in embodied systems, and what can remain implicit?
- How can learned world structure actually improve action, not just prediction aesthetics?
- What kind of abstraction transfers across robot embodiments?
- How should long-horizon success be measured when recovery matters as much as first-step accuracy?
- Can affordance, geometry, language, and dynamics be unified without becoming too vague to execute?

---

## Closing Thought

The field becomes easier to navigate when you stop asking,  
“Which topic is the most important?”  
and start asking,  
**“At what interface does intelligence become difficult here?”**

That is the spirit of this repository.
