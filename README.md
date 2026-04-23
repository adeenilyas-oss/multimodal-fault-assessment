# Multimodal Deep Learning for Autonomous Traffic Accident Fault Assessment

## Overview

This project presents a multimodal deep learning system for automated traffic accident fault assessment using video data. The system combines spatio-temporal visual analysis with vehicle trajectory and kinematic modeling to produce objective, percentage-based fault allocation.

Traditional accident investigation is manual, time-consuming, and prone to bias. This project aims to transform that process into a data-driven, consistent, and scalable solution.

---

## Objectives

- Automate accident fault determination
- Reduce subjectivity and human bias
- Accelerate insurance claim processing
- Provide explainable AI-based decisions
- Enable data-driven road safety insights

---

## System Architecture

The system is divided into two primary modules:

### Sub-System A: Spatio-Temporal Video Analysis

Focus:
- Scene understanding
- Traffic rule violations
- Pre-crash behavior

Approach:
- Two-Stream I3D Network
  - RGB stream for appearance
  - Optical flow stream for motion

Input:
- Dashcam video frames

Output:
- Contextual fault predictions

---

### Sub-System B: Vehicle Trajectory and Kinematics

Focus:
- Vehicle motion analysis
- Speed, acceleration, and interaction dynamics

Pipeline:
1. Vehicle Detection (YOLOv8)
2. Object Tracking (DeepSORT)
3. Trajectory Extraction
4. Motion Feature Computation

Model:
- Transformer-based sequence model

Output:
- Physics-based fault predictions

---

## Fusion Strategy

Final fault prediction is computed using a weighted fusion approach:

```
final_result = (confidence_A * result_A + confidence_B * result_B) / total_confidence
```

Fusion methods include:
- Confidence-based weighting
- Learned neural fusion
- Scenario-specific strategies

---

## Datasets

### Car Crash Dataset (CCD)
- Dashcam footage
- Used for spatio-temporal analysis
- ~75,000 files

### HWID12 Dataset
- Highway surveillance videos
- Used for trajectory modeling
- 2,700+ clips

### CCTV Dataset
- Mixed real-world scenarios
- Used for validation

### YOLOv8 Benchmark
- Object detection baseline
- Performance comparison

---

## Data Processing Pipeline

- Frame extraction (10 FPS)
- Resolution normalization (224x224)
- Data augmentation
- Temporal sequencing
- Cross-dataset harmonization

---

## Evaluation Metrics

### Core Metrics
- Accuracy
- F1 Score
- Fault percentage error

### Additional Metrics
- Ranking correctness
- Tracking consistency
- Motion prediction accuracy

---

## Explainability

The system integrates explainable AI techniques:

- Grad-CAM visualizations
- Attention maps
- Temporal importance analysis

These methods provide insight into model decisions and improve transparency.

---

## Tech Stack

- Python
- PyTorch / TensorFlow
- OpenCV
- YOLOv8
- DeepSORT
- Transformer architectures

---

## Experimental Plan

### Phase 1
- Independent model development
- Dataset-specific optimization

### Phase 2
- Model comparison
- Cross-dataset evaluation

### Phase 3
- Fusion model development
- Final system evaluation

---

## Expected Outcomes

- Reduced accident analysis time
- Improved consistency in fault determination
- Lower operational costs for insurance workflows
- Scalable and deployable AI system

---

## Applications

- Insurance claim automation
- Traffic monitoring systems
- Fleet management
- Driver assistance systems
- Autonomous vehicle liability assessment

---

## Future Work

- Real-time deployment pipeline
- Integration with smart city infrastructure
- Multi-vehicle interaction modeling
- Edge deployment for in-vehicle systems

---

## Contributors

- Sub-System A: Video Analysis
- Sub-System B: Trajectory Modeling

---

## License

This project is intended for academic and research use.
