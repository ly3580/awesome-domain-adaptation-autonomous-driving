# awesome-domain-adaptation-autonomous-driving

DA-Survey

A curated list of benchmarks, task suites, open-source implementations, and reproducibility resources for domain adaptation, cross-domain transfer learning, and generalization in autonomous driving.

This repository focuses on autonomous driving scenarios, including perception, prediction, planning, policy learning, traffic-agent modeling, and end-to-end driving.

---

## Contents

- [Benchmarks and Task Suites](#benchmarks-and-task-suites)
- [Open-Source Implementations](#open-source-implementations)
  - [Perception Tasks](#perception-tasks)
    - [Object Detection](#object-detection)
    - [Semantic Segmentation](#semantic-segmentation)
    - [Depth Estimation](#depth-estimation)
  - [Decision-Making Modules](#decision-making-modules)
    - [Behavior Prediction](#behavior-prediction)
    - [Policy Learning and Adaptation](#policy-learning-and-adaptation)
    - [Traffic-Agent Modeling](#traffic-agent-modeling)
    - [Trajectory Generation](#trajectory-generation)
  - [End-to-End Driving](#end-to-end-driving)
    - [Imitation Learning](#imitation-learning)
    - [Reinforcement Learning](#reinforcement-learning)
- [Notes](#notes)
- [Contribution](#contribution)
- [License](#license)

---

## Benchmarks and Task Suites

| Dataset / Suite | Year / Source | Main Tasks | Typical Scale | Modality | Link |
|---|---:|---|---|---|---|
| KITTI | 2012, KIT | Stereo, Flow, 3D Det. | 150k imgs | Multi-sensor | [Link](https://www.cvlibs.net/datasets/kitti/) |
| GTA5 | 2016, RWTH | Syn→Real Seg. | 24,966 imgs | RGB | [Link](https://github.com/sarrrrry/PyTorchDL_GTA5) |
| Stanford Drone | 2016, Stanford CVGL | Traj. Pred. | 60 scenes | Aerial RGB | [Link](https://cvgl.stanford.edu/projects/uav_data/) |
| Cityscapes | 2016, TU Darmstadt | Sem. Seg., Det. | 5k fine / 20k coarse imgs | RGB, stereo | [Link](https://www.cityscapes-dataset.com) |
| Foggy Cityscapes | 2018, ETH Zürich | Seg. (fog) | 550 fine / 25k imgs | RGB + depth | [Link](https://people.ee.ethz.ch/~csakarid/SFSU_synthetic/) |
| BDD100K | 2018, BAIR | Sem. Seg., Det. | 100k sequences | Multi-sensor | [Link](https://bair.berkeley.edu/blog/2018/05/30/bdd/) |
| Dark Zurich | 2019, ETH Zürich | Night Seg. | 8,779 imgs | RGB | [Link](https://www.trace.ethz.ch/publications/2019/GCMA_UIoU/) |
| nuScenes | 2020, Motional | 3D Det., Pred. | 1,000 scenes / 1.4M imgs | Full AV sensor | [Link](https://www.nuscenes.org/nuscenes) |
| Virtual KITTI 2 | 2020, Naver Labs | Syn Multi-task | 21.26k stereo pairs | RGB, depth, flow | [Link](https://europe.naverlabs.com/proxy-virtual-worlds-vkitti-2/) |
| WildPASS | 2021, KIT | Panor. Sem. Seg. in the Wild | 500 labeled + 2k unlabeled images | RGB-pano | [Link](https://github.com/elnino9ykl/WildPASS) |
| DensePASS | 2021, KIT | 360° Panor. Seg. | 100 labeled / 2k unlabeled images | RGB-pano | [Link](https://github.com/chma1024/DensePASS) |
| DDAD | 2021, TRI | Dense Depth | 200 scenes / 16,600 frames | RGB, LiDAR | [Link](https://github.com/TRI-ML/DDAD) |
| Waymo Open Motion | 2021, Waymo | Motion Forec. | 103,354 scenes | LiDAR, RGB, HD-map | [Link](https://github.com/waymo-research/waymo-open-dataset) |
| RCooper | 2024, AIR-THU | Coop. Percep., Det., Tracking | 50k imgs / 30k pts | RGB, LiDAR | [Link](https://github.com/AIR-THU/DAIR-RCooper) |
| V2X-Real | 2024, UCLA | V2X Coop. Percep., 3D Det. | 171k imgs / 33k LiDAR | RGB, LiDAR | [Link](https://mobility-lab.seas.ucla.edu/v2x-real/) |
| Multi-V2X | 2024, THU | Multi-agent V2X Percep. | 549k imgs / 146k LiDAR | RGB, LiDAR, HD-map | [Link](https://github.com/RadetzkyLi/Multi-V2X) |
| V2X-Radar | 2024, THU | V2X 4D Radar Percep. | 40k imgs / 20k radar frames | Multi-sensor | [Link](http://openmpd.com/column/V2X-Radar) |
| OpenAD | 2024, PKU | Open-world 3D Det. | 2k scenes / 206 classes | RGB, LiDAR | [Link](https://github.com/VDIGPKU/OpenAD) |
| OmniHD-Scenes | 2024, Tongji | 3D Det., Occ. Pred. | 450k+ frames / 514k boxes | Multi-sensor | [Link](https://github.com/TJRadarLab/OmniHD-Scenes) |
| UrbanV2X | 2025, PolyU | Coop. Nav., V2X Percep. | 81 seqs / 200 km+ | Multi-sensor | [Link](https://polyu-taslab.github.io/UrbanV2X/) |
| UrbanIng-V2X | 2025, THI | Coop. Percep., Tracking, Pred. | 34 seqs / 712k inst. | Multi-sensor | [Link](https://github.com/thi-ad/UrbanIng-V2X) |
| ADAS-TO | 2026, USF | Takeover Pred., Safety | 15.7k clips / 327 drivers | RGB, CAN | [Link](https://huggingface.co/datasets/HenryYHW/ADAS-TO) |
| BATON | 2026, USF | Handover Pred., Takeover Pred. | 380 routes / 136.6 h | Multi-sensor | [Link](https://github.com/OpenLKA/BATON) |
| ORAD-3D | 2026, ICT | Free-space, Occ., Planning | 350 GB / 5 tasks | RGB, LiDAR | [Link](https://github.com/chaytonmin/ORAD-3D-Dataset-For-Off-Road-AD) |
| HetroD | 2026, NYCU | Forecast., Planning, Sim. | 65.4k traj. / 70% VRUs | Aerial RGB, HD-map | [Link](https://hetroddata.github.io/HetroD/) |
| StyleDrive | 2026, AIR-THU | E2E Driving, Style Cond. | 30k scenes / 11 types | BEV, HD-map, traj. | [Link](https://styledrive.github.io/) |

---

## Open-Source Implementations

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
| T4P | INTERACTION → nuScenes | ADE/FDE ↓ | 0.54 / 1.14 | -0.51 / -1.11 | [GitHub](https://github.com/daeheepark/T4P) |
| TrajSDE | nuScenes + WOMD → nuScenes | ADE/FDE ↓ | 0.893 / -- | -0.151 / -- | [GitHub](https://github.com/daeheepark/TrajSDE) |
| STraj | Argoverse MIA → PIT | ADE/FDE ↓ | 1.96 / 4.45 | -0.36 / -1.01 | [GitHub](https://github.com/Zhanwei-Z/STraj) |
| Frenet+ | Argoverse seen domains → unseen domains | ADE/FDE ↓ | 0.7882 / 1.2602 | -0.0713 / -0.1234 | [GitHub](https://github.com/XIAOYEJIAYOU/Frenet-Strategy) |
| EP-Q | Argoverse 2 → WOMD | ADE/FDE ↓ | 0.530 / 1.150 | -- | [GitHub](https://github.com/continental/everything-polynomial) |
| MTR-UniTraj | WOMD + Argoverse 2 + nuScenes → nuScenes | brier-minFDE ↓ | 2.27 | -0.59 | [GitHub](https://github.com/vita-epfl/UniTraj) |

### Policy Learning and Adaptation

| Method | Transfer Scenario | Metric | Performance | Improvement | Code |
|---|---|---|---:|---:|---|
| LoRD | nuPlan Boston/Pittsburgh → Singapore | Score / Success ↑ | 0.764 | +0.062 | [GitHub](https://github.com/rst-tu-dortmund/LoRD) |
| AnyD | Multi-city driving data → CARLA regional benchmark | Driving Score ↑ | 0.50 | +0.14 | [GitHub](https://github.com/h2xlab/anyd) |
| PPGeo | YouTube Driving → CARLA Town05-long | Driving Score ↑ | 47.44 ± 5.63 | +6.15 | [GitHub](https://github.com/OpenDriveLab/PPGeo) |
| ACO | YouTube Driving → CARLA IL benchmark | Success Rate ↑ | 96.0 ± 3.3 | +5.3 | [GitHub](https://github.com/metadriverse/ACO) |

### Traffic-Agent Modeling

| Method | Transfer Scenario | Metric | Performance | Improvement | Code |
|---|---|---|---:|---:|---|
| SMART | nuPlan → WOMD | RMM ↑ | 0.7210 | -- | [GitHub](https://github.com/rainmaker22/SMART) |
| CAT-K | Open-loop BC → Closed-loop WOSAC | RMM ↑ | 0.7702 | +0.0031 | [GitHub](https://github.com/NVlabs/catk) |

### Trajectory Generation

| Method | Transfer Scenario | Metric | Performance | Improvement | Code |
|---|---|---|---:|---:|---|
| DG-TrajGen | RobotCar → KITTI/CARLA | ADE_KITTI/CARLA ↓ | 1.70 / 0.92 | -0.43 / -0.44 | [GitHub](https://github.com/IamWangYunKai/DG-TrajGen) |

---

## End-to-End Driving

### Imitation Learning

| Method | Transfer Scenario | Metric | Performance | Improvement | Code |
|---|---|---|---:|---:|---|
| ACO | YouTube Driving → CARLA Town02 | Success Rate ↑ | 96.0 ± 3.3 | +5.3 | [GitHub](https://github.com/metadriverse/ACO) |
| PPGeo | YouTube Driving → CARLA Town05-long | Driving Score ↑ | 47.44 ± 5.63 | +6.15 | [GitHub](https://github.com/OpenDriveLab/PPGeo) |
| AnyD | AV2 + nuScenes + Waymo → CARLA Town01/02/10 | Driving Score ↑ | 0.50 | +0.14 | [GitHub](https://github.com/h2xlab/anyd) |
| KING | CARLA Town01--06 → KING | Collision Rate ↓ | 28.57 ± 0.00 | -28.57 | [GitHub](https://github.com/autonomousvision/king) |
| CodeMerge | nuScenes → nuScenes-C | Avg. L2 Error ↓ | 0.7266 | -0.0657 | [GitHub](https://github.com/UQHTy/CodeMerge) |
| RAP-DiffusionDrive | OpenScene raster → NAVSIM v1 | Planning Score ↑ | 89.2 | +3.2 | [GitHub](https://github.com/vita-epfl/RAP) |

### Reinforcement Learning

| Method | Transfer Scenario | Metric | Performance | Improvement | Code |
|---|---|---|---:|---:|---|
| Sim2Seg | Unity sim. → Arroyo Seco | L2 Error ↓ | 0.287 ± 0.024 | -0.165 | [GitHub](https://github.com/rll-research/sim2seg) |
| CAT | WOMD logs → safety-critical WOMD | Crash Rate ↓ | 28.15% ± 1.63% | -15.18% | [GitHub](https://github.com/metadriverse/cat) |
| RAD | 3DGS train → unseen 3DGS | Collision Ratio ↓ | 0.089 | -0.140 | [GitHub](https://github.com/hustvl/RAD) |

---

## Notes

- `↑` means higher is better.
- `↓` means lower is better.
- `--` means the value is not explicitly reported or not applicable in the collected table.
- `Syn→Real` denotes synthetic-to-real transfer.
- `Sem. Seg.` denotes semantic segmentation.
- `Det.` denotes detection.
- `Pred.` denotes prediction.
- `Traj.` denotes trajectory.
- Some repositories may appear in more than one section because they are related to both modular decision-making and end-to-end driving.
- The reported numbers follow the corresponding papers or collected tables. Please refer to the original papers and repositories for detailed experimental settings.

---

## Contribution

Contributions are welcome.

If you find a missing paper, code repository, benchmark, or incorrect entry, please open an issue or submit a pull request. Suggested information includes:

- Paper or method name
- Task category
- Transfer scenario
- Evaluation metric
- Reported performance
- Code repository
- Dataset or benchmark link

---

## License

This repository is intended for academic and research use.

Please refer to the license of each linked project before using its code, dataset, model, or benchmark.
