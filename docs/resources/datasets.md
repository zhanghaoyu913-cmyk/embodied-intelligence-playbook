# Datasets

This page collects practical datasets that appear repeatedly in embodied-AI workflows.

## General robot data

| Dataset | What it is useful for | Links |
|---|---|---|
| Open X-Embodiment | large cross-lab, cross-robot dataset for generalist policy training | [project](https://robotics-transformer-x.github.io/) · [code](https://github.com/google-deepmind/open_x_embodiment) |
| BridgeData V2 | scalable robot-learning dataset with strong manipulation coverage | [project](https://rail-berkeley.github.io/bridgedata/) · [code](https://github.com/rail-berkeley/bridge_data_v2) |
| RoboMIND | recent multi-embodiment teleoperation dataset from China’s humanoid ecosystem | [project](https://x-humanoid-robomind.github.io/) |
| LeRobot datasets | practical dataset format + hosted open robotics data | [docs](https://huggingface.co/docs/lerobot/index) |

## Manipulation and benchmarking

| Dataset / benchmark | Notes | Links |
|---|---|---|
| CALVIN | long-horizon instruction-conditioned manipulation benchmark | [code](https://github.com/mees/calvin) |
| LIBERO | benchmark suite for lifelong and compositional manipulation | [project](https://libero-project.github.io/main.html) |
| BEHAVIOR-1K | 1,000 human-centered household activities in realistic simulation | [project](https://behavior.stanford.edu/index.html) |
| robomimic datasets | standard demonstration datasets for manipulation learning | [project](https://robomimic.github.io/) |

## Grasping and affordance

| Dataset | Notes | Links |
|---|---|---|
| GraspNet | benchmark-scale grasp detection dataset | [project](https://graspnet.net/) |
| PartNet-Mobility | articulated-object data for manipulation and affordance work | [project](https://sapien.ucsd.edu/partnet-mobility) |
| GAPartNet | part segmentation / articulation-oriented dataset and benchmark | [project](https://pku-epic.github.io/GAPartNet/) |

## How to choose quickly

- **Want generalist policy training?** Start with Open X-Embodiment and BridgeData V2.
- **Want long-horizon manipulation?** Add CALVIN, LIBERO, and BEHAVIOR-1K.
- **Want grasping?** Start with GraspNet.
- **Want articulated affordance?** Use PartNet-Mobility, SAPIEN, and GAPartNet.
