# CIFAR-10 Image Classification using VGG16

A PyTorch-based image classification project using the **CIFAR-10 dataset** and a **pre-trained VGG16 model** with transfer learning.

## Overview

The project classifies CIFAR-10 images into 10 categories using a pre-trained VGG16 convolutional neural network.

The pre-trained VGG16 feature extractor is frozen, while the final classifier is replaced with a custom fully connected network containing 10 output classes.

## Dataset

**CIFAR-10** contains 60,000 color images of size 32×32 pixels divided into 10 classes:

- airplane
- automobile
- bird
- cat
- deer
- dog
- frog
- horse
- ship
- truck

The dataset is downloaded automatically through `torchvision.datasets.CIFAR10`, so the dataset itself is **not included in this repository**.

## Model

**Architecture:** Pre-trained VGG16

The original VGG16 classifier is replaced with:

```text
Linear(25088 → 1024)
ReLU
Dropout(0.3)
Linear(1024 → 256)
ReLU
Dropout(0.3)
Linear(256 → 10)
```

The convolutional feature layers are frozen during training.

## Training Configuration

| Parameter | Value |
|---|---|
| Framework | PyTorch |
| Model | Pre-trained VGG16 |
| Optimizer | Adam |
| Learning Rate | 0.0001 |
| Loss Function | Cross Entropy Loss |
| Batch Size | 64 |
| Epochs | 10 |
| Train/Validation Split | 80/20 |
| Random Seed | 42 |

## Results

The recorded training run in the notebook achieved:

| Metric | Result |
|---|---:|
| Training Accuracy | **72.22%** |
| Validation Accuracy | **64.17%** |
| Test Accuracy | **64.11%** |

Training and validation loss/accuracy curves are included in the notebook.

## Project Structure

```text
CIFAR10-VGG16/
│
├── CIFAR10_VGG16_Transfer_Learning.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

## How to Run

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd CIFAR10-VGG16
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Open the notebook

Open:

```text
CIFAR10_VGG16_Transfer_Learning.ipynb
```

You can run it using Jupyter Notebook, JupyterLab, or Google Colab.

### 4. Dataset download

The CIFAR-10 dataset will be downloaded automatically when the dataset cell is executed.

## Technologies Used

- Python
- PyTorch
- Torchvision
- NumPy
- Matplotlib
- Jupyter Notebook / Google Colab

## Note

The repository contains the notebook and the recorded experiment results. The CIFAR-10 dataset is not uploaded to GitHub because it is downloaded automatically by the notebook.
