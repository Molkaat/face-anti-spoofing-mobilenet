# Face Anti-Spoofing Detection using MobileNetV2

A deep learning-based face anti-spoofing system designed to distinguish between **real** and **spoofed** facial inputs using transfer learning with **MobileNetV2**.

This project leverages lightweight CNN architecture for efficient inference while maintaining strong classification performance, making it suitable for real-time biometric authentication pipelines.

---

## Overview

Face anti-spoofing is critical in biometric systems to prevent attacks using:

- Printed photos
- Replay/video attacks
- Screen displays
- Fake facial reproductions

This model classifies facial inputs into:

- **Real**
- **Spoof**

---

## Features

- Transfer learning with **MobileNetV2**
- Custom classification head with regularization
- Data augmentation pipeline
- Class imbalance handling with weighted loss
- Full evaluation metrics and confusion matrix
- Exported trained model (`.hdf5`) for deployment

---

## Model Architecture

Base Model:

- **MobileNetV2 (ImageNet Pretrained)**

Custom Head:

- Conv2D
- Dropout
- GlobalAveragePooling
- Dense Layers
- Sigmoid Binary Classifier

---

## Dataset

Trained on **LCC_FASD Dataset**:

- Real Faces
- Spoof Faces

Dataset Split:

| Split | Real | Spoof | Total |
|--------|------|-------|-------|
| Train | 1272 | 1500 | 2772 |
| Validation | 405 | 2543 | 2948 |
| Test | 314 | 7266 | 7580 |

---

## Performance

### Test Results

| Metric | Score |
|--------|------|
| Accuracy | **82.32%** |
| Precision | **99.61%** |
| Recall | **81.87%** |
| F1 Score | **89.88%** |

---

## Training Configuration

```bash
Epochs: 15
Learning Rate: 5e-5
Batch Size: 32
Input Resolution: 224x224
Loss: Binary Crossentropy
Optimizer: Adam
