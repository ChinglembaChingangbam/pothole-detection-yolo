# Pothole Detection using Deep Learning: A Comparative Study of YOLO Models

A research project comparing **YOLOv8s** and **YOLOv11s** for real-time pothole detection using computer vision. This study was conducted at the Department of Computer Science and Engineering, Assam Don Bosco University.

---

## Overview

Potholes pose a significant risk to road safety and vehicle integrity, particularly on rural and high-traffic roads. This project presents a comparative analysis of two state-of-the-art YOLO (You Only Look Once) object detection models for automated pothole detection.

**Key Findings:**
- **YOLOv8s** achieved higher precision (0.7501) and mAP@0.5 (0.6887) — best for accuracy-critical applications
- **YOLOv11s** demonstrated faster inference and higher recall (0.6267) — best for real-time edge deployments

---

## Results Summary

| Model | Precision | Recall | mAP@0.5 | mAP@0.5:0.95 |
|---|---|---|---|---|
| YOLOv8s | **0.7501** | 0.5786 | **0.6887** | 0.3314 |
| YOLOv11s | 0.6981 | **0.6267** | 0.6733 | **0.3320** |

---

## Project Structure

```
├── Notebooks/
│   ├── Yolov8_training.ipynb       # YOLOv8s training pipeline
│   └── YOLO11_training.ipynb       # YOLOv11s training pipeline
├── Dataset_Sample/                 # Sample annotated images
├── Results/                        # Training graphs, confusion matrices, predictions
├── paper.pdf                       # Full research paper
├── Requirements.txt
└── README.md
```

---

## Dataset

The dataset is sourced from [Roboflow Universe](https://universe.roboflow.com/shantanu-maity/potholes-detection-qwkkc/10) and contains:
- **3,393** annotated road images (single class: pothole)
- YOLO bounding box annotation format
- Split: 80% training / 10% validation / 10% testing
- Preprocessing: auto-orientation, resized to 640×640
- Augmentations: flips, rotations, hue/saturation/exposure adjustments, mosaic, blur, noise

To download the dataset, run the setup cell in either notebook (requires a Roboflow API key).

---

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/pothole-detection-yolo.git
cd pothole-detection-yolo
```

### 2. Install dependencies

```bash
pip install -r Requirements.txt
```

### 3. Open notebooks in Google Colab

Upload either notebook to [Google Colab](https://colab.research.google.com/) for GPU-accelerated training:

- `Notebooks/Yolov8_training.ipynb` — for YOLOv8s
- `Notebooks/YOLO11_training.ipynb` — for YOLOv11s

Each notebook walks through:
1. Installing Ultralytics
2. Downloading the dataset from Roboflow
3. Training the model
4. Evaluating results (confusion matrix, loss curves, predictions)
5. Running inference on images and videos

---

## Tech Stack

- **Python 3.x**
- **PyTorch** — deep learning framework
- **Ultralytics YOLOv8 / YOLOv11** — object detection models
- **OpenCV** — image processing
- **Roboflow** — dataset management
- **Google Colab** — GPU-accelerated training environment

---

## Model Architecture

Both models follow the YOLO architecture:
- Input images resized to **640×640**
- Convolutional backbone with batch normalization and dropout
- ReLU activations (linear activation in the final layer)
- Evaluated on Precision, Recall, mAP@0.5, and mAP@0.5:0.95

---

## Paper

The full research paper is included as [`paper.pdf`](./paper.pdf).

> *Pothole Detection using Deep Learning: A Comparative Study of YOLO Models*  
> Tilling Huto, Chao Nanchang Gogoi, Chinglemba Chingangbam, Kausthav Pratim Kalita, Mriganka Sarmah  
> Department of CSE, Assam Don Bosco University

---

## Authors

- Tilling Huto
- Chao Nanchang Gogoi
- Chinglemba Chingangbam
- Kausthav Pratim Kalita
- Mriganka Sarmah (Supervisor)

---

## MIT License

Copyright (c) 2023 BAPPY AHMED

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.



