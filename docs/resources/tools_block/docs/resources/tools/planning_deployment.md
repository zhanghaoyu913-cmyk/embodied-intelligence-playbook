# Planning and Deployment

> This file covers **how perception and learning outputs connect to robot software and motion execution**.

## Quick selector

| Problem | Best first choices |
|---|---|
| robot software backbone | ROS 2 |
| manipulation and motion planning | MoveIt 2 |
| more model-based robotics and optimization | Drake |
| kinematics / dynamics utilities | Pinocchio |

---

## 1. ROS 2

- **What it is**: the core software libraries and tools used to build robotic applications.
- **Best for**: node graphs, communication, sensors, controllers, distributed robot software, integration glue.
- **Why embodied AI people use it**: it is the most common bridge between perception/training code and real robotic systems.
- **Official links**
  - Docs root: https://docs.ros.org/
  - ROS 2 docs: https://docs.ros.org/en/humble/index.html

## 2. MoveIt 2

- **What it is**: the manipulation and motion-planning platform for ROS 2.
- **Best for**: motion planning, kinematics, collision-aware planning, servoing, pick-and-place.
- **Why use it**: if your embodied stack manipulates arms and grippers, this is one of the most standard planning layers.
- **Official links**
  - Docs: https://moveit.picknik.ai/

## 3. Drake

- **What it is**: a toolbox for analysis, simulation, planning, and control of underactuated robotic systems.
- **Best for**: model-based control, trajectory optimization, systems-level robotics research.
- **Useful links**
  - Homepage: https://drake.mit.edu/

## 4. Pinocchio

- **What it is**: a fast library for rigid-body dynamics and kinematics.
- **Best for**: kinematics, dynamics, model-based robotics backends.
- **Useful links**
  - Docs: https://stack-of-tasks.github.io/pinocchio/

---

## Practical guidance

### If you are building a real robot stack
Use:
- ROS 2 + MoveIt 2

### If you are exploring model-based planning or control
Use:
- Drake and/or Pinocchio

### If you only need to get an arm moving safely
Use:
- MoveIt 2 before writing everything from scratch

---

## Common failure modes

- trying to bypass middleware too early
- mixing coordinate frames carelessly
- not deciding what runs online vs offline
- underestimating the integration cost from perception output to planner input
