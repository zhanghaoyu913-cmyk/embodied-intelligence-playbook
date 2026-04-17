<p align="center">
  <img src="../../assets/figures/banner_grasping.svg" alt="Grasping banner" width="100%"/>
</p>

# Grasping

> **Grasping is the art of establishing meaningful contact.**

<p align="center">
  <img src="../../assets/figures/flow_grasping.svg" alt="Grasping pipeline" width="92%"/>
</p>

---

## Topic Mood

Grasping is often introduced as a subroutine, but in practice it is one of the most consequential primitives in embodied manipulation.

A poor grasp does not just fail locally.  
It can:

- make downstream manipulation impossible
- damage a long-horizon plan
- force awkward recovery
- hide task misunderstanding behind apparent mechanical failure

That is why grasping sits at a fascinating junction of:
- geometry
- stability
- uncertainty
- embodiment
- task intent

---

## What is this topic?

Grasping studies how a robot should establish contact with an object so that interaction becomes stable, useful, and task-appropriate.

There are at least three distinct questions hidden inside that sentence:

1. **Where** should contact happen?
2. **How** should the hand or gripper be configured?
3. **Why this grasp**, given the downstream task?

This last question is especially important.  
A grasp that is mechanically stable may still be functionally poor.

---

## Why it matters

Grasping matters because it is a gateway action.  
If the initial interaction is wrong, many later behaviors become either impossible or unnecessarily fragile.

It also serves as a compact microcosm of embodied AI:

- perception must identify shape and free space
- representation must encode geometry and uncertainty
- decision must balance stability and task constraints
- control must execute contact without destabilization
- verification must detect whether the grasp truly succeeded

---

## A Five-Stage View

| Stage | Main concern |
|---|---|
| sense | what geometry and occlusion are visible? |
| propose | what candidate grasps are even feasible? |
| score | which grasp best matches stability and task intent? |
| execute | can the robot realize the contact precisely? |
| verify | did the actual interaction match the expected one? |

A grasp pipeline is only as strong as its weakest stage.  
Verification is especially under-emphasized in many systems.

---

## Main Technical Routes

### Route A — analytical grasp synthesis
Derive grasp quality from geometry and force closure style reasoning.

**Strengths**
- interpretable
- physically motivated
- useful when geometry is reliable

**Weaknesses**
- sensitive to modeling assumptions
- can struggle with clutter, partial observation, or novel object variation

### Route B — data-driven grasp detection
Predict grasp candidates from depth, point clouds, images, or multimodal inputs.

**Strengths**
- strong empirical performance
- scalable to many object classes
- adapts to real-world messiness better than strict analytical pipelines

**Weaknesses**
- may be less transparent
- grasp quality can depend strongly on dataset bias

### Route C — task-oriented grasping
Select grasps not only for stability, but for what comes after.

**Strengths**
- more aligned with manipulation
- supports tool use, reorientation, and structured tasks

**Weaknesses**
- requires modeling future task consequences
- harder to evaluate cleanly

### Route D — multimodal grasping
Use tactile signals, force feedback, vision, or language jointly.

**Strengths**
- better for uncertainty and verification
- improves closed-loop adaptation

**Weaknesses**
- system complexity rises quickly

---

## What Makes Grasping Deep

### 1. Partial observation
The robot rarely sees the full object clearly.

### 2. Stability is contextual
A “good grasp” changes depending on the downstream task.

### 3. Contact is noisy
Execution error, compliance, friction, and material properties all matter.

### 4. Verification is essential
A predicted grasp is not yet a successful grasp.

---

## Stability vs Usefulness

One of the most important distinctions in grasping is this:

| Type | Optimization target |
|---|---|
| stable grasp | hold the object reliably |
| task-oriented grasp | hold the object in a way that enables the next action |
| recoverable grasp | allow re-adjustment or safe recovery if the first attempt is imperfect |

A mature grasping system eventually needs all three.

---

## Practical Failure Modes

### Proposal failure
The system never considered the right grasp family.

### Scoring failure
The right grasp was proposed, but ranked too low.

### Execution failure
The chosen grasp was good in principle, but motion or contact realization was poor.

### Task mismatch
The grasp is stable, but blocks the actual manipulation objective.

### Verification failure
The system assumes success even though the object slipped or rotated undesirably.

---

## Build-First Project Ideas

### Beginner project
Implement grasp proposal plus scoring on point clouds and visualize how ranking changes under scene perturbation.

### Intermediate project
Compare geometry-only grasp ranking against a task-conditioned reranking module.

### Advanced project
Integrate tactile or post-contact verification into the loop and measure how many nominal failures are recoverable.

---

## Reading Strategy

When reading grasping papers, ask:

1. Is the paper optimizing stability, usefulness, or both?
2. What observation modality is assumed?
3. How are candidates generated?
4. Is execution realism evaluated?
5. Does the method connect to downstream task success?

That last question often changes how impressive a result actually is.

---

## Representative Work Clusters to Curate Later

- analytical grasping
- point-cloud-based grasp detection
- clutter-aware grasping
- task-oriented grasping
- tactile or multimodal grasp verification

---

## Closing Thought

Grasping is where geometry first becomes intention.  
It is not just about holding an object. It is about holding it **for something**.
