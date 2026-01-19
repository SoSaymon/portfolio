---
title: "Automated Root Phenotyping & Inoculation System"
date: 2026-01-16T10:00:00+02:00
draft: false
startDate: "Nov 2025"
endDate: "Jan 2026"
tags:
  - PyTorch
  - SegFormer
  - OpenCV
  - Reinforcement Learning
  - Opentrons
  - Weights & Biases
image: /images/projects/plants.jpg
description: "Automated system that segments plant roots and controls a robot to perform high-precision inoculations, reducing manual processing time 21× while achieving 0.18mm accuracy"
presentationLink: "/files/Presentation-Automated_Root_Phenotyping.pdf"
contributors:
  - name: "Szymon Chirowski"
    role: "Sole developer"
    link: "https://linkedin.com/in/szymon-chirowski"
---

During this block, I developed an **Automated Root Phenotyping & Inoculation System** for [NPEC](https://www.npec.nl/) as part of my education at BUas. The Netherlands Plant Eco-phenotyping Centre is a research facility dedicated to plant phenotyping, studying the interaction between genetics and environment to secure future food sustainability. Their goal is to rapidly screen and identify robust, disease-resistant plant genotypes using automated modules. My task was to automate the inoculation process using computer vision, deep learning segmentation models, and simulate the robotic workflow with reinforcement learning.

## Problem Definition

NPEC owns 7 state-of-the-art growth modules capable of generating massive amounts of data. However, the downstream analysis remains manual, creating a bottleneck. Valuable genetic data is lost due to fatigue, human error, or processing speed. The client’s focus for this project was *Arabidopsis thaliana*.

## Project Goal

My solution provides a **scalable and consistent** workflow. Robots can be added based on the client’s budget, and inoculation accuracy reached **0.18mm** in benchmarks. This reduced the time per Petri dish by **21×**—from ~3.5 minutes for a skilled scientist to just 10 seconds per dish—allowing scientists to focus on experiment design while automating repetitive tasks. The system segments root systems from images and controls an **Opentrons OT-2** liquid-handling robot for precise inoculation.

## Project Scope and Workflow

This was an **individual project**, completed end-to-end from data exploration and model development to evaluation and reporting.

### Data Preparation and Annotation

* **Annotation:** Created pixel-level annotations for three classes (shoot, seed, root) using LabKit, ensuring accurate root-shoot boundaries.
* **Quality Control:** Peer-reviewed annotations and created clean training/validation splits to prevent data leakage.

### Baseline Computer Vision

* **ROI Extraction:** Applied color thresholding and contour detection with OpenCV to isolate Petri dishes and standardize inputs.
* **Benchmarking:** Established baseline performance and identified failure modes caused by lighting variations.

### Deep Learning Modeling

* **Architecture:** Used **SegFormer** for semantic segmentation of roots and shoots.
* **Training Strategy:** Applied **Albumentations** for data augmentation to improve robustness.

### Experiment Tracking and Evaluation

* **MLOps:** Tracked experiments with **Weights & Biases (W&B)**, visualizing loss curves and monitoring metrics.
* **Evaluation:** Assessed segmentation quality through F1-scores and visual inspection of root tips for robotic targeting.

### Robotics and Reinforcement Learning

* **Simulation:** Created a custom **Gymnasium** environment simulating the robot, defining continuous observation (pipette & goal positions) and action spaces (velocity).
* **RL Agent:** Trained a **Soft Actor-Critic (SAC)** agent using **Stable Baselines 3**.
* **Reward Function:** Dense reward based on negative Euclidean distance, with penalties for collisions and success bonuses.

![Full-pipeline](/images/projects/benchmark_run_RL.gif)

### System Integration

* **Coordinate Mapping:** Transformed pixel coordinates from SegFormer to physical robot coordinates.
* **Validation:** Simulated end-to-end inoculation, ensuring the RL agent could reach targets identified by the vision model.

### Reflection and Iteration

* Optimized trade-offs between model complexity and inference speed.
* Refined RL reward functions for stable convergence.
* Enhanced data augmentation to resolve segmentation discontinuities.

## Key Results

### Computer Vision

* Root segmentation F1-score: **0.81**
* Shoot segmentation F1-score: **0.93**
* Primary root length sMAPE: **11.3%** (measures relative percentage error between predicted and true values)

### Robotics

* PID controller: 0.32mm accuracy, ~3s per plant
* RL controller: 0.18mm accuracy, ~1.2s per plant

## Assumptions and Limitations

* Works for Petri dishes with ≤5 evenly spaced plants.
* Roots do not overlap.
* Fixed camera position and orientation.
* Limited to *Arabidopsis thaliana*; new plants require retraining the segmentation model.
* Real-world deployment requires additional tuning for PID and RL controllers.

## Lessons Learned

### Technical

* Classical CV is efficient for structural tasks like ROI detection.
* High-quality annotations are crucial for fine details like root tips.
* RL agents are highly sensitive to reward design; dense rewards improve convergence.
* Transformer-based models like SegFormer handle global context better than CNNs for complex biological structures.

### Professional

* Client requirements (sMAPE targets, robotic precision) taught me to prioritize business objectives.
* Baseline-first workflow improves iterative development.
* Peer-reviewed annotations reinforced the importance of quality control.
* Vision models require robust integration logic to interface with physical systems effectively.

## Conclusion

This project strengthened my interest in applied computer vision and demonstrated how machine learning interacts with physical systems in real-world scenarios.
