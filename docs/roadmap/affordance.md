<p align="center">
  <img src="../../assets/figures/banner_affordance.svg" alt="Affordance banner" width="100%"/>
</p>

# Affordance Learning

> **Affordance is the meeting point of function and possibility.**

<p align="center">
  <img src="../../assets/figures/flow_affordance.svg" alt="Affordance flow" width="92%"/>
</p>

---

## Topic Mood

Affordance learning is compelling because it gives action a semantic foothold.  
Instead of asking only what an object looks like, it asks:

- what can be done with it?
- where can that action happen?
- what part of the object matters for this task?
- how does function depend on context?

This turns perception from passive recognition into **action-oriented understanding**.

---

## What is this topic?

Affordance learning studies the relationship between:

- objects or object parts
- possible actions
- task context
- interaction regions
- functional consequence

An affordance is not just a label.  
It is a bridge between **perception** and **use**.

For embodied systems, this bridge is extremely valuable because it helps answer questions like:

- where should I grasp?
- what part can be pulled?
- where should force be applied?
- which region supports pouring, opening, pressing, or lifting?

---

## Why it matters

Affordance reasoning matters because many interaction decisions are not purely geometric.  
They are **functional**.

Two regions may look similar, but only one is a handle.  
Two stable grasps may exist, but only one supports the next task.  
A single object may support multiple affordances depending on the goal.

This makes affordance learning one of the most natural ways to connect:

- visual semantics
- geometry
- task intent
- manipulation planning
- grasp reranking

---

## The Central Question

The central question is:

> **How can an embodied system infer actionable structure rather than only descriptive structure?**

That structure may be expressed at multiple levels:

| Level | Example |
|---|---|
| object-level | this item can be opened |
| part-level | this segment is the handle |
| region-level | this local area is graspable |
| task-conditioned | this area is good for lifting but poor for pouring |
| relational | this affordance depends on pose, context, or tool state |

---

## Typical Technical Routes

### Route A — dense affordance prediction
Predict affordance labels over pixels, points, or mesh regions.

**Strengths**
- explicit interaction localization
- strong interpretability
- useful for direct execution cues

**Weaknesses**
- annotation is expensive
- multiple affordances may overlap

### Route B — part-level functional understanding
Represent objects through functional parts.

**Strengths**
- aligns naturally with manipulation
- helps organize task semantics

**Weaknesses**
- part boundaries and functions are often ambiguous

### Route C — retrieval or transfer-based affordance reasoning
Transfer interaction priors from similar objects or stored experience.

**Strengths**
- useful under limited annotation
- can exploit shape or feature similarity

**Weaknesses**
- transfer may be semantically wrong even when geometry looks similar

### Route D — language-guided affordance grounding
Use textual description or task language to specify the desired affordance.

**Strengths**
- flexible task conditioning
- ties semantics directly to action goals

**Weaknesses**
- language ambiguity can migrate into the affordance prediction itself

---

## What Makes Affordance Learning Hard

### 1. The same object can mean different things
A mug can be grasped, lifted, contained, displayed, or washed.

### 2. Function is contextual
A region that is safe for one action may be poor for another.

### 3. Annotation is expensive and subtle
Dense functional labeling is harder than ordinary object recognition.

### 4. Geometry alone is not enough
The system may need task semantics, prior experience, or temporal context.

---

## A Practical Taxonomy

You can organize affordance work by the kind of output it produces.

| Output style | What it gives you |
|---|---|
| binary affordance label | whether an action is possible |
| dense region map | where the action should happen |
| score field | how suitable different regions are |
| task-conditioned map | how suitability changes with the goal |
| executable interaction prior | a cue that can directly guide grasping or manipulation |

The last category is especially valuable for embodied systems.

---

## How Affordance Connects to Other Topics

### Affordance + grasping
Affordance can rerank grasp candidates according to task intent.

### Affordance + manipulation
Affordance can localize handles, support surfaces, pressable regions, or pull directions.

### Affordance + world models
Affordance can help define what state changes matter when modeling interaction.

### Affordance + VLA
Language can specify the desired action semantics, while affordance grounds them spatially.

---

## Practical Failure Modes

### Semantic failure
The model predicts a region that looks plausible but is functionally wrong.

### Localization failure
The correct affordance is known in concept, but the region is misplaced.

### Task mismatch
The model predicts generic “graspability” when the task requires a very specific interaction.

### Transfer failure
Affordance is copied from a similar-looking object whose function differs in a crucial way.

---

## Build-First Project Ideas

### Beginner project
Train a point-wise affordance predictor for a small set of object categories and visualize dense affordance fields.

### Intermediate project
Use affordance scores to rerank grasp candidates and compare against geometry-only grasp selection.

### Advanced project
Build a task-conditioned affordance system that predicts different interaction regions depending on textual or symbolic goals.

---

## Reading Strategy

When reading affordance papers, ask:

1. What is the unit of prediction — object, part, point, or region?
2. Is the affordance task-conditioned?
3. How expensive is the annotation pipeline?
4. Does the output directly help execution?
5. How is ambiguity handled when multiple affordances overlap?

---

## Representative Work Clusters to Curate Later

- dense affordance perception
- point-cloud and mesh-based affordance learning
- task-conditioned affordance reasoning
- retrieval-based affordance transfer
- affordance-guided grasping and manipulation

---

## Closing Thought

Affordance learning becomes powerful when a model stops saying  
“this is an object,”  
and starts saying  
**“this is where action can begin.”**
