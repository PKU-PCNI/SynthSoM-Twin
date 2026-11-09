# SynthSoM-Twin

SynthSoM-Twin is a framework for generating a multi-modal sensing-communication digital-twin dataset and studying Sim2Real transfer across wireless communication scenarios.

## 📌 Overview

Based on the construction architecture of the SynthSoM dataset, the SynthSoM-Twin dataset further completes the digital twin reconstruction of real-world scenarios in DeepSense 6G, achieving spatio-temporal consistency between the physical world and the simulation environment. The dataset covers two typical V2I scenarios, including urban and suburban scenarios. Data acquisition and construction comprehensively consider three types of scenario conditions: multi-frequency bands, multi-perspectives, and multi-vehicle traffic densities.

The reconstructed digital-twin scenarios include two components: static scenes and dynamic objects. Real 3D reconstruction models are used to restore static scenes, while multi-modal detection and tracking algorithms are used to restore dynamic object types and trajectories. The constructed SynthSoM-Twin dataset contains 70,000 synchronized RGB images, 70,000 depth maps, 70,000 LiDAR point clouds, 20,000 millimeter-wave radar point clouds, and 70,000 large- and small-scale channel-fading samples. Experimental results show that injecting less than 15% of real-world data can balance model performance and real-world data cost, indicating that a suitable digital-twin dataset can reduce measurement costs by an average of 85%.

![SynthSoM-Twin dataset overview](https://cdn-uploads.huggingface.co/production/uploads/69cf2558a553c0a282fcdce9/_IpJvUXbxJ8NyFUSS48gY.png)

## Repository Structure

~~~text
SynthSoM-Twin/
├── code/
│   ├── data_processing/
│   ├── models/
│   ├── inference/
│   ├── visualization/
│   └── utils/
├── dataset/
└── README.md
~~~

The repository contains the inference-oriented code structure and dataset documentation. Large dataset files are distributed through the permanent Baidu Netdisk links documented in [dataset/README.md](dataset/README.md).

## Main Tasks

The project covers three cross-modal generation and transfer tasks:

- Path-loss generation.
- Beam-power generation.
- Beam tracking.

The inference workflows include direct inference, zero-shot transfer, and inference after adapting a model with target-scenario real-world data.

## Dataset Release

The dataset is organized into three DeepSense 6G V2I scenario settings:

- `suburban_daytime` (SC31)
- `urban_daytime` (SC32)
- `urban_nighttime` (SC33)

The download links, extraction codes, and directory layout are listed in [dataset/README.md](dataset/README.md). The GitHub repository stores documentation and code; large raw data files remain on Baidu Netdisk.

## Model Releases

The model release is organized into four model families and three generation tasks, giving 12 model-task directories.

~~~text
models/
├── cnn/
│   ├── path_loss/
│   ├── beam_power/
│   └── beam_tracking/
├── lstm/
│   ├── path_loss/
│   ├── beam_power/
│   └── beam_tracking/
├── mlp/
│   ├── path_loss/
│   ├── beam_power/
│   └── beam_tracking/
└── transformer/
    ├── path_loss/
    ├── beam_power/
    └── beam_tracking/
~~~

The permanent model-directory links, extraction codes, and local placement paths are listed in [models/README.md](models/README.md).

## Code Modules

- `data_processing/`: Scenario-specific data preparation, split construction, and shared data utilities.
- `models/`: Model definitions for path-loss generation, beam-power generation, beam tracking, CMGMs, and baseline methods.
- `inference/`: Inference entry points for the three tasks and zero-shot transfer.
- `visualization/`: Plotting scripts for inference outputs and Sim2Real transfer results.
- `utils/`: Shared file, seed, and checkpoint utilities.

## Getting Started

Configure the inference scripts under `code/inference/` with the corresponding local dataset path. Follow the directory layout in `dataset/raw/` when placing downloaded scene data.

## Reproducibility

Inference configurations, model checkpoints, random seeds, input data descriptions, and figure-generation scripts are documented with the relevant modules.

## 📜 Citation

J. Chen, Z. Huang, X. Cai, X. Cheng, and L. Yang, “SynthSoM-Twin: A Framework to Generate Multi-Modal Sensing-Communication Digital-Twin Dataset for Sim2Real Transfer,” IEEE Transactions on Machine Learning in Communications and Networking, accepted for publication, Nov. 5, 2026.

## License

The license and dataset usage terms are specified in the project documentation.
