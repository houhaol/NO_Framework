# An Automated Multimodal Framework for Capturing Dynamic and Micro-scale Interactions between the Built Environment and Vulnerable Older Adults

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## Overview

This repository contains the implementation of an automated multimodal framework designed to capture and analyze dynamic, micro-scale interactions between the built environment and vulnerable older adults. The framework integrates multiple data streams including trajectory tracking, environmental attributes, gaze patterns, and physiological signals to provide comprehensive insights into how older adults interact with their physical surroundings.

### Key Features

- **Real-time Trajectory Tracking**: SLAM-based localization and mapping for continuous spatial positioning
- **Walkway Analysis**: Automated identification and attribute extraction of environmental features
- **Gaze-based Object Recognition**: Fixation-guided analysis of visual attention and environmental elements
- **Physiological Monitoring**: Multi-signal processing including heart rate variability, electrodermal activity, and gait parameters

## Framework Architecture

The framework consists of four main integrated modules:

```
┌─────────────────────────────────────────────────────────────┐
│                    Multimodal Framework                      │
├─────────────────┬─────────────────┬─────────────────────────┤
│   Trajectory    │    Walkway      │   Gaze & Physiology     │
│   (SLAM)        │   (Vision)      │   (Sensors)             │
└─────────────────┴─────────────────┴─────────────────────────┘
```

## Repository Structure

```
NO_Framework/
├── Trajectory/          # SLAM-based trajectory estimation
├── Walkway/            # Environmental attribute analysis
├── Gaze/               # Fixation-guided object recognition
├── Physiology/         # Physiological signal processing
└── README.md           # This file
```

## Modules

### 1. SLAM Trajectory (`/Trajectory`)

Implements real-time visual-inertial SLAM for accurate 6-DOF pose estimation and trajectory tracking of participants in the built environment.

**Features:**
- Visual-inertial odometry fusion
- Loop closure detection
- Global trajectory optimization
- GoPro camera calibration and setup

**Key Components:**
- `vins_estimator/`: Core SLAM estimation algorithms
- `loop_fusion/`: Loop closure and global optimization
- `global_fusion/`: Multi-sensor fusion framework
- `camera_models/`: Camera calibration models
- `gopro_calibration_vins_setup/`: GoPro-specific configurations

[📖 See detailed documentation](./Trajectory/README.md)

---

### 2. Walkway Identification and Attribute Analysis (`/Walkway`)

Automatically identifies and analyzes environmental attributes including walkway surfaces, materials, obstacles, and accessibility features.

**Features:**
- Material classification using deep learning
- Pose estimation for obstacle detection
- Walkway segmentation and characterization
- Environmental hazard identification

**Key Components:**
- `scripts/`: Processing pipelines for walkway analysis
- `materials/`: Material classification datasets and models
- `openpose-docker/`: Human pose estimation integration
- `utilis/`: Utility functions for data processing

[📖 See detailed documentation](./Walkway/README.md)

---

### 3. Fixation-Guided Object Recognition (`/Gaze`)

Analyzes eye-tracking data to identify fixation points and recognize objects of interest in the participant's visual field, providing insights into attention patterns and environmental engagement.

**Features:**
- Fixation detection and classification
- SAM-based object segmentation at fixation points
- CLIP-based object recognition
- Temporal gaze pattern analysis

**Key Components:**
- `scripts/`: Main inference and processing scripts
- `config/`: Configuration files for models and parameters
- `eval/`: Evaluation metrics and analysis tools
- `alternative_infer_scripts/`: Alternative processing pipelines

[📖 See detailed documentation](./Gaze/README.md)

---

### 4. Physiological Signal Processing (`/Physiology`)

Processes and analyzes multimodal physiological signals including heart rate variability (HRV), electrodermal activity (EDA), gait parameters, and their synchronization with spatial and environmental data.

**Features:**
- Heart rate variability analysis
- Electrodermal activity processing
- Gait parameter extraction
- Multi-signal temporal alignment
- Cross-modal data fusion

**Key Components:**
- `hrv/`: Heart rate variability analysis
- `eda/`: Electrodermal activity processing
- `gait/`: Gait parameter extraction and analysis
- `gaze/`: Gaze-physiology integration
- `traj/`: Trajectory-physiology synchronization
- `walkway/`: Environment-physiology correlation
- `utils/`: Common processing utilities
- `segments_inspect_vis_tools/`: Visualization tools

[📖 See detailed documentation](./Physiology/README.md)

---

## Installation

### Prerequisites

- Ubuntu 18.04/20.04 or later
- Python 3.8+
- CUDA 11.0+ (for GPU acceleration)
- Docker (optional, for containerized deployment)

### Quick Start

1. Clone the repository with submodules:
```bash
git clone --recursive https://github.com/yourusername/NO_Framework.git
cd NO_Framework
```

2. Set up each module (refer to individual module READMEs for detailed instructions):

```bash
# Trajectory module
cd Trajectory && ./setup.sh && cd ..

# Walkway module
cd Walkway && pip install -r requirements.txt && cd ..

# Gaze module
cd Gaze && pip install -r requirements.txt && cd ..

# Physiology module
cd Physiology && pip install -r requirements.txt && cd ..
```


### Individual Module Usage

Each module can be run independently. Please refer to the respective README files in each subdirectory for detailed usage instructions.


## Citation

If you use this framework in your research, please cite:

```bibtex
@article{yourname2025framework,
  title={An Automated Multimodal Framework for Capturing Dynamic and Micro-scale Interactions between the Built Environment and Vulnerable Older Adults},
  author={Your Name and Co-authors},
  journal={Journal Name},
  year={2025}
}
```

## Related Work

This framework was developed as part of the **BE-FIT (Built Environment in Falls and ArthrITis Study)** study, investigating how environmental factors influence mobility and independence in older adults with knee OA or fall history.

**Status**: 🚧 Active Development | Last Updated: December 2025