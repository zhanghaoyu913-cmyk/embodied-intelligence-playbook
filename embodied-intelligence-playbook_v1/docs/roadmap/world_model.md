<p align="center">
  <img src="../../assets/figures/banner_world_model.svg" alt="World model banner" width="100%"/>
</p>

# World Models

> **A world model is not just a predictor.**  
> It is an attempt to decide what the world must look like internally so action can become more deliberate.

<p align="center">
  <img src="../../assets/figures/flow_world_model.svg" alt="World model flow" width="92%"/>
</p>

---

## Topic Mood

World models are attractive because they promise something deeply important:  
an agent may not need to act blindly if it can **simulate, abstract, imagine, and compare futures before committing**.

That promise is powerful, but also dangerous.  
A world model can be visually impressive while still being useless for control.  
This topic is therefore about more than future prediction. It is about the relationship between:

- representation
- dynamics
- uncertainty
- planning
- action consequence

---

## What is this topic?

A world model tries to build an internal description of how the environment evolves, especially under the agent's actions.

Depending on the paper, that internal description might emphasize:

- latent state
- object-centric structure
- geometry
- contact and physical transitions
- temporal abstraction
- multimodal context
- action-conditioned imagination

The central question is not “can I predict the next frame?”  
It is:

> **What structure must be modeled so that prediction becomes useful for decision-making?**

---

## Why it matters

A good world model can support:

- long-horizon planning
- data-efficient learning
- recovery after deviation
- transfer across tasks
- reasoning about hidden state
- compression of task-relevant environment structure

This matters especially in embodied settings where trial-and-error on real hardware is expensive, risky, or slow.

---

## Three Views of World Models

### View A — the compression view
A world model compresses the environment into a compact latent structure.

This view is useful when the bottleneck is representation quality.

### View B — the imagination view
A world model lets the agent roll forward hypothetical futures.

This view is useful when planning and counterfactual reasoning matter.

### View C — the control view
A world model is only as good as the action decisions it enables.

This view is the most demanding, because it asks whether the learned internal world actually helps execution.

---

## Typical Technical Routes

### Route A — latent dynamics models
Encode observations into latent states and learn how those states evolve with actions.

**Best for**
- compact prediction
- planning in latent space
- long-horizon abstraction

**Main risk**
- latent states may be predictive but not controllable or interpretable

### Route B — visual future prediction
Model future observations or scene states directly.

**Best for**
- intuitive visualization
- explicit temporal behavior
- perception-heavy tasks

**Main risk**
- beautiful predictions can still be strategically empty

### Route C — object-centric world models
Represent the world in terms of objects, relations, and interactions.

**Best for**
- compositional structure
- interaction reasoning
- better transfer under scene change

**Main risk**
- object extraction and persistent identity are hard

### Route D — geometry-aware or 3D world models
Build state around spatial structure rather than only image-level regularities.

**Best for**
- embodied planning
- view consistency
- physical scene understanding

**Main risk**
- representation complexity rises quickly

### Route E — language- or task-conditioned world models
Incorporate instruction or goal context into what is predicted and remembered.

**Best for**
- task-aware prediction
- selective modeling of relevant future consequences

**Main risk**
- task conditioning may bias the model in ways that remove useful uncertainty

---

## The Core Difficulty

A world model should not merely predict what is easy to predict.  
It should emphasize what matters for action:

- contact onset
- object state change
- recoverability
- hidden constraints
- branching outcomes under different actions

This is where many systems fall short.  
They often learn the smooth parts of the world better than the consequential parts.

---

## A Practical Evaluation Lens

When reading world model work, ask these questions:

| Question | Why it matters |
|---|---|
| What state is being modeled? | determines whether the abstraction fits the task |
| What action interface is assumed? | prediction without executable action can remain detached |
| What uncertainty is represented? | important when futures branch or observations are partial |
| How is planning done? | imagined futures need a decision rule |
| Does better prediction improve action? | the ultimate test |

---

## Common Failure Modes

### 1. Predictive but strategically weak
The model predicts average futures well, yet does not help choose between actions.

### 2. Visually plausible but physically wrong
Frame-level realism hides mistakes in contact, timing, or object state.

### 3. Long-horizon drift
The imagined future becomes incoherent as rollout depth increases.

### 4. The representation is not portable
The latent state works for one embodiment, one view, or one task family only.

### 5. Planning assumes more than the model knows
The planner treats the world model as certain when it is not.

---

## How World Models Meet Robotics

In embodied intelligence, world models become interesting when they are attached to:

- task planning
- action proposal ranking
- model-based reinforcement learning
- error recovery
- simulation acceleration
- state abstraction for multimodal agents

The field becomes richer when world models stop being isolated predictors and become part of an action loop.

---

## Build-First Project Ideas

### Beginner project
Learn an action-conditioned latent predictor for a simple simulated robot task and study where short-horizon and long-horizon predictions diverge.

### Intermediate project
Compare:
- image-space prediction
- latent-state prediction
- object-centric prediction

Evaluate not only prediction quality, but whether each model helps planning.

### Advanced project
Use world-model rollouts to rank candidate action sequences or grasp candidates, then measure whether the imagined futures align with real outcomes.

---

## Reading Strategy

Read papers by asking:

1. **What exactly is the internal world here?**
2. **What is predictable, and what is strategically consequential?**
3. **How does this representation connect to control?**
4. **Does the planner trust the model appropriately?**

That sequence will reveal much more than simply asking whether the model is “generative.”

---

## Representative Work Clusters to Curate Later

- model-based reinforcement learning
- latent planning models
- object-centric world models
- 3D or geometry-aware world models
- multimodal or language-conditioned world models
- world models for manipulation and task planning

---

## Closing Thought

A world model earns its name only when it captures **the right world for action**,  
not merely a world that is easy to reconstruct.
