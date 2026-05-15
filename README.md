# awesome-domain-adaptation-autonomous-driving

DA-Survey

A curated list of open-source projects related to domain adaptation, cross-domain transfer learning, and generalization for autonomous driving.

This repository collects reproducible resources for autonomous driving tasks, including perception, prediction, planning, policy learning, simulation, and end-to-end driving.

## Contents

- [Perception Tasks](#perception-tasks)
  - [Object Detection](#object-detection)
  - [Semantic Segmentation](#semantic-segmentation)
  - [Depth Estimation](#depth-estimation)
- [Decision-Making Modules](#decision-making-modules)
  - [Behavior Prediction](#behavior-prediction)
  - [Policy Adaptation](#policy-adaptation)
  - [Traffic-Agent Simulation](#traffic-agent-simulation)
  - [Policy Learning and Pre-training](#policy-learning-and-pre-training)
  - [Trajectory Generation](#trajectory-generation)
- [End-to-End Driving](#end-to-end-driving)
  - [Imitation Learning](#imitation-learning)
  - [Reinforcement Learning](#reinforcement-learning)

---

## Perception Tasks

### Object Detection

| Method | Transfer Scenario | Metric | Performance | Improvement | Code |
|---|---|---|---:|---:|---|
| MemX-Former | Cityscapes → Foggy Cityscapes | mAP ↑ | 37.70 | +12.50 | [GitHub](https://github.com/Vibashan/online-da) |
| DA-Detect | Cityscapes → Foggy Cityscapes | mAP ↑ | 42.40 | +18.93 | [GitHub](https://github.com/jinlong17/DA-Detect) |
| Zhang et al., 2023 | Scenes100 | mAP ↑ | 70.39 | +4.65 | [GitHub](https://github.com/cvlab-stonybrook/scenes100) |
| DA-Pro | Cityscapes → Foggy Cityscapes | mAP ↑ | 55.90 | +3.30 | [GitHub](https://github.com/Therock90421/DA-Pro) |
| AT | Cityscapes → Foggy Cityscapes | mAP ↑ | 50.90 | +8.20 | [GitHub](https://github.com/facebookresearch/adaptive_teacher) |
| 2PCNet | BDD100K day → night | mAP ↑ | 46.40 | +5.30 | [GitHub](https://github.com/mecarill/2pcnet) |
| HT | Cityscapes → Foggy Cityscapes | mAP ↑ | 50.40 | +15.00 | [GitHub](https://github.com/kinredon/Harmonious-Teacher) |
| BlenDA | Cityscapes → Foggy Cityscapes | mAP ↑ | 53.40 | +6.30 | [GitHub](https://github.com/aiiu-lab/BlenDA) |
| DATR | Cityscapes → Foggy Cityscapes | mAP ↑ | 52.80 | +17.20 | [GitHub](https://github.com/h751410234/DATR) |
| ALDI++ | Cityscapes → Foggy Cityscapes | mAP ↑ | 66.80 | +3.50 | [GitHub](https://github.com/justinkay/aldi) |
| DA2OD | Cityscapes → Foggy Cityscapes | mAP ↑ | 57.30 | +5.20 | [GitHub](https://github.com/EstrellaXyu/Differential-Alignment-for-DAOD) |
| DINO Teacher | Cityscapes → Foggy Cityscapes | mAP ↑ | 55.40 | +4.50 | [GitHub](https://github.com/TRAILab/DINO_Teacher) |

### Semantic Segmentation

| Method | Transfer Scenario | Metric | Performance | Improvement | Code |
|---|---|---|---:|---:|---|
| CDAC | GTA5 → Cityscapes | mIoU ↑ | 75.30 | +28.80 | [GitHub](https://github.com/wangkaihong/CDAC) |
| CDMA | Cityscapes → Dark Zurich | mIoU ↑ | 54.80 | +1.30 | [GitHub](https://github.com/XiaRho/CMDA) |
| SePiCo | GTA5 → Cityscapes | mIoU ↑ | 69.70 | +1.40 | [GitHub](https://github.com/BIT-DA/SePiCo) |
| BUS | GTA5 → Cityscapes | mIoU ↑ | 72.47 | +14.30 | [GitHub](https://github.com/KU-VGI/BUS) |
| MIC | GTA5 → Cityscapes | mIoU ↑ | 75.90 | +7.60 | [GitHub](https://github.com/lhoyer/MIC) |
| DTA4PASS | Cityscapes, SynPASS → DensePASS | mIoU ↑ | 57.16 | +4.77 | [GitHub](https://github.com/jingjiang02/dta4pass) |
| FSDA | GTA5 → Cityscapes, 1-shot | mIoU ↑ | 33.80 | +12.00 | [GitHub](https://github.com/zgyang-hnu/DIP-hunnu) |
| VFM-UDA++ | GTA5 → Cityscapes | mIoU ↑ | 79.80 | +1.40 | [GitHub](https://github.com/tue-mps/vfm-uda-plusplus) |
| SoMA | GTAV → Cityscapes, BDD, Mapillary | mIoU ↑ | 68.27 | +1.77 | [GitHub](https://github.com/ysj9909/SoMA) |

### Depth Estimation

| Method | Transfer Scenario | Metric | Performance | Improvement | Code |
|---|---|---|---:|---:|---|
| Ada-Depth | KITTI → DDAD | δ < 1.25 ↑ | 0.867 | +0.079 | [GitHub](https://github.com/Malefikus/ada-depth) |
| ZoeDepth | KITTI → Virtual KITTI 2 | δ < 1.25 ↑ | 0.837 | +0.008 | [GitHub](https://github.com/isl-org/ZoeDepth) |
| ZeroDepth | Waymo et al. → KITTI | δ < 1.25 ↑ | 0.910 | +0.047 | [GitHub](https://github.com/TRI-ML/vidar) |
| Metric3D v2 | ScanNet et al. → KITTI | δ < 1.25 ↑ | 0.975 | +0.050 | [GitHub](https://github.com/YvanYin/Metric3D) |
| ACDepth | nuScenes day-clear → day-rain | δ < 1.25 ↑ | 0.813 | +0.003 | [GitHub](https://github.com/msscao/ACDepth) |
| Video Depth Anything | Virtual KITTI 2, IRS → KITTI | δ < 1.25 ↑ | 0.910 | +0.033 | [GitHub](https://github.com/DepthAnything/Video-Depth-Anything) |

---

## Decision-Making Modules

### Behavior Prediction

| Method | Transfer Scenario | Metric | Performance | Improvement | Code |
|---|---|---|---:|---:|---|
| T4P | INTER → nuScenes | ADE/FDE ↓ | 0.54 / 1.14 | -0.51 / -1.11 | [GitHub](https://github.com/daeheepark/T4P) |
| TrajSDE | WOMD + nuScenes → nuScenes | ADE/FDE ↓ | 0.893 / -- | -0.151 / -- | [GitHub](https://github.com/daeheepark/TrajSDE) |
| MTR-UniTraj | WOMD + Argoverse 2 + nuScenes → nuScenes | ADE/FDE ↓ | -- / 2.27 | -- / -0.59 | [GitHub](https://github.com/vita-epfl/UniTraj) |
| STraj | Argoverse MIA → PIT | ADE/FDE ↓ | 1.96 / 4.45 | -0.36 / -1.01 | [GitHub](https://github.com/Zhanwei-Z/STraj) |
| Frenet+ | Argoverse seen domains → unseen domains | ADE/FDE ↓ | 0.7882 / 1.2602 | -0.0713 / -0.1234 | [GitHub](https://github.com/XIAOYEJIAYOU/Frenet-Strategy) |
| EP-Q | Argoverse 2 → WOMD | ADE/FDE ↓ | 0.53 / 1.14 | -- | [GitHub](https://github.com/continental/everything-polynomial) |

### Policy Adaptation

| Method | Transfer Scenario | Metric | Performance | Improvement | Code |
|---|---|---|---:|---:|---|
| LoRD | nuPlan Boston/Pittsburgh → Singapore | OOD CL-R ↑ | 0.764 | +0.069 | [GitHub](https://github.com/rst-tu-dortmund/LoRD) |

### Traffic-Agent Simulation

| Method | Transfer Scenario | Metric | Performance | Improvement | Code |
|---|---|---|---:|---:|---|
| SMART | nuPlan → WOMD | RMM ↑ | 0.7210 | -- | [GitHub](https://github.com/rainmaker22/SMART) |

### Traffic-Agent Policy Adaptation

| Method | Transfer Scenario | Metric | Performance | Improvement | Code |
|---|---|---|---:|---:|---|
| CAT-K | Open-loop BC → Closed-loop WOSAC | RMM ↑ | 0.7702 | +0.0111 | [GitHub](https://github.com/NVlabs/catk) |

### Policy Learning and Pre-training

| Method | Transfer Scenario | Metric | Performance | Improvement | Code |
|---|---|---|---:|---:|---|
| AnyD | Multi-city driving data → CARLA regional benchmark | Driving Score ↑ | 0.50 | +0.14 | [GitHub](https://github.com/h2xlab/anyd) |
| PPGeo | YouTube Videos → CARLA Town05-long | Driving Score ↑ | 47.44 ± 5.63 | +6.15 | [GitHub](https://github.com/OpenDriveLab/PPGeo) |
| ACO | YouTube Videos → CARLA Town02/test weather | Success Rate ↑ | 96.0 ± 3.3 | +5.3 | [GitHub](https://github.com/metadriverse/ACO) |

### Trajectory Generation

| Method | Transfer Scenario | Metric | Performance | Improvement | Code |
|---|---|---|---:|---:|---|
| DG-TrajGen | RobotCar → KITTI/CARLA | ADE ↓ | 1.70 / 0.92 | -0.43 / -0.44 | [GitHub](https://github.com/IamWangYunKai/DG-TrajGen) |

---

## End-to-End Driving

### Imitation Learning

| Method | Transfer Scenario | Metric | Performance | Improvement | Code |
|---|---|---|---:|---:|---|
| ACO | YouTube Driving → CARLA Town02 | Success Rate ↑ | 96.0 ± 3.3 | +5.3 | [GitHub](https://github.com/metadriverse/ACO) |
| PPGeo | YouTube Driving → CARLA Town05 | Driving Score ↑ | 47.44 ± 5.63 | +6.15 | [GitHub](https://github.com/OpenDriveLab/PPGeo) |
| AnyD | AV2 + nuScenes + Waymo → CARLA Town01/02/10 | Driving Score ↑ | 0.50 | +0.14 | [GitHub](https://github.com/h2xlab/anyd) |
| KING | CARLA Town01--06 → KING | Collision Rate ↓ | 28.57 ± 0.00 | -28.57 | [GitHub](https://github.com/autonomousvision/king) |
| CodeMerge | nuScenes → nuScenes-C | Avg. L2 Error ↓ | 0.7266 | -0.0657 | [GitHub](https://github.com/UQHTy/CodeMerge) |
| RAP-DiffusionDrive | OpenScene → NAVSIM | Planning Score ↑ | 89.2 | +3.2 | [GitHub](https://github.com/vita-epfl/RAP) |

### Reinforcement Learning

| Method | Transfer Scenario | Metric | Performance | Improvement | Code |
|---|---|---|---:|---:|---|
| Sim2Seg | Unity → Arroyo | L2 Error ↓ | 0.287 ± 0.024 | -0.165 | [GitHub](https://github.com/rll-research/sim2seg) |
| CAT | WOMD → safety-critical WOMD | Crash Rate ↓ | 28.15% ± 1.63% | -15.18% | [GitHub](https://github.com/metadriverse/cat) |

---

## Notes

- `↑` means higher is better.
- `↓` means lower is better.
- `--` means the value is not explicitly reported or not applicable in the collected table.
- Some repositories may appear in more than one section because they are related to both decision-making modules and end-to-end driving.

## Contribution

Contributions are welcome. If you find a missing paper, code repository, benchmark, or incorrect entry, please open an issue or submit a pull request.

## License

This repository is intended for academic and research use. Please refer to the license of each linked project before using its code or data.
