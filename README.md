# An Automated Multimodal Framework for Capturing Dynamic and Micro-scale Interactions between the Built Environment and Vulnerable Older Adults

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## Overview

This repository provides the open-source computational pipelines for our framework designed to capture and analyze dynamic, micro-scale interactions between vulnerable older adults and the built environment (BE).
The framework processes four primary data streams:
- **Real-time Trajectory Tracking**: SLAM-based localization and mapping for continuous spatial positioning
- **Walkway Analysis**: Automated identification and attribute extraction of walkway materials and width
- **Gaze-based Object Recognition**: Fixation-guided analysis of visual attention and environmental elements
- **Physiological Monitoring**: Multi-signal processing including heart rate variability and electrodermal activity

This study has been accepted by Building and Environment. Read the full paper here: https://doi.org/10.1016/j.buildenv.2026.114754

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

Implements real-time visual-inertial SLAM for trajectory tracking of participants in the BE.

**Features:**
- Visual-inertial odometry fusion
- GoPro 13 camera calibration and setup

[📖 See detailed documentation](./Trajectory/README.md)

---

### 2. Walkway Identification and Attribute Analysis (`/Walkway`)

Automatically identifies and analyzes walkway attributes including walkway surfaces materials and width.

**Features:**
- Material classification using deep learning
- Material dataset for walkway surfaces
- Walkway width estimation

**Key Components:**
- `scripts/`: Processing pipelines for walkway analysis
- `materials/`: Material classification datasets and models

[📖 See detailed documentation](./Walkway/README.md)

---

### 3. Fixation-Guided Object Recognition (`/Gaze`)

Analyzes eye-tracking data to identify fixation points and recognize objects of interest in the participant's visual field, providing insights into attention patterns and environmental engagement.

**Features:**
- Fixation detection and classification
- SAM-based object segmentation at fixation points
- Temporal gaze pattern analysis
- Quantify the attention allocation

**Key Components:**
- `scripts/`: Main inference and processing scripts
- `config/`: Configuration files for models and parameters
- `eval/`: Evaluation metrics and analysis tools

[📖 See detailed documentation](./Gaze/README.md)

---

### 4. Physiological Signal Processing (`/Physiology`)

Processes and analyzes multimodal physiological signals from Empatica including heart rate variability (HRV), electrodermal activity (EDA).

**Features:**
- Heart rate variability analysis
- Electrodermal activity processing
- Visualizing tool to inspect the dual-perspective visual data and physiological data

**Key Components:**
- `hrv/`: Heart rate variability analysis
- `eda/`: Electrodermal activity processing
- `gaze/`: Gaze-physiology integration
- `utils/`: Common processing utilities
- `segments_inspect_vis_tools/`: Visualization tools

[📖 See detailed documentation](./Physiology/README.md)


### Individual Module Usage

Each module can be run independently. Please refer to the respective README files in each subdirectory for detailed usage instructions.


## Citation

If you use this framework in your research, please cite:

```bibtex
@article{BEFIT_NO_Framework_Study,
  title={An Automated Multimodal Framework for Capturing Dynamic and Micro-scale Interactions between the Built Environment and Vulnerable Older Adults},
  autho
  journal={Building and Environment},
  year={2026}
}
```

## Related Work

This framework was developed as part of the **BE-FIT (Built Environment in Falls and ArthrITis Study)** study, investigating how BE factors influence mobility and independence in older adults with knee OA or fall history.
