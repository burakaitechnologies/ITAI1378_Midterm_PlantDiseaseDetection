# Plant Disease Detection System

**Team Members:** Ahmet Burak Solak (Solo)
**Course:** ITAI 1378 - Computer Vision
**Tier:** Tier 1 (Pre-trained model with minimal customization)

---

## Problem Statement

Farmers worldwide lose up to 40% of their crop yield annually due to plant diseases that go undetected until it's too late. Manual inspection is time-consuming, requires expert knowledge, and is not scalable for large farms. Early and accurate identification of plant diseases can save crops, reduce pesticide overuse, and improve food security.

## Solution Overview

An image classification system that identifies plant diseases from leaf photos using a pre-trained deep learning model. A user takes a photo of a plant leaf, the system classifies it as healthy or identifies the specific disease, and provides the result in seconds. This enables farmers and agricultural workers to quickly diagnose crop issues without needing expert knowledge.

## Technical Approach

| Component | Choice |
|-----------|--------|
| **Technique** | Image Classification |
| **Model** | ResNet50 (pre-trained on ImageNet) |
| **Framework** | PyTorch + torchvision |
| **Method** | Transfer learning - freeze early layers, fine-tune final classifier layer |

**Why ResNet50?** It provides strong classification accuracy out of the box, is well-supported in PyTorch, and transfer learning makes it feasible to train on a smaller dataset with limited compute resources (Google Colab free tier).

## Dataset Plan

| Detail | Info |
|--------|------|
| **Source** | [PlantVillage Dataset](https://github.com/spMohanty/PlantVillage-Dataset) (public) |
| **Size** | ~54,000 labeled leaf images |
| **Classes** | 38 classes (healthy + diseased across 14 plant species) |
| **Labels** | Pre-labeled by disease type (e.g., Tomato_Early_Blight, Potato_Late_Blight) |
| **Preparation** | Resize to 224x224, normalize, train/val/test split (70/15/15), basic augmentation (flip, rotate) |

No manual labeling is required. The dataset is clean and well-organized.

## Metrics

| Metric Type | Metric | Target |
|-------------|--------|--------|
| **Primary** | Classification Accuracy | >= 90% on test set |
| **Secondary** | Inference Speed | < 1 second per image |
| **Additional** | Per-class Precision/Recall | >= 85% for each disease class |

## Week-by-Week Plan

| Week | Task | Milestone |
|------|------|-----------|
| 10 (Oct 30) | Download PlantVillage dataset, set up Colab environment, explore data | Dataset ready, initial EDA notebook |
| 11 (Nov 6) | Load pre-trained ResNet50, set up training pipeline, train classifier | Model training and achieving baseline accuracy |
| 12 (Nov 13) | Evaluate model, tune hyperparameters, add augmentation if needed | Accuracy >= 90% on test set |
| 13 (Nov 20) | Build simple demo (Gradio or Streamlit), create demo video | Working demo application |
| 14 (Nov 27) | Final testing, write documentation, clean up repository | Repository and docs complete |
| 15 (Dec 4) | Present project | Presentation day |

## Resources Needed

| Resource | Details |
|----------|---------|
| **Compute** | Google Colab (free GPU tier) |
| **Frameworks** | PyTorch, torchvision, Gradio |
| **Dataset** | PlantVillage (free, open-source) |
| **Estimated Cost** | $0 |

## Risks & Mitigation

| Risk | Probability | Mitigation |
|------|------------|------------|
| Low accuracy on certain disease classes | Medium | Add data augmentation (rotation, color jitter); focus on top 10 most common classes |
| Dataset too large for Colab storage | Low | Use a subset of classes (e.g., tomato + potato diseases only) |
| Colab session timeout during training | Medium | Save checkpoints every epoch; use smaller batch size to train faster |
| Model overfitting | Medium | Use dropout, early stopping, and data augmentation |
| Demo deployment issues | Low | Fall back to a simple Jupyter notebook demo with sample predictions |

## AI Usage Log

| Date | Tool | Usage |
|------|------|-------|
| | | (Will be updated throughout the project) |

---

## Repository Structure

```
ITAI1378_Midterm_PlantDiseaseDetection/
├── README.md                  ← This file
├── requirements.txt           ← Python packages
├── notebooks/
│   └── 01_exploration.ipynb   ← Initial data exploration
├── data/
│   └── README.md              ← Dataset info and download instructions
└── docs/
    └── proposal.pdf           ← Presentation slides
```
