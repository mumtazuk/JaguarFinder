# Jaguar Re-Identification (ReID) Project

This repository contains code and model architectures for **Jaguar Re-Identification** — a computer vision task where the goal is to identify individual jaguars across different images.

> ⚠️ **Important:** Due to Kaggle competition rules, the dataset used in this project is **not included** in this repository. You must download it yourself from the Kaggle competition page.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Installation](#installation)
- [Usage](#usage)
- [Model Architectures](#model-architectures)
- [State-of-the-Art Methods and Key References](#state-of-the-art-methods-and-key-references)
- [License](#license)
- [Result](#result)
---

## Project Overview

This project implements a **closed-set all-vs-all re-identification** system for jaguars. Given a pair of images, the system predicts a similarity score (0.0–1.0) indicating whether both images depict the same jaguar.

Key Features:
- Data preprocessing and augmentation pipelines
- Deep learning model for feature extraction
- Pairwise similarity computation
- Designed for identity-balanced Mean Average Precision (mAP) evaluation

---

## Dataset

The dataset comes from the **Jaguar Re-Identification Challenge** on Kaggle:

- **Competition page:** [Jaguar ReID on Kaggle](https://www.kaggle.com/competitions/jaguar-re-id)  
- **Files required for training and testing:**
  - `train/` — training images (1,896 jaguar images)
  - `train.csv` — mapping of filenames to jaguar identities
  - `test/` — test images (371 images)
  - `test.csv` — image pairs for similarity predictions

> You must download the dataset from Kaggle yourself and cannot include it in this repository.

---

## Installation

Clone the repo and install dependencies:

```bash
git clone https://github.com/mumtazuk/JaguarFinder
cd jaguar-reid
pip install -r requirements.txt
```
---
## Model Architectures

This project evaluates Swin Transformer deep learning architectures for jaguar re-identification.


### Swin Transformer
- Hierarchical transformer with shifted windows
- Efficient for high-resolution images
- Used as the main model in this project

---
Architecture pipeline:
Image
 ↓
Swin Transformer
 ↓
Feature Vector
 ↓
Embedding Layer
 ↓
Cosine Similarity
---

## State-of-the-Art Methods and Key References

The following modern computer vision and metric learning techniques can significantly improve the **JaguarFinder wildlife re-identification system**.

---

### 1. Vision Transformer (ViT)

Vision Transformer applies the Transformer architecture directly to **image patches**, allowing the model to learn **global image relationships using self-attention** instead of convolution.

**Key Idea**
- Splits images into 16×16 patches
- Processes patches like tokens in NLP
- Captures long-range dependencies in images

**Performance**
- ImageNet: **88.55% Top-1 Accuracy**
- CIFAR-100: **94.55% Accuracy**

**Paper**  
*An Image is Worth 16×16 Words: Transformers for Image Recognition at Scale*  
https://arxiv.org/abs/2010.11929

---

### 2. Self-Supervised Learning with DINO

DINO learns powerful image representations **without labeled data**, which is highly useful for wildlife datasets where manual labeling is expensive.

**Key Idea**
- Self-distillation training
- Learns strong visual features
- Enables clustering of similar animals

**Performance**
- ViT-DINO on ImageNet: **79.9% Top-1 Accuracy**

**Paper**  
*Emerging Properties in Self-Supervised Vision Transformers*  
https://arxiv.org/abs/2104.14294

---

### 3. Transformers for Object Re-Identification

Transformers have recently been adopted for **object re-identification (re-ID)** tasks such as person identification and wildlife tracking.

**Advantages**
- Attention-based feature learning
- Robust to viewpoint and lighting changes
- Strong cross-image matching ability

**Benchmark Performance (Market1501)**

- mAP: **88–92%**
- Rank-1 Accuracy: **94–96%**

**Paper**  
*Transformer for Object Re-Identification: A Survey*  
https://arxiv.org/abs/2401.06960

---

### 4. TransMatcher (Transformer Image Matching)

TransMatcher is a transformer-based framework designed specifically for **image matching in re-identification tasks**.

**Key Idea**
- Learns cross-image relationships
- Improves matching between unseen camera views

**Performance (Market1501)**

- mAP: **90.1%**
- Rank-1 Accuracy: **95.0%**

**Paper**  
*TransMatcher: Deep Image Matching Through Transformers for Generalizable ReID*  
https://arxiv.org/abs/2105.14432

---

### 5. Metric Learning — Triplet Loss (FaceNet)

Triplet Loss learns embeddings where:

- Images of the **same identity are closer**
- Images of **different identities are farther apart**

It trains using **triplets**:
- Anchor
- Positive (same identity)
- Negative (different identity)

**Performance**

- LFW: **99.63% Accuracy**
- YouTube Faces DB: **95.12% Accuracy**

**Paper**  
*FaceNet: A Unified Embedding for Face Recognition and Clustering*  
https://arxiv.org/abs/1503.03832

---

### 6. ArcFace & CosFace (Angular Margin Losses)

ArcFace and CosFace improve embedding discrimination by introducing **angular margins in the loss function**, leading to better identity separation.

**Performance**

- CASIA-WebFace: **99.3%**
- MegaFace: **99.42%**

**Paper**  
*X2-Softmax: Margin Based Loss Functions for Deep Face Recognition*  
https://arxiv.org/html/2312.05281v2

---

### 7. Swin Transformer

Swin Transformer is a **hierarchical Vision Transformer** that processes images using **shifted local windows**, allowing efficient capture of both local and global features.

**Performance**

- ImageNet Top-1: **87.3%**
- ImageNet Top-5: **97.6%**

**Paper**  
*Swin Transformer: Hierarchical Vision Transformer using Shifted Windows*  
https://arxiv.org/abs/2103.14030

---

### 8. Recent Re-Identification Enhancements

Recent research combines **Swin Transformers with advanced loss functions and re-ranking techniques** to improve re-ID performance.

**Performance (Market1501)**

- mAP: **95.2%**
- Rank-1 Accuracy: **97.1%**

**Paper**  
*Swin Transformer with Two-Fold Loss and Background Adaptation for ReID*  
https://www.mdpi.com/2079-9292/11/13/1941

---

### 9. Animal Re-Identification Techniques

Recent wildlife re-identification systems combine **Transformers with ArcFace-based metric learning**.

These methods work well for **animal identity recognition from camera trap images**.

**Typical Performance**

- mAP: **86–90%**
- Rank-1 Accuracy: **92–94%**

**Paper**  
*Animal Re-Identification and Swin with ArcFace (MegaDescriptor)*  
https://link.springer.com/10.1007/s11263-025-02708-9


---

## Result
| Model    | Loss     | Notes            |
| -------- | -------- | ---------------- |
| Swin     | **0.79** | best performance |



## License

This project is licensed under the MIT License.  
See the LICENSE file for details.