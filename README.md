# Awesome Isaac Lab [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

[![Links](https://github.com/Lynn-hh/awesome-isaac-lab/actions/workflows/links.yml/badge.svg)](https://github.com/Lynn-hh/awesome-isaac-lab/actions/workflows/links.yml)
[![License: CC0-1.0](https://img.shields.io/badge/license-CC0--1.0-lightgrey.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

> A curated list of projects, tools, papers and learning resources for [NVIDIA Isaac Lab](https://github.com/isaac-sim/IsaacLab),
> the open-source GPU-accelerated framework for robot learning and the successor to Isaac Gym and Orbit.

Every entry was checked to be built on Isaac Lab or to support it as a backend. Projects that support several simulators are
marked *(multi-sim)*. Last full review: September 2026.

## Contents

- [Start Here](#start-here)
- [Official](#official)
  - [Core](#core)
  - [Physics and Rendering Backends](#physics-and-rendering-backends)
  - [NVIDIA Projects Built on Isaac Lab](#nvidia-projects-built-on-isaac-lab)
- [Learning Resources](#learning-resources)
  - [Tutorials and Courses](#tutorials-and-courses)
  - [Migration Guides](#migration-guides)
  - [Blog Posts](#blog-posts)
  - [Videos](#videos)
  - [Core Papers](#core-papers)
- [RL and Learning Libraries](#rl-and-learning-libraries)
- [Tools](#tools)
  - [Teleoperation and Data Collection](#teleoperation-and-data-collection)
  - [Assets and Conversion](#assets-and-conversion)
  - [Sensors](#sensors)
  - [Visualization and Performance](#visualization-and-performance)
  - [Cloud, Cluster and Developer Setup](#cloud-cluster-and-developer-setup)
- [Projects](#projects)
  - [Legged Locomotion](#legged-locomotion)
  - [Humanoids and Whole-Body Control](#humanoids-and-whole-body-control)
  - [Manipulation](#manipulation)
  - [Dexterous Hands](#dexterous-hands)
  - [Mobile Manipulation and Navigation](#mobile-manipulation-and-navigation)
  - [Aerial Robots](#aerial-robots)
  - [Benchmarks and Evaluation](#benchmarks-and-evaluation)
  - [Other Domains](#other-domains)
- [Sim-to-Real and Deployment](#sim-to-real-and-deployment)
- [Research Papers with Code](#research-papers-with-code)
- [Historical](#historical)
- [Related Lists](#related-lists)
- [Contributing](#contributing)

## Start Here

1. Read the [Isaac Lab documentation](https://isaac-sim.github.io/IsaacLab/) and install Isaac Lab.
2. Work through the [official tutorials](https://isaac-sim.github.io/IsaacLab/main/source/tutorials/index.html), or the
   NVIDIA learning path [Getting Started With Isaac Lab](https://docs.nvidia.com/learning/physical-ai/getting-started-with-isaac-lab/latest/index.html).
3. Train a first policy with [RSL-RL](https://github.com/leggedrobotics/rsl_rl) on one of the built-in locomotion or manipulation tasks.
4. Start your own project with the [template generator](https://isaac-sim.github.io/IsaacLab/develop/source/developer-tools/template_generator.html),
   then browse [Projects](#projects) for similar work.

## Official

### Core

- [Isaac Lab](https://github.com/isaac-sim/IsaacLab) - GPU-accelerated framework for robot learning (RL, imitation learning, motion planning). Version 3.0 on `develop` adds a multi-backend architecture with PhysX, Newton and the experimental kit-less OVPhysX backend.
- [Isaac Lab Documentation](https://isaac-sim.github.io/IsaacLab/) - Installation, tutorials, how-to guides and API reference for the `main` and `develop` branches.
- [Isaac Sim](https://github.com/isaac-sim/IsaacSim) - NVIDIA's open-source robotics simulator on Omniverse, which provides the PhysX, RTX rendering and importer stack for Isaac Lab's Kit-based workflows.
- [Isaac Lab-Arena](https://github.com/isaac-sim/IsaacLab-Arena) - Framework on top of Isaac Lab for composing simulation environments and evaluating robot policies at scale.
- [Isaac Lab Mimic](https://isaac-sim.github.io/IsaacLab/develop/source/features/imitation-learning/index.html) - Built-in extension that generates synthetic demonstrations from a few teleoperated ones, including SkillGen with cuRobo.
- [Isaac Teleop](https://github.com/NVIDIA/IsaacTeleop) - XR and device teleoperation framework with retargeting, which replaces Isaac Lab's native OpenXR teleop stack from Isaac Lab 3.0.
- [Template Generator](https://isaac-sim.github.io/IsaacLab/develop/source/developer-tools/template_generator.html) - Built-in tool that scaffolds external Isaac Lab projects and tasks.
- [Show and Tell](https://github.com/isaac-sim/IsaacLab/discussions/categories/show-and-tell) - GitHub Discussions category where users share Isaac Lab projects and tutorials.

### Physics and Rendering Backends

- [Newton](https://github.com/newton-physics/newton) - Open-source GPU physics engine built on NVIDIA Warp and hosted by the Linux Foundation, used as a physics backend in Isaac Lab 3.0.
- [MuJoCo Warp](https://github.com/google-deepmind/mujoco_warp) - GPU port of MuJoCo on Warp, available as the MJWarp solver in Newton and Isaac Lab's Newton backend.
- [PhysX SDK](https://github.com/NVIDIA-Omniverse/PhysX) - Open-source physics SDK behind Isaac Lab's PhysX and OVPhysX backends.
- [OVPhysX Backend](https://isaac-sim.github.io/IsaacLab/develop/source/concepts/ovphysx.html) - Isaac Lab's experimental kit-less PhysX backend, distributed as the `ovphysx` Python package.
- [NVIDIA Warp](https://github.com/NVIDIA/warp) - Python framework for GPU simulation kernels, the foundation of Newton and Isaac Lab 3.0's Warp-native data paths.
- [ovrtx](https://github.com/NVIDIA-Omniverse/ovrtx) - C and Python library for Omniverse RTX sensor rendering, used by Isaac Lab 3.0 as a kit-less camera renderer (pre-release).

### NVIDIA Projects Built on Isaac Lab

- [Isaac GR00T](https://github.com/NVIDIA/Isaac-GR00T) - Open foundation model for generalist humanoid robots, evaluated in Isaac Lab-Arena and fine-tuned on Isaac Lab tasks.
- [cuRobo](https://github.com/NVlabs/curobo) - CUDA-accelerated motion generation library, used by Isaac Lab Mimic's SkillGen.
- [Isaac Lab Evaluation Tasks](https://github.com/isaac-sim/IsaacLabEvalTasks) - Industrial manipulation tasks for evaluating GR00T N1 policies.
- [Isaac Lab Eureka](https://github.com/NVlabs/IsaacLabEureka) - LLM-based reward-function generation and tuning for Isaac Lab direct-workflow environments.
- [AutoData](https://github.com/isaac-sim/AutoData) - Generation of robot demonstration trajectories at scale on Isaac Lab and Isaac Lab-Arena.
- [Isaac Sim ROS Workspaces](https://github.com/isaac-sim/IsaacSim-ros_workspaces) - ROS 2 Humble and Jazzy workspaces with sample packages for Isaac Sim.

NVIDIA research code for humanoids, navigation and manipulation (GR00T Whole-Body Control, HOVER, ProtoMotions, COMPASS, DextrAH and others) is listed under [Projects](#projects).

## Learning Resources

### Tutorials and Courses

- [Official Tutorials](https://isaac-sim.github.io/IsaacLab/main/source/tutorials/index.html) - Step-by-step tutorials on simulation setup, assets, scenes, environments, sensors and controllers.
- [Isaac Lab 3.0 Tutorial: SO-101 Vial Place](https://isaac-sim.github.io/IsaacLab/develop/source/setup/tutorial.html) - End-to-end tutorial that packages, trains and evaluates an SO-101 task as a downstream project ([code](https://github.com/isaac-sim/IsaacLabTutorial)).
- [Getting Started With Isaac Lab](https://docs.nvidia.com/learning/physical-ai/getting-started-with-isaac-lab/latest/index.html) - NVIDIA learning path covering robot learning basics, training first robots and sim-to-real concepts.
- [Accelerating Robot Learning With Isaac Lab and Newton](https://docs.nvidia.com/learning/physical-ai/getting-started-with-newton/latest/index.html) - NVIDIA hands-on course on Newton and training policies with it in Isaac Lab.
- [Train an SO-101 Robot From Sim-to-Real With NVIDIA Isaac](https://docs.nvidia.com/learning/physical-ai/sim-to-real-so-101/latest/index.html) - NVIDIA workshop on an end-to-end SO-101 workflow with Isaac Lab and GR00T ([code](https://github.com/isaac-sim/Sim-to-Real-SO-101-Workshop)).
- [Isaac Spinning Up](https://github.com/Mayankm96/isaac-spinning-up) - Walkthrough for building an Isaac Lab extension, using BeyondMimic integration as the example.
- [Ray Integration Guide](https://isaac-sim.github.io/IsaacLab/develop/source/features/ray.html) - Official guide to multi-job training and hyperparameter tuning with Ray.

### Migration Guides

- [Migrating to Isaac Lab 3.0](https://isaac-sim.github.io/IsaacLab/develop/source/migration/migrating_to_isaaclab_3-0.html) - API and workflow changes from Isaac Lab 2.x to 3.0.
- [Migrating from IsaacGymEnvs](https://isaac-sim.github.io/IsaacLab/main/source/migration/migrating_from_isaacgymenvs.html) - Porting Isaac Gym environments to Isaac Lab.

### Blog Posts

- [Fast-Track Robot Learning in Simulation Using NVIDIA Isaac Lab](https://developer.nvidia.com/blog/fast-track-robot-learning-in-simulation-using-nvidia-isaac-lab/) - Overview of Isaac Lab features and workflows.
- [Closing the Sim-to-Real Gap: Training Spot Quadruped Locomotion with NVIDIA Isaac Lab](https://developer.nvidia.com/blog/closing-the-sim-to-real-gap-training-spot-quadruped-locomotion-with-nvidia-isaac-lab/) - Training and deploying a Spot locomotion policy.
- [Building a Synthetic Motion Generation Pipeline for Humanoid Robot Learning](https://developer.nvidia.com/blog/building-a-synthetic-motion-generation-pipeline-for-humanoid-robot-learning/) - GR00T-Mimic demonstration generation in Isaac Lab.
- [Streamline Robot Learning with Whole-Body Control and Enhanced Teleoperation in NVIDIA Isaac Lab 2.3](https://developer.nvidia.com/blog/streamline-robot-learning-with-whole-body-control-and-enhanced-teleoperation-in-nvidia-isaac-lab-2-3/) - Isaac Lab 2.3 features.
- [Train a Quadruped Locomotion Policy and Simulate Cloth Manipulation with NVIDIA Isaac Lab and Newton](https://developer.nvidia.com/blog/train-a-quadruped-locomotion-policy-and-simulate-cloth-manipulation-with-nvidia-isaac-lab-and-newton/) - Early Newton usage in Isaac Lab.
- [Simplify Generalist Robot Policy Evaluation in Simulation with NVIDIA Isaac Lab-Arena](https://developer.nvidia.com/blog/simplify-generalist-robot-policy-evaluation-in-simulation-with-nvidia-isaac-lab-arena/) - Introduction to Isaac Lab-Arena.
- [R²D²: Scaling Multimodal Robot Learning with NVIDIA Isaac Lab](https://developer.nvidia.com/blog/r2d2-scaling-multimodal-robot-learning-with-nvidia-isaac-lab/) - Multimodal robot learning at scale with Isaac Lab.
- [Newton Adds Contact-Rich Manipulation and Locomotion Capabilities for Industrial Robotics](https://developer.nvidia.com/blog/newton-adds-contact-rich-manipulation-and-locomotion-capabilities-for-industrial-robotics/) - Newton solver features relevant to Isaac Lab.

### Videos

- [Isaac Lab Tutorial Series (LycheeAI)](https://www.youtube.com/watch?v=Y-K1cAvnSFI) - Community tutorial series, starting with interactive scenes.
- [Hyperparameter Tuning for Robotics in NVIDIA Isaac Lab](https://www.youtube.com/watch?v=z7MDgSga2Ho) - Walkthrough of Ray-based tuning, linked from the official docs.

### Core Papers

- [Isaac Lab: A GPU-Accelerated Simulation Framework for Multi-Modal Robot Learning](https://arxiv.org/abs/2511.04831) - Isaac Lab technical report (2025).
- [Orbit: A Unified Simulation Framework for Interactive Robot Learning Environments](https://arxiv.org/abs/2301.04195) - The framework Isaac Lab grew from (RA-L 2023).
- [Isaac Gym: High Performance GPU-Based Physics Simulation For Robot Learning](https://arxiv.org/abs/2108.10470) - The predecessor of Isaac Lab (2021).
- [RSL-RL: A Learning Library for Robotics Research](https://arxiv.org/abs/2509.10771) - The default RL library for many Isaac Lab tasks (2025).
- [MimicGen: A Data Generation System for Scalable Robot Learning using Human Demonstrations](https://arxiv.org/abs/2310.17596) - The data generation method behind Isaac Lab Mimic (2023).
- [DexMimicGen: Automated Data Generation for Bimanual Dexterous Manipulation via Imitation Learning](https://arxiv.org/abs/2410.24185) - Multi-end-effector data generation supported in Isaac Lab Mimic (2024).

## RL and Learning Libraries

- [RSL-RL](https://github.com/leggedrobotics/rsl_rl) - PPO-centered library from ETH Zurich's Robotic Systems Lab, the default for many Isaac Lab tasks.
- [skrl](https://github.com/Toni-SM/skrl) - Modular RL library in PyTorch, JAX and Warp, with loaders and wrappers for Isaac Lab environments.
- [rl_games](https://github.com/Denys88/rl_games) - GPU-oriented RL implementations inherited from Isaac Gym and supported by Isaac Lab's training scripts.
- [Stable-Baselines3](https://github.com/DLR-RM/stable-baselines3) - PyTorch RL algorithms, supported through Isaac Lab's vectorized-environment wrapper.
- [TorchRL](https://github.com/pytorch/rl) - PyTorch RL library, supported through a wrapper and PPO configuration on the `develop` branch.
- [robomimic](https://github.com/ARISE-Initiative/robomimic) - Learning-from-demonstration framework used by Isaac Lab's imitation learning scripts.
- [LeRobot](https://github.com/huggingface/lerobot) - Hugging Face robot learning library that loads Isaac Lab-Arena environments through EnvHub ([guide](https://huggingface.co/docs/lerobot/envhub_isaaclab_arena)).
- [RLinf](https://github.com/RLinf/RLinf) - Distributed RL infrastructure for embodied AI, including RL post-training of VLA models on Isaac Lab tasks *(multi-sim)*.
- [verl-vla](https://github.com/verl-project/verl-vla) - VLA post-training framework for data collection, fine-tuning and RL, with LIBERO and Isaac Lab-Arena environments *(multi-sim)*.
- [Ray](https://github.com/ray-project/ray) - Distributed compute framework used by Isaac Lab for multi-job training and hyperparameter tuning.
- [Robotic World Model](https://github.com/leggedrobotics/robotic_world_model) - Isaac Lab extension for model-based RL with learned neural dynamics models, demonstrated on ANYmal D.
- [beyondAMP](https://github.com/Renforce-Dynamics/beyondAMP) - Pipeline for adding Adversarial Motion Priors to Isaac Lab robot setups *(multi-sim)*.
- [rsl_rl_sac](https://github.com/leggedrobotics/rsl_rl_sac) - Soft Actor-Critic extension of RSL-RL for legged locomotion, used with a companion Isaac Lab fork.
- [Telekinesis RLbotics](https://github.com/telekinesis-ai/telekinesis-rlbotics) - Lightweight PyTorch RL library with training support for Isaac Lab, mjlab and Gymnasium environments.
- [MorphoSymm-RSL-RL](https://github.com/iit-DLSLab/morphosymm-rsl-rl) - RSL-RL extension that exploits morphological symmetries in Isaac Lab training.

## Tools

### Teleoperation and Data Collection

- [VisionProTeleop](https://github.com/Improbable-AI/VisionProTeleop) - Apple Vision Pro app and Python library that streams hand tracking for robot teleoperation, with Isaac Lab scene streaming *(multi-sim)*.
- [LeIsaac](https://github.com/LightwheelAI/leisaac) - SO-101 teleoperation in Isaac Lab with the SO101 leader arm, including data collection and conversion to LeRobot datasets.
- [Isaac XR Teleop Sample Client](https://github.com/isaac-sim/isaac-xr-teleop-sample-client-apple) - Apple Vision Pro app for streaming and teleoperating Isaac Sim and Isaac Lab scenes over CloudXR.
- [LeRobot SO-101 Teleop](https://github.com/liorbenhorin/lerobot_so101_teleop) - Sample Isaac Lab environment for collecting SO-101 demonstrations in simulation.
- [GraspDataGen](https://github.com/NVlabs/GraspDataGen) - Gripper grasp data generation and physics validation on Isaac Lab.
- [SoftMimicGen](https://github.com/NVlabs/SoftMimicGen) - MimicGen-style demonstration generation for deformable-object manipulation.

### Assets and Conversion

- [urdf-usd-converter](https://github.com/newton-physics/urdf-usd-converter) - Converts URDF robot descriptions to OpenUSD.
- [mujoco-usd-converter](https://github.com/newton-physics/mujoco-usd-converter) - Converts MuJoCo MJCF models to OpenUSD.
- [MJCF2USD](https://github.com/LightwheelAI/mjcf2usd) - Isaac Sim extension for converting MuJoCo MJCF files to USD.
- [Newton USD Schemas](https://github.com/newton-physics/newton-usd-schemas) - OpenUSD schemas for authoring Newton-specific physics properties.
- [Newton Assets](https://github.com/newton-physics/newton-assets) - Permissively licensed robot and object assets used for Newton testing.
- [Lightwheel SimReady Assets](https://github.com/LightwheelAI/Lightwheel-simready-asset) - Simulation-ready 3D assets validated with Isaac Lab, free for non-commercial use.

### Sensors

- [TacEx](https://github.com/DH-Ng/TacEx) - GelSight-style vision-based tactile sensor simulation for Isaac Sim and Isaac Lab.
- [sharpa-tacmap](https://github.com/sharpa-robotics/sharpa-tacmap) - TacMap-based tactile sensor module that plugs into Isaac Lab environments.

### Visualization and Performance

- [Visualizers](https://isaac-sim.github.io/IsaacLab/develop/source/concepts/visualization.html) - Isaac Lab 3.0's Kit, Newton, Rerun and Viser visualizers.
- [Rerun](https://github.com/rerun-io/rerun) - Multimodal data visualization SDK, available as an Isaac Lab 3.0 visualizer backend.
- [Viser](https://github.com/viser-project/viser) - Web-based 3D visualization library for Python, available as an Isaac Lab 3.0 visualizer backend.
- [Omniperf](https://github.com/NVIDIA/omniperf) - Performance tracking and dashboards for Isaac Lab across GPUs and physics backends.

### Cloud, Cluster and Developer Setup

- [Isaac Automator](https://github.com/isaac-sim/IsaacAutomator) - Deploys Isaac Sim, Isaac Lab and Isaac Lab-Arena to AWS, GCP, Azure and Alibaba Cloud.
- [Isaac Launchable](https://github.com/isaac-sim/isaac-launchable) - Browser-accessible Isaac Sim and Isaac Lab environment with VS Code and streaming, deployable on NVIDIA Brev.
- [Docker and Cluster Guide](https://isaac-sim.github.io/IsaacLab/develop/source/workflows/docker/cluster.html) - Running Isaac Lab containers on SLURM and PBS clusters with Singularity/Apptainer.
- [Editor Setup](https://isaac-sim.github.io/IsaacLab/develop/source/developer-tools/editor_setup.html) - Configuring VS Code and compatible editors with the repository's shared settings.
- [Agent Skills](https://isaac-sim.github.io/IsaacLab/develop/source/developer-tools/agent_skills.html) - Instruction files that help coding agents with installation, migration and RL debugging.
- [isaaclab-h100](https://github.com/Kyk0/isaaclab-h100) - Guide and scripts for headless Isaac Lab 2.x training on H100 GPUs, with rollout recording and browser replay without RTX rendering.

## Projects

### Legged Locomotion

- [robot_lab](https://github.com/fan-ziqi/robot_lab) - RL velocity-tracking environments for many quadrupeds (ANYmal D, Unitree Go2/B2/A1, Deep Robotics Lite3), wheeled-legged robots and humanoids.
- [unitree_rl_lab](https://github.com/unitreerobotics/unitree_rl_lab) - Unitree's official RL environments for Go2, H1 and G1, with MuJoCo sim2sim and real-robot deployment.
- [LeggedLab](https://github.com/Hellod035/LeggedLab) - Direct-workflow framework for legged locomotion, tested sim-to-real on Unitree G1 and H1.
- [Isaac-RL-Two-wheel-Legged-Bot](https://github.com/jaykorea/Isaac-RL-Two-wheel-Legged-Bot) - Environments for the Flamingo two-wheel-legged robot with constraints-as-terminations and zero-shot sim-to-real.
- [Isaaclab_Parkour](https://github.com/CAI23sbP/Isaaclab_Parkour) - Port of Extreme Parkour teacher-student training for the Unitree Go2.
- [rl_training](https://github.com/DeepRoboticsLab/rl_training) - Deep Robotics' RL training library for its Lite3 quadruped and M20 wheeled-legged robot.
- [the-bimo-project](https://github.com/mekion/the-bimo-project) - Open-source small bipedal robot kit with an Isaac Lab environment for training and deploying walking policies.
- [LocoWheeledLegged](https://github.com/zhaozijie2022/LocoWheeledLegged) - Locomotion for wheeled-legged robots focused on reward design and training stability, with sim-to-real configurations for the Go2W.
- [SpdrBot](https://github.com/Indystrycc/SpdrBot) - 3D-printable four-legged spider robot with URDF/USD assets and a direct-workflow RL project.
- [basic-locomotion-isaaclab](https://github.com/iit-DLSLab/basic-locomotion-isaaclab) - Quadruped locomotion (Aliengo, Go2, B2, A2, HyQReal2) with state estimation, RMA, symmetries, AMP, sim2sim and ROS 2 deployment.
- [bipedal_locomotion_isaaclab](https://github.com/Andy-xiong6/bipedal_locomotion_isaaclab) - Flat, rough and stair terrain tasks for point-foot bipeds such as the LimX TRON1.
- [go2_rl_robotlab](https://github.com/wertyuilife2/go2_rl_robotlab) - MoE-CTS robust Unitree Go2 locomotion (RSS 2026) on robot_lab, with MuJoCo sim2sim validation.
- [JEPLO](https://github.com/ASIG-X/JEPLO) - JEPA-based mapless LiDAR perceptive locomotion for the Unitree Go2.
- [himloco_lab](https://github.com/IsaacZH/himloco_lab) - Port of HIMLoco quadruped locomotion from Isaac Gym, with training, export and deployment scripts.
- [Learn-It-All Quadruped](https://github.com/youngboss2026/Learn-It-All-Full-Stack-EmbodiedAI-Quadruped-Robot) - Low-cost DIY quadruped covering mechanical design, RL training, sim2sim, ONNX export and real deployment.
- [LocoTouch](https://github.com/linchangyi1/LocoTouch) - Perceptive legged-robot policies, including tactile quadrupedal transport.
- [legged_rl_lab](https://github.com/zihanwang0422/legged_rl_lab) - Unitree Go2 walking and footstand tasks, G1 tasks and depth-based teacher-student parkour.
- [TARLoco](https://github.com/ammousa/TARLoco) - Blind quadruped locomotion that aligns teacher and student representations via contrastive learning (IROS 2025).
- [BDX-R-IsaacLab](https://github.com/BDX-R/BDX-R-IsaacLab) - RL training for BDX-R, a hobbyist bipedal robot inspired by Disney's BDX droids.
- [IsaacLab-Quadruped-Tasks](https://github.com/felipemohr/IsaacLab-Quadruped-Tasks) - Blind and vision-based flat, rough and stairs tasks for ANYmal D, Unitree Go2 and Spot.

### Humanoids and Whole-Body Control

- [GR00T Whole-Body Control](https://github.com/NVlabs/GR00T-WholeBodyControl) - NVIDIA humanoid whole-body controllers (Decoupled WBC, SONIC, MotionBricks) with checkpoints and deployment code; SONIC is trained in Isaac Lab.
- [whole_body_tracking](https://github.com/HybridRobotics/whole_body_tracking) - BeyondMimic motion tracking for sim-to-real-ready humanoid motions on the Unitree G1.
- [ProtoMotions](https://github.com/NVlabs/ProtoMotions) - NVIDIA framework for simulated digital humans and humanoid robots in motion imitation *(multi-sim)*.
- [MimicKit](https://github.com/xbpeng/MimicKit) - RL framework for motion imitation and control *(multi-sim)*.
- [ASAP](https://github.com/LeCAR-Lab/ASAP) - Aligning simulation and real-world physics for agile humanoid whole-body skills on the Unitree G1 (RSS 2025) *(multi-sim)*.
- [Berkeley Humanoid Lite](https://github.com/HybridRobotics/berkeley-humanoid-lite) - Open-source sub-$5,000 humanoid with training environments, sim2sim and real-robot deployment.
- [holosoma](https://github.com/amazon-far/holosoma) - Amazon FAR humanoid framework for locomotion, whole-body tracking, retargeting and deployment *(multi-sim)*.
- [TienKung-Lab](https://github.com/Open-X-Humanoid/TienKung-Lab) - Locomotion for the full-size TienKung humanoid combining AMP-style and periodic gait rewards.
- [InstinctLab](https://github.com/project-instinct/InstinctLab) - Project Instinct humanoid whole-body control RL for the Unitree G1.
- [BFM-Zero](https://github.com/LeCAR-Lab/BFM-Zero) - Promptable behavioral foundation model for humanoid control trained with unsupervised RL *(multi-sim)*.
- [HOVER](https://github.com/NVlabs/HOVER) - NVIDIA extension for training neural whole-body controllers for humanoids.
- [HDMI](https://github.com/LeCAR-Lab/HDMI) - Interactive humanoid whole-body skills on the Unitree G1 learned from monocular human videos.
- [HumanoidVerse](https://github.com/LeCAR-Lab/HumanoidVerse) - Multi-simulator humanoid learning framework with an Isaac Lab backend *(multi-sim)*.
- [humanoid_amp](https://github.com/linden713/humanoid_amp) - Adversarial Motion Priors on the Unitree G1.
- [legged_lab](https://github.com/zitongbai/legged_lab) - DeepMimic and AMP motion-imitation tasks for humanoids such as the Unitree G1.
- [GR00T-VisualSim2Real](https://github.com/NVlabs/GR00T-VisualSim2Real) - NVIDIA VIRAL and DoorMan: visual humanoid loco-manipulation policies trained for sim-to-real transfer.
- [WBC-AGILE](https://github.com/nvidia-isaac/WBC-AGILE) - NVIDIA workflow for humanoid loco-manipulation and whole-body control with sim-to-real transfer on Unitree G1 and Booster T1.
- [PMT](https://github.com/Mondo-Robotics/PMT) - Perceptive motion-tracking policies for the Unitree G1 with terrain perception and teacher-student distillation.
- [trackerLab](https://github.com/Renforce-Dynamics/trackerLab) - Humanoid motion retargeting, trajectory tracking and skill-level control from SMPL/FBX motion data.
- [DreamControl](https://github.com/GenRobo/DreamControl) - Whole-body humanoid scene interaction using diffusion-generated reference trajectories and RL.
- [MultiModalWBC](https://github.com/Renforce-Dynamics/MultiModalWBC) - Multi-modal whole-body motion mimicking (SMPL-X pose, SE(3) keypoints) on the Unitree G1.
- [roboparty_train](https://github.com/Roboparty/roboparty_train) - Training workspace for Roboparty robots with locomotion, AMP, BeyondMimic and parkour tasks.
- [Mini-Pi-Plus_BeyondMimic](https://github.com/HighTorque-Robotics/Mini-Pi-Plus_BeyondMimic) - BeyondMimic adapted to HighTorque Mini Pi Plus humanoids.
- [G1DWAQ_Lab](https://github.com/liuyufei-nubot/G1DWAQ_Lab) - DreamWaQ-based blind stair climbing for the Unitree G1, with sim2sim and real deployment.
- [MOSAIC](https://github.com/BAAI-Humanoid/MOSAIC) - Generalist humanoid motion tracking and whole-body teleoperation for the Unitree G1.
- [CoorDex](https://github.com/Skevinci/coordex) - Humanoid dexterous loco-manipulation using body and hand motion priors.
- [WEAVE](https://github.com/xiaohu-art/Weave) - Whole-body dexterous loco-manipulation learned from human-object interaction data.
- [gentle-humanoid-training](https://github.com/Axellwppr/gentle-humanoid-training) - Universal whole-body motion tracking with upper-body compliance for the Unitree G1.
- [isaac_asimov](https://github.com/menloresearch/isaac_asimov) - Locomotion policies for Menlo Research's open-source Asimov 1 humanoid.
- [booster_train](https://github.com/BoosterRobotics/booster_train) - Booster Robotics' BeyondMimic motion tracking for the T1, T2 and K1 humanoids.
- [engineai_rl_lab](https://github.com/engineai-robotics/engineai_rl_lab) - EngineAI's environments for the PM01 and T800 humanoids, with whole-body tracking and AMP tasks.

### Manipulation

- [UW Lab](https://github.com/UW-Lab/UWLab) - Framework on Isaac Lab adding manipulation (including Factory-extension assembly), locomotion and sim-to-real configurations.
- [DynamicVLA](https://github.com/hzxie/DynamicVLA) - Vision-language-action model for manipulating moving objects, with data and evaluation in Isaac Lab.
- [isaacLab.manipulation](https://github.com/NathanWu7/isaacLab.manipulation) - Manipulation tasks for robot arms and dexterous hands.
- [isaac_so_arm101](https://github.com/MuammerBay/isaac_so_arm101) - Tasks such as reaching for the SO-ARM100/101 arm, used in the LycheeAI tutorial series.
- [SoftVTBench](https://github.com/TuojingAI/SoftVTBench) - Visuo-tactile benchmark for safe deformable-object manipulation with a Franka arm and GelSight Mini sensors.
- [kinova_isaaclab_sim2real](https://github.com/louislelay/kinova_isaaclab_sim2real) - Kinova Gen3 reaching policy with sim-to-real transfer through ROS.
- [EgoVLA](https://github.com/RchalYang/EgoVLA_Release) - VLA model learned from egocentric human videos, evaluated on an Isaac Lab humanoid manipulation benchmark.
- [MetaIsaacGrasp](https://github.com/YitianShi/MetaIsaacGrasp) - Grasp learning data generation engine and test bench built on MetaGraspNetv2.
- [Re3Sim](https://github.com/InternRobotics/Re3Sim) - Real-to-sim pipeline using 3D reconstruction to generate photorealistic manipulation data.
- [manip-as-in-sim-suite](https://github.com/ByteDance-Seed/manip-as-in-sim-suite) - Camera depth models and WBCMimic data generation built on Isaac Lab Mimic.
- [LeHome Challenge](https://github.com/lehome-official/lehome-challenge) - Household garment manipulation challenge built on Isaac Lab and LeRobot.
- [UniVTAC](https://github.com/univtac/UniVTAC) - Visuo-tactile manipulation data generation, learning and benchmark platform built on TacEx.
- [cyclo_lab](https://github.com/ROBOTIS-GIT/cyclo_lab) - RL and imitation learning environments with sim-to-real support for ROBOTIS robots such as the OMY arm.
- [openarm_isaac_lab](https://github.com/enactic/openarm_isaac_lab) - Reach, cube lift and drawer opening environments for the OpenArm open-source arm.
- [mindmap](https://github.com/nvidia-isaac/nvblox_mindmap) - Spatial-memory 3D action policies with Isaac Lab data generation and evaluation.
- [Tabero](https://github.com/NathanWu7/Tabero) - Tactile foundation model and tactile-augmented LIBERO benchmark.
- [Isaac_Lab_UR5e_Peg_in_Hole](https://github.com/JonasFano/Isaac_Lab_UR5e_Peg_in_Hole) - RL peg-in-hole insertion with a UR5e using differential IK and impedance control.
- [gearboxAssembly](https://github.com/rocochallenge/gearboxAssembly) - Gearbox assembly challenge for the Galaxea R1 robot.
- [YAMLab](https://github.com/ARISE-Initiative/yamlab) - Bimanual YAM robot framework for teleoperation, Isaac Lab Mimic data generation and parallel evaluation.
- [SRSA](https://github.com/NVlabs/SRSA) - Skill retrieval and adaptation for contact-rich robotic assembly (ICLR 2025).

### Dexterous Hands

- [video_to_data](https://github.com/nvidia-isaac/video_to_data) - Reconstructs human demonstration videos and grounds them as RL policies for a Sharpa dexterous hand.
- [SimToolReal](https://github.com/tylerlum/simtoolreal) - Object-centric policy for zero-shot dexterous tool manipulation *(multi-sim)*.
- [DextrAH](https://github.com/NVlabs/DEXTRAH) - Kuka arm with Allegro hand grasping via privileged RL and distillation.
- [DexVerse](https://github.com/ycyao216/DexVerse) - Multi-task, multi-embodiment dexterous manipulation benchmark.
- [sharpa-rl-lab](https://github.com/sharpa-robotics/sharpa-rl-lab) - RL examples for the Sharpa dexterous hand.
- [ReGrind](https://github.com/yunhaif/regrind) - Retargeting-guided RL recipe for dexterous manipulation.
- [RevoLab](https://github.com/BrainCoTech/RevoLab) - RL examples for the BrainCo Revo3 dexterous hand.
- [Bench2Dex](https://github.com/Bench2Dex/Bench2Dex) - Visuo-tactile bimanual dexterous manipulation benchmark across multiple hands.
- [GraspQP](https://github.com/leggedrobotics/graspqp) - Differentiable force-closure optimization for dexterous grasp synthesis (CoRL 2025).
- [RoTO](https://github.com/elle-miller/roto) - Robot Tactile Olympiad RL benchmark with Allegro, ORCA and Shadow hands plus a Franka arm.
- [LEAP_Hand_Isaac_Lab](https://github.com/leap-hand/LEAP_Hand_Isaac_Lab) - In-hand cube reorientation with the LEAP Hand v1, including sim-to-real code.
- [ViserDex](https://github.com/leggedrobotics/ViserDex) - Visual sim-to-real framework with an object pose estimator and in-hand reorientation training.
- [UHAS_sim](https://github.com/IRVLUTD/UHAS_sim) - In-hand cube reorientation using a unified hand action space across hands.

### Mobile Manipulation and Navigation

- [NavDP](https://github.com/InternRobotics/NavDP) - Navigation diffusion policy with privileged information, with an Isaac Sim / Isaac Lab navigation benchmark.
- [ViPlanner](https://github.com/leggedrobotics/viplanner) - Visual semantic local planner for legged robots, with an Isaac Lab extension for evaluation.
- [FDM](https://github.com/leggedrobotics/fdm) - Learned perceptive forward dynamics model for safe legged-robot navigation (RSS 2025).
- [NaVILA-Bench](https://github.com/yang-zj1026/NaVILA-Bench) - Vision-language navigation benchmark for legged robots.
- [WheeledLab](https://github.com/UWRobotLearning/WheeledLab) - Environments, assets and workflows for small wheeled robots, such as drifting (CoRL 2025).
- [LeggedManip_Lab](https://github.com/zzzJie-Robot/LeggedManip_Lab) - Whole-body legged manipulation across seven legged-manipulator platforms, with real-robot transfer.
- [URBAN-SIM](https://github.com/metadriverse/urban-sim) - Large-scale urban simulation for micromobility robot navigation and locomotion (CVPR 2025).
- [VR-Robo](https://github.com/zst1406217/VR-Robo) - Real-to-sim-to-real with Gaussian splatting for visual navigation and locomotion of the Unitree Go2 (RA-L 2025).
- [TIC-VLA](https://github.com/ucla-mobility/TIC-VLA) - Latency-aware VLA model for navigation in dynamic human environments.
- [COMPASS](https://github.com/NVlabs/COMPASS) - NVIDIA cross-embodiment mobility policy built with residual RL and skill synthesis.
- [RAMBO](https://github.com/catachiii/rambo) - RL-augmented model-based whole-body control for quadruped loco-manipulation on the Unitree Go2 (RA-L 2025).
- [REASAN](https://github.com/ASIG-X/REASAN) - Modular learning framework for reactive navigation of legged robots.
- [nav-suite](https://github.com/leggedrobotics/nav-suite) - Unified navigation environments, data sampling, RL terms and benchmarking.
- [sru-navigation-sim](https://github.com/leggedrobotics/sru-navigation-sim) - RL-based long-range mapless navigation with spatially-enhanced recurrent units.
- [OmniNavBench](https://github.com/AutoLab-SAI-SJTU/OmniNavBench) - Unified benchmark for general-purpose navigation across tasks and embodiments (RSS 2026).
- [ReLIC](https://github.com/rai-opensource/relic) - Legged loco-manipulation through flexible interlimb coordination.
- [S2E](https://github.com/VAIL-UCLA/S2E) - Visual navigation foundation models fine-tuned with RL in URBAN-SIM, with a 3DGS navigation benchmark.
- [OASIS](https://github.com/TeleHuman/OASIS) - Simulation data collection with XR teleoperation for humanoid loco-manipulation.
- [locomanipulation-teleop-isaaclab](https://github.com/iit-DLSLab/locomanipulation-teleop-isaaclab) - Teleoperating a Unitree Go2 with an AgileX Piper arm, with sim-to-sim and sim-to-real support.
- [FLUX](https://github.com/Zeying-Gong/FLUX) - Flow-based cross-embodiment navigation policy.
- [AutoMoMa](https://github.com/fi6/automoma) - Whole-body mobile manipulation trajectory generation using cuRobo, Isaac Sim and Isaac Lab.

### Aerial Robots

- [isaac_drone_racer](https://github.com/kousheekc/isaac_drone_racer) - RL framework for high-speed autonomous quadrotor racing.
- [AERO-MPPI](https://github.com/XinChen-stars/AERO_MPPI) - GPU-accelerated MPPI planner for agile mapless quadrotor navigation.
- [MARL Cooperative Aerial Manipulation](https://github.com/Aerial-Manipulation-Lab/MARL_cooperative_aerial_manipulation_ext) - Decentralized multi-drone transport of a cable-suspended load with multi-agent RL.
- [OmniNxtSimulator](https://github.com/UAV-Swarm/tools-OmniNxtSimulator) - Simulator for the OmniNxt aerial robot platform, including synthetic data generation.
- [MasterRacing](https://github.com/MasterDroneRacing/MasterRacing) - RL drone racing on diverse and cluttered tracks.
- [AgileFlight_MultiAgent](https://github.com/Jirl-upenn/AgileFlight_MultiAgent) - Multi-agent competitive quadrotor racing.
- [AM-Bench](https://github.com/ambench/ambench) - Simulation suite and benchmark for aerial manipulation policy learning.
- [rl-vs-gc](https://github.com/PratikKunapuli/rl-vs-gc) - Comparison of RL and geometric control for a 2-DoF aerial manipulator.
- [aerial_lab](https://github.com/ut-dragon-lab/aerial_lab) - Environments for articulated aerial robots.

### Benchmarks and Evaluation

- [RoboVerse](https://github.com/RoboVerseOrg/RoboVerse) - Unified platform, dataset and benchmark for robot learning across simulators (RSS 2025) *(multi-sim)*.
- [RoboDojo](https://github.com/RoboDojo-Benchmark/RoboDojo) - Sim-and-real benchmark for generalist manipulation policies with 42 simulation tasks.
- [inspect-robots](https://github.com/robocurve/inspect-robots) - Evaluation framework for LLM agents and VLA policies on robot benchmarks, with an Isaac Lab plugin *(multi-sim)*.
- [RoboLab](https://github.com/NVlabs/RoboLab) - NVIDIA task-based benchmark with 100+ manipulation tasks and automated success detection (RSS 2026).
- [PolaRiS](https://github.com/arhanjain/polaris) - Scalable real-to-sim evaluations for generalist robot policies.
- [LW-BenchHub](https://github.com/LightwheelAI/LW-BenchHub) - Kitchen manipulation and loco-manipulation benchmark hub built on Isaac Lab-Arena.
- [HumanoidArena](https://github.com/William-wAng618/HumanoidArena) - Humanoid manipulation and whole-body control benchmark with teleoperation pipelines.
- [Ego Humanoid Manipulation Benchmark](https://github.com/quincy-u/Ego_Humanoid_Manipulation_Benchmark) - Humanoid manipulation benchmark used to evaluate EgoVLA.
- [RoboWM-Bench](https://github.com/fffstrong/RoboWM-Bench) - Benchmark for world models in robotic manipulation with Franka and human-hand tasks.

### Other Domains

- [i4h-workflows](https://github.com/isaac-for-healthcare/i4h-workflows) - NVIDIA Isaac for Healthcare reference workflows for healthcare robotics on Isaac Lab-Arena.
- [SonoGym](https://github.com/SonoGym/SonoGym) - Training platform for robotic ultrasound in orthopedic surgical tasks.
- [IsaacLab-HARL](https://github.com/DIRECTLab/IsaacLab-HARL) - Isaac Lab fork adding heterogeneous-agent RL algorithms and multi-agent tasks such as team soccer.
- [MARLadona](https://github.com/leggedrobotics/marladona-isaac-lab) - Multi-agent RL soccer environment for legged robots.
- [SoccerLab](https://github.com/Renforce-Dynamics/soccerLab) - Humanoid soccer from recovery and locomotion to multi-agent skills *(multi-sim)*.
- [Decentralized-Pinch-Lift-Move](https://github.com/osudrl/Decentralized-Pinch-Lift-Move) - Teams of Go2 quadrupeds with arms cooperatively transporting a payload.
- [OceanGym](https://github.com/OceanGPT/OceanGym) - Underwater embodied-agent benchmark with an Isaac Lab port *(multi-sim)*.
- [isaac-auv-env](https://github.com/warplab/isaac-auv-env) - Environment for the WarpAUV/CUREE autonomous underwater vehicle (ICRA 2025).
- [RLRoverLab](https://github.com/abmoRobotics/RLRoverLab) - Rover and space-robotics RL environments.
- [RoboRAN](https://github.com/snt-spacer/RoboRAN-Code) - Unified RL navigation for multiple robot types such as floating platforms.
- [Matterix](https://github.com/AccelerationConsortium/Matterix) - Multi-scale digital twin of robotics-assisted chemistry labs.
- [EmbodiedSWE](https://github.com/EmbodiedSWE/EmbodiedSWE) - Coding-agent simulation data generation and a long-horizon dexterous task benchmark.

## Sim-to-Real and Deployment

- [rl_sar](https://github.com/fan-ziqi/rl_sar) - Simulation verification and real-robot deployment of RL policies for quadruped, wheeled and humanoid robots (ROS/ROS 2, libtorch/ONNX Runtime) *(multi-sim)*.
- [go2_omniverse](https://github.com/abizovnuralem/go2_omniverse) - Unitree Go2 and G1 simulation with a ROS 2 bridge and a real-robot digital-twin mode.
- [PACE](https://github.com/leggedrobotics/pace-sim2real) - Actuator and joint dynamics identification from real data with CMA-ES for legged sim-to-real transfer (IJRR 2026).
- [sim2real-robot-identification](https://github.com/iit-DLSLab/sim2real-robot-identification) - Estimates motor parameters, inertia, mass and center of mass for quadrupeds and manipulators, interfacing with PACE.
- [isaac-go2-ros2](https://github.com/Zhefan-Xu/isaac-go2-ros2) - Unitree Go2 simulation with a ROS 2 interface for testing navigation and autonomy stacks.
- [RoboJuDo](https://github.com/HansZ8/RoboJuDo) - Plug-and-play deployment of humanoid policies from several frameworks, in simulation and on Unitree G1/H1 *(multi-sim)*.
- [unitree_sim_isaaclab](https://github.com/unitreerobotics/unitree_sim_isaaclab) - Unitree robots in task scenes publishing the same DDS topics as the real robots, for data collection and validation.
- [motion_tracking_controller](https://github.com/HybridRobotics/motion_tracking_controller) - C++ ONNX deployment controller on ROS 2 Jazzy for BeyondMimic policies.
- [gentle-humanoid](https://github.com/Axellwppr/gentle-humanoid) - Inference, sim2sim and Unitree G1 deployment for GentleHumanoid policies.
- [Beyondmimic_Deploy_G1](https://github.com/Ming827/Beyondmimic_Deploy_G1) - MuJoCo sim2sim and Unitree G1 deployment scripts for BeyondMimic policies.
- [LEAPP](https://github.com/nvidia-isaac/leapp) - NVIDIA library for exporting multi-stage PyTorch policy pipelines, used in Isaac Lab's deployment guides.
- [LeggedLabDeploy](https://github.com/Hellod035/LeggedLabDeploy) - Runs LeggedLab policies on Unitree G1 and H1 via unitree_sdk2_python.
- [instinct_onboard](https://github.com/project-instinct/instinct_onboard) - ROS 2 onboard ONNX inference for Project Instinct policies on the Unitree G1's Jetson Orin NX.
- [go2_isaac_ros2](https://github.com/CLeARoboticsLab/go2_isaac_ros2) - Joint-level ROS 2 control of a simulated Unitree Go2 that emulates the real robot's interface.
- [go2_parkour_deploy](https://github.com/CAI23sbP/go2_parkour_deploy) - MuJoCo and real-world deployment of Go2 parkour policies.
- [unitree_cpp_deploy](https://github.com/wty-yy/unitree_cpp_deploy) - C++ ONNX deployment on the Unitree Go2 Edu (Orin NX).
- [Deploy_Tienkung](https://github.com/Open-X-Humanoid/Deploy_Tienkung) - ROS 2 control library and SDK for deploying TienKung-Lab policies.
- [g1_deploy_mujoco](https://github.com/RoboCubPilot/g1_deploy_mujoco) - Lightweight MuJoCo sim2sim for Unitree G1 policies, with JIT/ONNX conversion scripts.
- [booster_deploy](https://github.com/BoosterRobotics/booster_deploy) - Runs the same policy code on Booster robots (via ROS 2) and in MuJoCo.
- [Go2_Isaac_ros2](https://github.com/sallu-786/Go2_Isaac_ros2) - Unitree Go2 and Spot simulation with ROS 2 topics for navigation.
- [tron1-rl-deploy-python](https://github.com/limxdynamics/tron1-rl-deploy-python) - Python ONNX deployment for LimX TRON1 in MuJoCo and on the real robot *(multi-sim)*.

## Research Papers with Code

Papers whose public code uses Isaac Lab or Orbit, newest first within each topic.

### Frameworks and Benchmarks

- **RoboLab: A High-Fidelity Simulation Benchmark for Analysis of Task Generalist Policies** (RSS 2026) [[paper]](https://arxiv.org/abs/2604.09860) [[code]](https://github.com/NVlabs/RoboLab)
- **PolaRiS: Scalable Real-to-Sim Evaluations for Generalist Robot Policies** (arXiv 2025) [[paper]](https://arxiv.org/abs/2512.16881) [[code]](https://github.com/arhanjain/polaris)
- **MimicKit: A Reinforcement Learning Framework for Motion Imitation and Control** (arXiv 2025) [[paper]](https://arxiv.org/abs/2510.13794) [[code]](https://github.com/xbpeng/MimicKit)
- **RLinf: Flexible and Efficient Large-scale Reinforcement Learning via Macro-to-Micro Flow Transformation** (OSDI 2026) [[paper]](https://arxiv.org/abs/2509.15965) [[code]](https://github.com/RLinf/RLinf)
- **FastTD3: Simple, Fast, and Capable Reinforcement Learning for Humanoid Control** (arXiv 2025) [[paper]](https://arxiv.org/abs/2505.22642) [[code]](https://github.com/younggyoseo/FastTD3)
- **RoboVerse: Towards a Unified Platform, Dataset and Benchmark for Scalable and Generalizable Robot Learning** (RSS 2025) [[paper]](https://arxiv.org/abs/2504.18904) [[code]](https://github.com/RoboVerseOrg/RoboVerse)

### Locomotion

- **Bridging the Gap: Enabling Soft Actor Critic for High Performance Legged Locomotion** (arXiv 2026) [[paper]](https://arxiv.org/abs/2605.24975) [[code]](https://github.com/leggedrobotics/rsl_rl_sac)
- **LocoTouch: Learning Dynamic Quadrupedal Transport with Tactile Sensing** (arXiv 2025) [[paper]](https://arxiv.org/abs/2505.23175) [[code]](https://github.com/linchangyi1/LocoTouch)
- **Towards Embodiment Scaling Laws in Robot Locomotion** (CoRL 2025) [[paper]](https://arxiv.org/abs/2505.05753) [[code]](https://github.com/BoAi01/embodiment-scaling-laws)
- **TAR: Teacher-Aligned Representations via Contrastive Learning for Quadrupedal Locomotion** (IROS 2025) [[paper]](https://arxiv.org/abs/2503.20839) [[code]](https://github.com/ammousa/TARLoco)
- **CaT: Constraints as Terminations for Legged Locomotion Reinforcement Learning** (IROS 2024) [[paper]](https://arxiv.org/abs/2403.18765) [[code]](https://github.com/Gepetto/constraints-as-terminations)

### Humanoid and Whole-Body

- **Perceptive Behavior Foundation Model: Adapting Human Motion Priors to Robot-Centric Terrain** (arXiv 2026) [[paper]](https://arxiv.org/abs/2606.08059) [[code]](https://github.com/Mondo-Robotics/PMT)
- **Learning Versatile Humanoid Manipulation with Touch Dreaming** (arXiv 2026) [[paper]](https://arxiv.org/abs/2604.13015) [[code]](https://github.com/chrisyrniu/humanoid-touch-dream)
- **AGILE: A Comprehensive Workflow for Humanoid Loco-Manipulation Learning** (arXiv 2026) [[paper]](https://arxiv.org/abs/2603.20147) [[code]](https://github.com/nvidia-isaac/WBC-AGILE)
- **MOSAIC: Bridging the Sim-to-Real Gap in Generalist Humanoid Motion Tracking and Teleoperation with Rapid Residual Adaptation** (arXiv 2026) [[paper]](https://arxiv.org/abs/2602.08594) [[code]](https://github.com/BAAI-Humanoid/MOSAIC)
- **Deep Whole-body Parkour** (arXiv 2026) [[paper]](https://arxiv.org/abs/2601.07701) [[code]](https://github.com/project-instinct/InstinctLab)
- **VIRAL: Visual Sim-to-Real at Scale for Humanoid Loco-Manipulation** (arXiv 2025) [[paper]](https://arxiv.org/abs/2511.15200) [[code]](https://github.com/NVlabs/GR00T-VisualSim2Real)
- **SONIC: Supersizing Motion Tracking for Natural Humanoid Whole-Body Control** (Science Robotics 2026) [[paper]](https://arxiv.org/abs/2511.07820) [[code]](https://github.com/NVlabs/GR00T-WholeBodyControl)
- **Ego-Vision World Model for Humanoid Contact Planning** (arXiv 2025) [[paper]](https://arxiv.org/abs/2510.11682) [[code]](https://github.com/HybridRobotics/Ego-VCP)
- **HDMI: Learning Interactive Humanoid Whole-Body Control from Human Videos** (arXiv 2025) [[paper]](https://arxiv.org/abs/2509.16757) [[code]](https://github.com/LeCAR-Lab/HDMI)
- **DreamControl: Human-Inspired Whole-Body Humanoid Control for Scene Interaction via Guided Diffusion** (arXiv 2025) [[paper]](https://arxiv.org/abs/2509.14353) [[code]](https://github.com/GenRobo/DreamControl)
- **BeyondMimic: From Motion Tracking to Versatile Humanoid Control via Guided Diffusion** (arXiv 2025) [[paper]](https://arxiv.org/abs/2508.08241) [[code]](https://github.com/HybridRobotics/whole_body_tracking)
- **Demonstrating Berkeley Humanoid Lite: An Open-source, Accessible, and Customizable 3D-printed Humanoid Robot** (RSS 2025) [[paper]](https://arxiv.org/abs/2504.17249) [[code]](https://github.com/HybridRobotics/berkeley-humanoid-lite)
- **RAMBO: RL-Augmented Model-Based Whole-Body Control for Loco-Manipulation** (RA-L 2025) [[paper]](https://arxiv.org/abs/2504.06662) [[code]](https://github.com/catachiii/rambo)
- **ASAP: Aligning Simulation and Real-World Physics for Learning Agile Humanoid Whole-Body Skills** (RSS 2025) [[paper]](https://arxiv.org/abs/2502.01143) [[code]](https://github.com/LeCAR-Lab/ASAP)
- **Embrace Collisions: Humanoid Shadowing for Deployable Contact-Agnostics Motions** (arXiv 2025) [[paper]](https://arxiv.org/abs/2502.01465) [[code]](https://github.com/project-instinct/InstinctLab)
- **HOVER: Versatile Neural Whole-Body Controller for Humanoid Robots** (ICRA 2025) [[paper]](https://arxiv.org/abs/2410.21229) [[code]](https://github.com/NVlabs/HOVER)
- **Berkeley Humanoid: A Research Platform for Learning-based Control** (arXiv 2024) [[paper]](https://arxiv.org/abs/2407.21781) [[code]](https://github.com/HybridRobotics/isaac_berkeley_humanoid)

### Manipulation

- **DynamicVLA: A Vision-Language-Action Model for Dynamic Object Manipulation** (arXiv 2026) [[paper]](https://arxiv.org/abs/2601.22153) [[code]](https://github.com/hzxie/DynamicVLA)
- **EgoVLA: Learning Vision-Language-Action Models from Egocentric Human Videos** (arXiv 2025) [[paper]](https://arxiv.org/abs/2507.12440) [[code]](https://github.com/RchalYang/EgoVLA_Release)
- **Real2Render2Real: Scaling Robot Data Without Dynamics Simulation or Robot Hardware** (arXiv 2025) [[paper]](https://arxiv.org/abs/2505.09601) [[code]](https://github.com/uynitsuj/real2render2real)
- **SRSA: Skill Retrieval and Adaptation for Robotic Assembly Tasks** (ICLR 2025) [[paper]](https://arxiv.org/abs/2503.04538) [[code]](https://github.com/NVlabs/SRSA)
- **Re³Sim: Generating High-Fidelity Simulation Data via 3D-Photorealistic Real-to-Sim for Robotic Manipulation** (ICRA 2026) [[paper]](https://arxiv.org/abs/2502.08645) [[code]](https://github.com/InternRobotics/Re3Sim)
- **AnyPlace: Learning Generalized Object Placement for Robot Manipulation** (CoRL 2025) [[paper]](https://arxiv.org/abs/2502.04531) [[code]](https://github.com/ac-rad/anyplace)
- **FORGE: Force-Guided Exploration for Robust Contact-Rich Manipulation under Uncertainty** (arXiv 2024) [[paper]](https://arxiv.org/abs/2408.04587) [[code]](https://github.com/isaac-sim/IsaacLab/tree/main/source/isaaclab_tasks/isaaclab_tasks/direct/forge)
- **AutoMate: Specialist and Generalist Assembly Policies over Diverse Geometries** (arXiv 2024) [[paper]](https://arxiv.org/abs/2407.08028) [[code]](https://github.com/isaac-sim/IsaacLab/tree/main/source/isaaclab_tasks/isaaclab_tasks/direct/automate)
- **Reconciling Reality through Simulation: A Real-to-Sim-to-Real Approach for Robust Manipulation** (arXiv 2024) [[paper]](https://arxiv.org/abs/2403.03949) [[code]](https://github.com/real-to-sim-to-real/RialToPolicyLearning)

### Dexterous

- **Play2Perfect: What Matters in Dexterous Play Pretraining for Precise Assembly?** (arXiv 2026) [[paper]](https://arxiv.org/abs/2606.26428) [[code]](https://github.com/kushal2000/play2perfect)
- **Tabero: Learning Gentle Manipulation with Closed-Loop Force Feedback from Vision, Touch, and Language** (ICML 2026) [[paper]](https://arxiv.org/abs/2605.27886) [[code]](https://github.com/NathanWu7/Tabero)
- **SimToolReal: An Object-Centric Policy for Zero-Shot Dexterous Tool Manipulation** (arXiv 2026) [[paper]](https://arxiv.org/abs/2602.16863) [[code]](https://github.com/tylerlum/simtoolreal)
- **UniVTAC: A Unified Simulation Platform for Visuo-Tactile Manipulation Data Generation, Learning, and Benchmarking** (CoRL 2026) [[paper]](https://arxiv.org/abs/2602.10093) [[code]](https://github.com/univtac/UniVTAC)
- **GraspQP: Differentiable Optimization of Force Closure for Diverse and Robust Dexterous Grasping** (CoRL 2025) [[paper]](https://arxiv.org/abs/2508.15002) [[code]](https://github.com/leggedrobotics/graspqp)
- **DextrAH-RGB: Visuomotor Policies to Grasp Anything with Dexterous Hands** (arXiv 2024) [[paper]](https://arxiv.org/abs/2412.01791) [[code]](https://github.com/NVlabs/DEXTRAH)
- **TacEx: GelSight Tactile Simulation in Isaac Sim -- Combining Soft-Body and Visuotactile Simulators** (arXiv 2024) [[paper]](https://arxiv.org/abs/2411.04776) [[code]](https://github.com/DH-Ng/TacEx)

### Navigation and Mobile Robots

- **Beyond Isolation: A Unified Benchmark for General-Purpose Navigation** (RSS 2026) [[paper]](https://arxiv.org/abs/2605.09441) [[code]](https://github.com/AutoLab-SAI-SJTU/OmniNavBench)
- **TIC-VLA: A Think-in-Control Vision-Language-Action Model for Robot Navigation in Dynamic Environments** (ICML 2026) [[paper]](https://arxiv.org/abs/2602.02459) [[code]](https://github.com/ucla-mobility/TIC-VLA)
- **Spatially-Enhanced Recurrent Memory for Long-Range Mapless Navigation via End-to-End Reinforcement Learning** (arXiv 2025) [[paper]](https://arxiv.org/abs/2506.05997) [[code]](https://github.com/leggedrobotics/sru-navigation-learning)
- **NavDP: Learning Sim-to-Real Navigation Diffusion Policy with Privileged Information Guidance** (arXiv 2025) [[paper]](https://arxiv.org/abs/2505.08712) [[code]](https://github.com/InternRobotics/NavDP)
- **Towards Autonomous Micromobility through Scalable Urban Simulation** (CVPR 2025) [[paper]](https://arxiv.org/abs/2505.00690) [[code]](https://github.com/metadriverse/urban-sim)
- **Learned Perceptive Forward Dynamics Model for Safe and Platform-aware Robotic Navigation** (RSS 2025) [[paper]](https://arxiv.org/abs/2504.19322) [[code]](https://github.com/leggedrobotics/fdm)
- **COMPASS: Cross-embodiment Mobility Policy via Residual RL and Skill Synthesis** (arXiv 2025) [[paper]](https://arxiv.org/abs/2502.16372) [[code]](https://github.com/NVlabs/COMPASS)
- **NaVILA: Legged Robot Vision-Language-Action Model for Navigation** (RSS 2025) [[paper]](https://arxiv.org/abs/2412.04453) [[code]](https://github.com/yang-zj1026/NaVILA-Bench)
- **ViPlanner: Visual Semantic Imperative Learning for Local Navigation** (arXiv 2023) [[paper]](https://arxiv.org/abs/2310.00982) [[code]](https://github.com/leggedrobotics/viplanner)

### Sim-to-Real

- **Towards bridging the gap: Systematic sim-to-real transfer for diverse legged robots** (IJRR 2026) [[paper]](https://arxiv.org/abs/2509.06342) [[code]](https://github.com/leggedrobotics/pace-sim2real)
- **Wheeled Lab: Modern Sim2Real for Low-cost, Open-source Wheeled Robotics** (CoRL 2025) [[paper]](https://arxiv.org/abs/2502.07380) [[code]](https://github.com/UWRobotLearning/WheeledLab)
- **VR-Robo: A Real-to-Sim-to-Real Framework for Visual Robot Navigation and Locomotion** (RA-L 2025) [[paper]](https://arxiv.org/abs/2502.01536) [[code]](https://github.com/zst1406217/VR-Robo)

### Other

- **Robotic World Model: A Neural Network Simulator for Robust Policy Optimization in Robotics** (arXiv 2025) [[paper]](https://arxiv.org/abs/2501.10100) [[code]](https://github.com/leggedrobotics/robotic_world_model)
- **Learning to Swim: Reinforcement Learning for 6-DOF Control of Thruster-driven Autonomous Underwater Vehicles** (ICRA 2025) [[paper]](https://arxiv.org/abs/2410.00120) [[code]](https://github.com/warplab/isaac-auv-env)
- **ORBIT-Surgical: An Open-Simulation Framework for Learning Surgical Augmented Dexterity** (arXiv 2024) [[paper]](https://arxiv.org/abs/2404.16027) [[code]](https://github.com/orbit-surgical/orbit-surgical)

## Historical

Archived or superseded projects, kept for reference when porting older code.

- [IsaacGymEnvs](https://github.com/isaac-sim/IsaacGymEnvs) - RL environments for the preview Isaac Gym simulator (archived).
- [OmniIsaacGymEnvs](https://github.com/isaac-sim/OmniIsaacGymEnvs) - RL environments for Isaac Sim that were merged into Isaac Lab (archived).
- [Isaac Lab Extension Template](https://github.com/isaac-sim/IsaacLabExtensionTemplate) - Former template for external Isaac Lab projects, replaced by the built-in template generator (archived).
- [ORBIT-Surgical](https://github.com/orbit-surgical/orbit-surgical) - Surgical robot learning framework built on Orbit, no longer actively updated.

## Related Lists

- [awesome-isaac-gym](https://github.com/robotlearning123/awesome-isaac-gym) - Resources for Isaac Gym, the predecessor of Isaac Lab.
- [awesome-isaac-sim](https://github.com/sjtuyinjie/awesome-isaac-sim) - Resources for Isaac Sim.
- [awesome-humanoid-robot-learning](https://github.com/YanjieZe/awesome-humanoid-robot-learning) - Papers on humanoid robot learning.
- [Awesome-Robot-Learning](https://github.com/RayYoh/Awesome-Robot-Learning) - Papers on robot learning.
- [mjlab](https://github.com/mujocolab/mjlab) - Not built on Isaac Lab, but reimplements its API on MuJoCo Warp; many projects support both.

## Contributing

Contributions are welcome! Please read the [contributing guide](CONTRIBUTING.md) before opening a pull request.

Maintained by [@Lynn-hh](https://github.com/Lynn-hh).

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the contributors have waived all copyright and related rights to this work.
