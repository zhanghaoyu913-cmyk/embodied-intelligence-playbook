# Academia Map

This page is an ecosystem map, not a ranking. The goal is to answer three questions quickly:

1. Which institutions are strongest on which part of the embodied stack?
2. Which labs are worth following for reproducible systems, not only papers?
3. Which researchers should you track if you care about a specific line of work?

## How to read this page

| Signal | Meaning |
|---|---|
| `algorithm` | theory, model design, perception, RL, learning method |
| `system` | end-to-end embodied system, benchmark, integrated robot stack |
| `hardware` | embodiment, hand, humanoid, platform engineering |
| `platform` | dataset, simulator, tooling, public benchmark, infra |

## Institution map

### North America

| Institution | Type | Stack focus | Bias | What to watch | Representative work and links | Why track |
|---|---|---|---|---|---|---|
| Stanford | university | interaction, household systems, benchmark design | system | home manipulation and human-centered embodied AI | [Stanford Robotics Center](https://src.stanford.edu/), [Mobile ALOHA](https://src.stanford.edu/demo/moble-aloha), [TidyBot++](https://tidybot2.github.io/), [BEHAVIOR-1K](https://behavior.stanford.edu/index.html) | strong bridge from research prototype to reproducible system page |
| UC Berkeley | university | policy learning, robot data, RL, manipulation | algorithm + platform | open data and generalist robot policy ecosystems | [BAIR](https://bair.berkeley.edu/), [RAIL / BridgeData V2](https://rail-berkeley.github.io/bridgedata/), [Open X-Embodiment](https://robotics-transformer-x.github.io/), [Octo](https://octo-models.github.io/) | one of the strongest anchors for buildable robot learning |
| Carnegie Mellon | university | broad embodied systems, robot intelligence, autonomy | system | embodied AI breadth across planning, manipulation, and perception | [REAL at CMU](https://www.cmu.edu/real/), [Bot Intelligence Group](https://www.cs.cmu.edu/~jeanoh/big/) | useful when you want systems breadth rather than only one method family |
| MIT | university | robot learning, locomotion, control, manipulation | algorithm + system | control-rich embodied work and high-signal robotics labs | [MIT CSAIL Robotics](https://robotics.csail.mit.edu/), [Improbable AI Lab](https://improbableai.github.io/) | strong signal for robotics methods that remain grounded in real systems |
| Columbia | university | manipulation, diffusion policy, robot learning | algorithm | high-impact visuomotor manipulation methods | [Columbia Robot Learning Lab](https://robotlearning.cs.columbia.edu/), [Diffusion Policy](https://diffusion-policy.cs.columbia.edu/) | important for manipulation-policy design and evaluation |
| University of Washington | university | grasping, perception, manipulation | algorithm + system | embodied vision and practical robot interaction | [RAIL @ UW](https://rail.ece.uw.edu/), [Dieter Fox group](https://homes.cs.washington.edu/~fox/) | strong for grasping, perception, and system-facing embodied learning |

### China and Greater China

| Institution | Type | Stack focus | Bias | What to watch | Representative work and links | Why track |
|---|---|---|---|---|---|---|
| Tsinghua | university | embodied intelligence, multimodal systems, robotics platforms | system + platform | embodied platforms with strong industry interfaces | [AIR](https://air.tsinghua.edu.cn/en/), [AIR Robotics](https://air.tsinghua.edu.cn/en/) | key signal source for China-side embodied platform building |
| Peking University | university | embodied robotics, part interaction, startup transfer | algorithm + system | embodied robotics center plus startup-facing translation | [Center for Embodied Intelligence and Robotics](https://www.ai.pku.edu.cn/en/Faculty/Artificial_General_Intelligence_Centers/Center_for_Embodied_Intelligence_and_Robotics.htm), [GALBOT](https://www.galbot.com/) | good place to watch lab-to-company transfer |
| Shanghai Jiao Tong University | university | RL, control, embodied systems | algorithm + system | embodied intelligence tied to control and RL practice | [RL2 Lab](https://gaoyue.sjtu.edu.cn/research-embodied.html), [SJTU Robotics](https://robotics.sjtu.edu.cn/) | useful for readers tracking the control side of embodied AI |
| Zhejiang University | university | humanoids, embodied platforms, whole-body systems | hardware + system | humanoid platform development and integration | [Humanoid Innovation Institute](https://hic.zju.edu.cn/hicenglish/), [ZJU HIC](https://hic.zju.edu.cn/hicenglish/82825/list.htm) | important for whole-body and platform-level embodied work |
| Fudan | university | embodied AI institute and trusted embodied systems | system | institutionally organized embodied intelligence effort | [Trusted Embodied AI Institute](https://teai.fudan.edu.cn/) | one of the clearer dedicated embodied-AI institutes in China |
| Nanjing University | university | intelligence science and embodied directions | algorithm | emerging embodied-intelligence academic signal | [School of Intelligence Science and Technology](https://is.nju.edu.cn/is_en/) | worth tracking as the ecosystem broadens beyond the biggest robotics centers |
| USTC | university | robotics, robot scientist, embodied platforms | system + hardware | science-meets-robotics embodied direction | [USTC English news](https://en.ustc.edu.cn/info/1144/5145.htm) | good to watch when robotics crosses scientific automation and embodied platforms |

## Researcher watchlists

### VLA, foundation models, and spatial intelligence

| Name | Institution anchor | Main line | Representative hooks | Why track | Stable links |
|---|---|---|---|---|---|
| Shuran Song | Stanford | embodied systems, VLA, household robotics | BEHAVIOR, TidyBot, home embodied systems | strong system builder for household-scale embodied AI | [homepage](https://shurans.github.io/) |
| Chelsea Finn | Stanford | robot learning, adaptation, imitation, meta-learning | data-efficient robot learning, adaptation-oriented policy design | useful when tracking how generalization becomes actionable | [homepage](https://ai.stanford.edu/~cbfinn/) |
| Fei-Fei Li | Stanford | spatial intelligence, embodied AI leadership | spatial intelligence framing, ecosystem building | high-level direction setter for the field | [profile](https://profiles.stanford.edu/fei-fei-li) |
| Pulkit Agrawal | MIT | world models, self-supervised interaction, embodied learning | active perception and predictive embodied learning | important for state and prediction layers | [homepage](https://people.csail.mit.edu/pulkitag/) |
| Deepak Pathak | Carnegie Mellon | self-supervision, embodied intelligence, agent learning | predictive and self-supervised agent learning | strong signal for agent-centric learning loops | [homepage](https://pathak22.github.io/) |
| Yonatan Bisk | Carnegie Mellon | language-grounded embodied AI | language and embodied reasoning | useful for grounding language into action settings | [homepage](https://www.cs.cmu.edu/~ybisk/) |

### Robot learning, manipulation, and RL

| Name | Institution anchor | Main line | Representative hooks | Why track | Stable links |
|---|---|---|---|---|---|
| Sergey Levine | Berkeley | robot learning, RL, manipulation | BAIR, robot learning at scale | one of the central organizers of modern robot learning | [homepage](https://people.eecs.berkeley.edu/~svlevine/) |
| Pieter Abbeel | Berkeley | RL, control, robot learning, platforms | Open X-Embodiment, Octo, MuJoCo Playground ecosystem | strong signal for reproducible stacks and ambitious scaling | [homepage](https://people.eecs.berkeley.edu/~pabbeel/) |
| Ken Goldberg | Berkeley | grasping, cloud robotics, manipulation | grasp planning and robotic manipulation systems | historically important for manipulation and grasping lines | [homepage](https://goldberg.berkeley.edu/) |
| Dave Held | robot learning ecosystem | manipulation, perception, action models | manipulation learning and 3D perception links | useful for task-driven manipulation design | [scholar search](https://scholar.google.com/scholar?q=Dave+Held+robotics) |
| Oliver Kroemer | Carnegie Mellon | manipulation, robot learning, tactile interaction | manipulation under uncertainty | relevant when interaction and feedback matter | [homepage](https://www.cs.cmu.edu/~okroemer/) |
| Andrea Bajcsy | Berkeley ecosystem | human-centered robotics, adaptive interaction | interactive autonomy and embodied systems | strong for deployment-aware robot behavior | [scholar search](https://scholar.google.com/scholar?q=Andrea+Bajcsy+robotics) |
| Chris Atkeson | Carnegie Mellon | control, humanoids, manipulation | robotics systems and control | important for readers closer to robotics systems than pure ML | [homepage](https://www.cs.cmu.edu/~cga/) |
| Zackory Erickson | Carnegie Mellon ecosystem | assistive and practical robotics | robot interaction in constrained real settings | high-signal applied robotics perspective | [homepage](https://zackory.com/) |
| Jean Oh | Carnegie Mellon | embodied systems, multi-robot and practical autonomy | CMU Bot Intelligence Group | useful ecosystem node for systems and deployment | [homepage](https://www.cs.cmu.edu/~jeanoh/) |

### Grasping, perception, and embodied vision

| Name | Institution anchor | Main line | Representative hooks | Why track | Stable links |
|---|---|---|---|---|---|
| Jitendra Malik | Berkeley | vision, perception, embodied understanding | embodied vision and perception foundations | important bridge from visual understanding to action | [homepage](https://people.eecs.berkeley.edu/~malik/) |
| Dieter Fox | University of Washington | perception, manipulation, robot learning | grasping and embodied perception systems | highly relevant for perception-to-interaction pipelines | [homepage](https://homes.cs.washington.edu/~fox/) |
| Katerina Fragkiadaki | Carnegie Mellon | visual prediction, 3D and dynamics understanding | predictive perception for agents | useful for state representation and world-model thinking | [homepage](https://www.cs.cmu.edu/~katef/) |

### China and Chinese scholar watchlist

For several China-side scholars, public homepages are fragmented across lab pages, scholar pages, and institution pages. The stable links below therefore prefer scholar-search or public lab anchors when a single maintained homepage is not obvious.

| Name | Institution anchor | Main line | Representative hooks | Why track | Stable links |
|---|---|---|---|---|---|
| Jianlan Luo | China embodied AI ecosystem | embodied intelligence and robot learning | embodied systems and robot learning | high-signal scholar for embodied learning and systems | [scholar search](https://scholar.google.com/scholar?q=Jianlan+Luo+robotics) |
| Huazhe Xu | Tsinghua / embodied ML ecosystem | decision making, RL, embodied agents | robot learning and decision making | useful for the learning-loop and control layers | [homepage](https://sites.google.com/view/huazhexu) |
| Hao Su | UC San Diego / embodied vision ecosystem | 3D, embodied AI, simulation-rich systems | 3D and embodied simulation | strong for perception and simulation interfaces | [homepage](https://cseweb.ucsd.edu/~haosu/) |
| Cewu Lu | Shanghai Jiao Tong ecosystem | 3D scene understanding, embodied perception | 3D vision and embodied perception | relevant for perception-to-action pipelines | [lab](https://www.mvig.org/) |
| Ping Luo | multimodal and embodied model ecosystem | multimodal learning and embodied systems | multimodal representation and embodied modeling | useful for tracking model-side convergence | [scholar search](https://scholar.google.com/scholar?q=Ping+Luo+embodied+AI) |
| Hao Dong | PKU / embodied manipulation ecosystem | manipulation and embodied interaction | manipulation and part-aware interaction | strong for practical manipulation-facing research | [homepage](https://www.donghao.org/) |
| Guoyue Zhou | SJTU / embodied RL ecosystem | embodied control and platform building | embodied control and systems | relevant for system plus RL integration | [scholar search](https://scholar.google.com/scholar?q=Guoyue+Zhou+robotics) |
| Xinlei Chen | multimodal and visual intelligence ecosystem | representation learning and multimodal systems | multimodal representation learning | useful as frontier signal for perception layers | [homepage](https://xinleic.xyz/) |
| Wenbo Ding | embodied systems and autonomy ecosystem | embodied decision systems | autonomy and embodied system design | useful for system-facing embodied work | [scholar search](https://scholar.google.com/scholar?q=Wenbo+Ding+robotics) |
| Yaqin Zhang | China AI ecosystem leadership | AI systems and industry ecosystem | ecosystem building and AI strategy | track for macro direction and ecosystem building | [profile](https://baike.baidu.com/item/%E5%BC%A0%E4%BA%9A%E5%8B%A4/110231) |
| Hong Liu | Beijing Institute of Technology ecosystem | control, robotics systems | robotics systems and control | strong signal for physical systems and robotics practice | [scholar search](https://scholar.google.com/scholar?q=Hong+Liu+robotics) |
| Qining Wang | robotics and embodied platforms ecosystem | robot system design and embodied platforms | robotics systems and wearable robotics | good for deployment-aware robotics | [scholar search](https://scholar.google.com/scholar?q=Qining+Wang+robotics) |
| Tao Wang | robotics and embodied control ecosystem | control and embodied system integration | control-oriented embodied systems | useful for robotics systems lines | [scholar search](https://scholar.google.com/scholar?q=Tao+Wang+robotics+embodied) |
| Hao Zhao | Tsinghua / embodied perception ecosystem | 3D, manipulation, embodied interaction | 3D perception and robot interaction | strong for perception-to-action bridge | [homepage](https://haozhaosv.github.io/) |
| Yao Mu | China embodied systems ecosystem | embodied learning and platform work | embodied systems and platform work | useful for current China-side embodied movement | [scholar search](https://scholar.google.com/scholar?q=Yao+Mu+robotics) |
| Yanyong Zhang | embodied platforms ecosystem | embodied systems and infrastructure | embodied systems and infrastructure | useful for platform tracking | [scholar search](https://scholar.google.com/scholar?q=Yanyong+Zhang+robotics) |
| Zhenshan Bing | robotics systems ecosystem | embodied robot systems | embodied robot systems | relevant for system execution lines | [scholar search](https://scholar.google.com/scholar?q=Zhenshan+Bing+robotics) |
| Shangke Lv | robotics and embodied control ecosystem | embodied robotics | embodied robotics and control | useful for academic ecosystem mapping | [scholar search](https://scholar.google.com/scholar?q=Shangke+Lv+robotics) |
| Yugang Jiang | embodied systems ecosystem | robotics and control | robotics and control | good supplementary signal on system side | [scholar search](https://scholar.google.com/scholar?q=Yugang+Jiang+robotics) |
| Yan Wang | embodied ecosystem | robotics and embodied intelligence | embodied intelligence systems | useful watch node | [scholar search](https://scholar.google.com/scholar?q=Yan+Wang+robotics+embodied) |
| He Wang | embodied ML ecosystem | embodied perception and interaction | embodied perception and interaction | relevant for high-signal academic tracking | [scholar search](https://scholar.google.com/scholar?q=He+Wang+embodied+AI) |
| Qian Wang | embodied ecosystem | robotic learning systems | robotic learning systems | useful secondary watch node | [scholar search](https://scholar.google.com/scholar?q=Qian+Wang+robotics) |
| Yilun Chen | embodied model ecosystem | embodied multimodal learning | multimodal embodied learning | useful frontier signal | [scholar search](https://scholar.google.com/scholar?q=Yilun+Chen+embodied+AI) |
| Jiyang Gao | embodied ecosystem | embodied control and systems | embodied control and systems | useful secondary watch node | [scholar search](https://scholar.google.com/scholar?q=Jiyang+Gao+robotics) |
| Tianlan Shao | 3D and embodied perception ecosystem | 3D understanding and embodied scene reasoning | 3D understanding and scene reasoning | relevant for perception/state layers | [homepage](https://geometrylearning.com/TianlanShao/) |
| Zheyuan Jiang | embodied ecosystem | embodied agents and learning systems | embodied agents and learning systems | useful watch node | [scholar search](https://scholar.google.com/scholar?q=Zheyuan+Jiang+robotics) |

## How to use this page

- If you want reproducible manipulation systems, start with Stanford, Berkeley, Columbia, and UW.
- If you want control, RL, and robotics systems depth, track Berkeley, CMU, MIT, and SJTU.
- If you want China-side platform and humanoid signal, watch Tsinghua, PKU, ZJU, Fudan, and USTC.
- Cross-reference this page with [Industry Map](industry.md), [Benchmarks](../resources/benchmarks.md), and the build paths in [docs/build_paths](../build_paths/).
