# Repository Upgrade Checklist

## Status

The repository-level upgrade described in this checklist has been executed in the current curation pass.

What is now in place:

- six roadmap pages upgraded into guide-style atlas pages
- `docs/maps/` added as the canonical ecosystem-map layer
- `docs/resources/benchmarks.md` added
- `docs/build_paths/` added with five execution routes
- `README.md`, `CONTRIBUTING.md`, and `docs/templates/` updated to enforce atlas logic
- compatibility entry points kept for `docs/resources/academia_map.md` and `docs/resources/industry_map.md`

The checklist below is retained as the planning record for the upgrade and as a future maintenance reference.

## Positioning

This repository should become:

- a structured, judgment-heavy, build-oriented atlas for embodied intelligence
- organized by system stack, not only by resource type
- selective by reproducibility and practical value, not flat paper accumulation
- visually strong, but with visuals serving navigation and memory

It should not drift into:

- another broad Chinese link dump
- a conference/year-first paper warehouse
- a page set that looks polished but lacks execution paths

## Current State Assessment

The repository already has a solid phase-one base:

- six topic roadmaps exist and already contain `Topic Thesis`, `Core Technical Routes`, `Frontier Watchlist`, `Classical Backbone`, `Build Paths`, `Common Failure Modes`, and `Open Questions`
- `academia_map.md` and `industry_map.md` already exist, but they are still entry pages rather than full ecosystem maps
- datasets, simulators, frameworks, and venues pages already exist, but cross-navigation is still weak
- the visual system is already present, but information navigation is not yet strong enough

The main gap is not taste. The main gap is information architecture.

## Upgrade Principle

Do not rewrite the repository into a new taxonomy. Strengthen the existing six-topic spine and add the missing information layers around it.

## Phase 0: Foundation Fixes

### P0.1 Structure alignment

- [x] Add `docs/resources/benchmarks.md`
- [x] Add `docs/build_paths/`
- [x] Decide whether to keep `docs/resources/academia_map.md` and `docs/resources/industry_map.md` as canonical pages or migrate toward `docs/maps/academia.md` and `docs/maps/industry.md`
- [x] If migrating paths, keep compatibility links or redirect notes in old pages
- [x] Update `README.md` to reflect the final structure after the move

### P0.2 Navigation baseline

- [x] Add a short in-page navigation block near the top of each roadmap page
- [x] Add consistent section anchors across all six topics
- [x] Add a shared label system for `classical`, `frontier-2025-2026`, `open-source`, `benchmark`, `simulator`, `industry-system`, `build-path`
- [x] Add a cross-link block at the end of each topic page pointing to adjacent topics and relevant resource pages

### P0.3 Repository hygiene

- [x] Create `docs/templates/topic_page_template.md`
- [x] Create `docs/templates/institution_entry_template.md`
- [x] Create `docs/templates/build_path_template.md`
- [x] Add a lightweight curation rubric to `CONTRIBUTING.md` so future additions do not dilute the atlas

### Exit Criteria

- [x] No dead internal links in `README.md`
- [x] New pages have clear target paths before content expansion starts
- [x] Contributors can tell what a finished topic page should look like

## Phase 1: Upgrade The Six Core Topic Pages

Apply one shared template to all six existing roadmap pages without changing their titles.

### Target Template For Every Topic Page

- [x] `Topic Thesis`
- [x] `Why This Topic Matters`
- [x] `Problem Decomposition`
- [x] `Core Technical Routes`
- [x] `Classical Backbone`
- [x] `Frontier Watchlist (2025-2026)`
- [x] `Open-source Projects & Toolchains`
- [x] `Datasets / Benchmarks / Simulators`
- [x] `Academic Labs & Company Systems`
- [x] `Practical Build Paths`
- [x] `Common Failure Modes`
- [x] `Reading Sequence`
- [x] `Open Questions`

### Shared Content Standard For Every Topic

- [x] Expand `Classical Backbone` to at least 5-8 genuinely foundational papers or systems
- [x] Expand `Frontier Watchlist` to at least 8-15 2025-2026 entries with official project pages first, code second, papers third
- [x] Expand `Open-source Projects & Toolchains` to at least 5-10 items
- [x] Expand `Datasets / Benchmarks / Simulators` to at least 3-6 high-signal entries
- [x] Expand `Academic Labs & Company Systems` to at least 5-10 entries
- [x] Expand `Practical Build Paths` to at least 2-4 actionable tracks
- [x] Add a one-line judgment for each item: why it matters, not just what it is
- [x] Mark which items are beginner-friendly, reproducible, frontier-only, or industrial signal

### Topic-Specific Tasks

#### `docs/roadmap/vla.md`

- [x] Strengthen the distinction between `language-conditioned BC`, `foundation-policy pretraining`, `hierarchical VLA`, and `on-device / humanoid VLA`
- [x] Add a `representative systems matrix` comparing RT-1, RT-2, PaLM-E, Octo, OpenVLA, pi0, Gemini Robotics, GR00T, Helix, Seed GR-3
- [x] Add `Academic Labs & Company Systems` section with Stanford, Berkeley, Google DeepMind, NVIDIA, Physical Intelligence, Figure, ByteDance Seed, Alibaba DAMO
- [x] Expand build paths into beginner open-source, low-cost real robot, and frontier system analysis tracks

#### `docs/roadmap/world_model.md`

- [x] Separate `latent world models`, `video world models`, `object-centric models`, and `world-model-plus-planner` routes more sharply
- [x] Add a `decision interface` comparison table: prediction only vs planning vs RL vs data generation
- [x] Add `Academic Labs & Company Systems` section with Meta, Berkeley, DeepMind, NVIDIA GEAR, CMU, Stanford, Physical Intelligence-adjacent systems where relevant
- [x] Expand build paths into benchmark-first, manipulation-first, and VLA-bridge tracks

#### `docs/roadmap/rl.md`

- [x] Reframe RL as a placement question in the embodied stack: simulation, offline datasets, pretrained policy post-training, world-model RL, real-world RL
- [x] Add a matrix of `where RL sits`, `what signal it uses`, `what it improves`, and `what it breaks`
- [x] Add `Academic Labs & Company Systems` section focused on Berkeley, CMU, DeepMind, NVIDIA, ByteDance Seed, OpenAI historical milestones, legged robotics groups
- [x] Expand build paths into simulation control, humanoid/legged RL, and manipulation refinement lines

#### `docs/roadmap/manipulation.md`

- [x] Add a clearer decomposition of tabletop, mobile manipulation, bimanual manipulation, articulated object operation, and contact-rich tasks
- [x] Add a `representative system comparison` across ACT, Diffusion Policy, Mobile ALOHA, TidyBot++, Octo, OpenVLA, pi0, Helix
- [x] Add `Academic Labs & Company Systems` section with Stanford, Berkeley, Columbia, CMU, Figure, NVIDIA, ByteDance Seed, Alibaba DAMO
- [x] Expand build paths into low-cost real robot, simulation-first, benchmark-first, and foundation-policy comparison routes

#### `docs/roadmap/grasping.md`

- [x] Split parallel-jaw, cluttered-scene, task-oriented, dexterous, and active-perception grasping more explicitly
- [x] Add `benchmark-to-system` mapping from GraspNet / Contact-GraspNet style work to deployable pick pipelines
- [x] Add `Academic Labs & Company Systems` section with Berkeley, UW, NVIDIA, CMU, grasping-heavy labs and industrial manipulation systems
- [x] Expand build paths into practical pick-and-place, research clutter grasping, task-oriented grasping, and dexterous-hand tracks

#### `docs/roadmap/affordance.md`

- [x] Clarify the difference between affordance as region prediction, function prediction, interaction prior, and executable action prior
- [x] Add a `representation family` matrix: pixel, point cloud, part graph, language-conditioned affordance, interactive affordance
- [x] Add `Academic Labs & Company Systems` section with Berkeley, Stanford, PKU, ZJU, SJTU, part-level manipulation and articulated-object groups
- [x] Expand build paths into dense 3D affordance, articulated object interaction, retrieval transfer, and affordance-guided manipulation tracks

### Exit Criteria

- [x] All six topic pages use the same section spine
- [x] Every page can answer both `what is this direction` and `how do I build into it`
- [x] Every page contains explicit labs, companies, toolchains, datasets, and build paths
- [x] A new reader can choose a path without leaving the page confused about next steps

## Phase 2: Build The Ecosystem Maps

This is the differentiation layer. Do not make these pages simple name directories.

### Page Structure

- [x] Create `docs/maps/academia.md`
- [x] Create `docs/maps/industry.md`
- [x] Keep or mirror content from existing `docs/resources/academia_map.md` and `docs/resources/industry_map.md`

### Required Entry Schema

Each institution or company entry should answer:

- [x] name
- [x] institution or company type
- [x] main line of work
- [x] representative papers, systems, or projects
- [x] official homepage, lab page, project page, code page
- [x] bias: algorithm, system, hardware, platform
- [x] why this node is worth tracking

### `docs/maps/academia.md`

- [x] Build by region first, then by research line second
- [x] Cover at least Stanford, Berkeley, CMU, MIT, Tsinghua, PKU, SJTU, ZJU, NJU, USTC, Fudan
- [x] Add a `who to watch` researcher layer instead of a raw person list
- [x] Group researchers into themes such as `VLA / foundation models`, `robot learning / control`, `grasping / embodied vision`, `systems / humanoids / platforms`
- [x] For each priority scholar, add institution, main direction, representative work, tracking reason, and stable links

### `docs/maps/industry.md`

- [x] Cover Google DeepMind, Meta, NVIDIA, OpenAI, Figure, Physical Intelligence, ByteDance Seed, Alibaba DAMO, Huawei, Meituan
- [x] For each company, answer `which stack layer they are strongest in`
- [x] Add a `signal type` field: model release, benchmark release, robot platform, deployment system, open-source stack
- [x] Add a `what to track next` field so the page becomes a living watchlist

### Seed Researcher Watchlists

#### International priority list

- [x] Shuran Song
- [x] Chelsea Finn
- [x] Fei-Fei Li
- [x] Sergey Levine
- [x] Pieter Abbeel
- [x] Ken Goldberg
- [x] Jitendra Malik
- [x] Pulkit Agrawal
- [x] Dieter Fox
- [x] Yonatan Bisk
- [x] Dave Held
- [x] Oliver Kroemer
- [x] Andrea Bajcsy
- [x] Deepak Pathak
- [x] Katerina Fragkiadaki
- [x] Chris Atkeson
- [x] Zackory Erickson
- [x] Jean Oh

#### China and Chinese scholar priority list

- [x] Jianlan Luo
- [x] Huazhe Xu
- [x] Hao Su
- [x] Cewu Lu
- [x] Ping Luo
- [x] Hao Dong
- [x] Guoyue Zhou
- [x] Xinlei Chen
- [x] Wenbo Ding
- [x] Yaqin Zhang
- [x] Hong Liu
- [x] Qining Wang
- [x] Tao Wang
- [x] Hao Zhao
- [x] Yao Mu
- [x] Yanyong Zhang
- [x] Zhenshan Bing
- [x] Shangke Lv
- [x] Yugang Jiang
- [x] Yan Wang
- [x] He Wang
- [x] Qian Wang
- [x] Yilun Chen
- [x] Jiyang Gao
- [x] Tianlan Shao
- [x] Zheyuan Jiang

### Exit Criteria

- [x] A reader can tell who leads which line, not just who exists
- [x] The pages support tracking ecosystems, not collecting names
- [x] Person entries are anchored to labs, systems, and representative work

## Phase 3: Resource Layer And Cross Matrices

This phase makes the repository usable for project selection.

### `docs/resources/benchmarks.md`

- [x] Create a benchmark-first page covering CALVIN, LIBERO, BEHAVIOR-1K, Meta-World, ManiSkill, GraspNet, PartNet-Mobility, RoboCasa where appropriate
- [x] For each benchmark, include task type, modality, embodiment, evaluation protocol, code maturity, and best-fit use cases
- [x] Add a `when not to use this benchmark` note for each major benchmark

### Expand Existing Resource Pages

#### `docs/resources/datasets.md`

- [x] Split by `generalist robot data`, `manipulation`, `grasping`, `affordance`, `humanoid`, `multimodal teleoperation`
- [x] Add dataset scale, embodiment coverage, modality, license/access notes, and code ecosystem fields

#### `docs/resources/frameworks.md`

- [x] Split by `policy learning`, `RL/control`, `sim-to-real`, `grasping / affordance`, `whole-body / humanoid`
- [x] Add `best for`, `ecosystem maturity`, and `real-world friendliness` fields

#### `docs/resources/simulators.md`

- [x] Add task-level guidance: manipulation, locomotion, mobile manipulation, dexterous hand, benchmark reproduction
- [x] Add a quick matrix comparing MuJoCo, Isaac Lab, ManiSkill, SAPIEN, Habitat, BEHAVIOR, Meta-World

#### `docs/resources/venues.md`

- [x] Split venues by `robotics core`, `vision core`, `ML core`, `high-signal journals`
- [x] Add a short note on what kind of embodied work tends to appear in each venue

### Cross Matrices

- [x] Add a `task -> benchmark -> dataset -> simulator -> framework` matrix
- [x] Add a `goal -> recommended stack` quick selector
- [x] Add a `research question -> best entry points` quick selector

### Exit Criteria

- [x] A reader can start from a task and work backward to a usable stack
- [x] A reader can start from a dataset or framework and know what it is good for

## Phase 4: Build Path Library

This phase turns the repository from a guide into an execution atlas.

### Required Directory

- [x] Create `docs/build_paths/`

### Required Pages

- [x] `docs/build_paths/vla_entry.md`
- [x] `docs/build_paths/world_model.md`
- [x] `docs/build_paths/grasping_affordance.md`
- [x] `docs/build_paths/sim2real.md`
- [x] `docs/build_paths/real_robot.md`

### Required Structure For Every Build Path

- [x] who this path is for
- [x] prerequisite knowledge
- [x] minimum hardware and software stack
- [x] core papers and project pages
- [x] exact dataset / simulator / framework stack
- [x] 2-week milestone
- [x] 4-week milestone
- [x] 8-week milestone
- [x] expected failure modes
- [x] what success should look like

### Initial Build Paths To Prioritize

- [x] VLA beginner line
- [x] world-model line
- [x] grasping plus affordance line
- [x] sim-to-real line
- [x] real-robot low-cost line

### Exit Criteria

- [x] A motivated beginner can follow one path without needing to invent the workflow
- [x] Each path names concrete tools, data, and expected outputs

## Phase 5: Information Design Upgrade

The repository already looks good. Now it has to navigate well.

### README Upgrade

- [x] Add a fixed top-level navigation summary with `Roadmaps`, `Maps`, `Resources`, `Build Paths`, `Paper Lists`
- [x] Add a `How to use this repo` block for beginner, builder, and researcher personas
- [x] Add a `recommended starting routes` block with explicit links into the build-path pages
- [x] Add a `why this repo is different` block framed around `system stack`, `judgment`, `build path`, `ecosystem map`

### Topic-Page Navigation Elements

- [x] Add top anchors or a manual table of contents
- [x] Add a `representative systems matrix` where appropriate
- [x] Add a `related pages` footer linking to relevant resource and map pages
- [x] Add a small `research radar` block listing what to watch next in that area

### Visual-To-Information Conversion

- [x] Keep existing banner art
- [x] Add visual labels that function as navigation cues instead of pure decoration
- [x] Keep page rhythm consistent so readers can scan different topics quickly

### Exit Criteria

- [x] The page design helps users decide where to go next
- [x] Users can scan, compare, and route themselves without reading every paragraph

## Phase 6: Curation And Update Operations

If this repository is going to stay useful, it needs an update loop.

### Editorial Rules

- [x] Define what counts as `classical backbone`
- [x] Define what counts as `frontier watchlist`
- [x] Define what counts as `open-source reproducible`
- [x] Define what counts as `industry signal worth tracking`

### Maintenance Checklist

- [x] Review frontier entries monthly
- [x] Review broken links quarterly
- [x] Review whether each topic still reflects the active stack boundaries
- [x] Keep paper lists secondary to guide pages, not the other way around

### Contribution Controls

- [x] Update `CONTRIBUTING.md` so contributors add judgment, not just links
- [x] Require every new item to include a one-line relevance note
- [x] Prefer official project pages and code repos over secondary summaries

### Exit Criteria

- [x] The repository can scale without becoming noisy
- [x] Future contributors follow the atlas logic instead of turning pages into dumps

## Recommended Execution Order

1. Finish Phase 0 so the structure and navigation baseline are stable.
2. Finish Phase 1 so the six roadmap pages become the real backbone.
3. Finish Phase 2 so the repository gains ecosystem differentiation.
4. Finish Phase 3 so readers can select datasets, simulators, benchmarks, and frameworks from tasks.
5. Finish Phase 4 so the atlas becomes project-executable.
6. Finish Phase 5 and Phase 6 so the repository stays usable and maintainable.

## Success Definition

The repository is upgraded when a new reader can do all three of the following without external help:

- identify which system layer they want to work on
- choose a realistic build path with tools, data, and benchmarks
- track the most important labs, companies, and researchers in that slice of embodied AI
