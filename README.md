# Depth-Only UAV Obstacle Avoidance (Lightweight Real-Time Model)

This project implements a deep learning–based obstacle avoidance system for Unmanned Aerial Vehicles (UAVs), using only single-channel depth images to predict navigation actions in real time. The model is designed to run efficiently on resource-constrained platforms such as the NVIDIA Jetson Xavier NX.

## 🔧 Features

- Depth-only input (no RGB or external localization)
- Lightweight architecture (~696 KB)
- Real-time inference (~17.7 ms per frame) using TP4 on Google Colab
- Temporal modeling using GRU
- Attention-based pooling mechanism
- Trained and validated in CoppeliaSim
- Real-world testing with Intel RealSense D435

## Model Architecture

- **Spatial Encoder**: Depthwise-Separable Convolutions + GroupNorm
- **Feature Extractor**: Additional convolutional layers with max pooling
- **SPP**: 2×2 Spatial Pyramid Pooling
- **Temporal Modeling**: GRU (Gated Recurrent Unit)
- **Attention**: Simple linear attention layer
- **Classifier**: Fully connected output layer for 9 navigation classes

##  Dataset

### Training
- Collected from CoppeliaSim
- 10,178 single-channel depth frames
- Manually piloted UAV trajectories

### Testing
- Real-world depth sequences from Intel RealSense D435
- 205 frames

## Evaluation Metrics

- Classification Accuracy
- Training/Validation Loss and Accuracy
- Confusion Matrix
- Action Time (Inference Latency)
- Model Size (Memory Footprint)

## Deployment

- Tested on Google Colab with NVIDIA T4 GPU
- Designed for deployment on Jetson Xavier NX or similar platforms
- Inference time: ~17.7 ms/frame

##  Requirements

- Python 3.8+
- PyTorch 1.12+
- OpenCV
- NumPy
- CoppeliaSim (for simulation-based training)
- RealSense SDK (optional, for real-world testing)

