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
- [License](#license)
- [References](#references)

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
git clone https://github.com/yourusername/JaguarFinder.git
cd jaguar-reid
pip install -r requirements.txt