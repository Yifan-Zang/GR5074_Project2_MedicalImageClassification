# GR5074_Project2_MedicalImageClassification
**Columbia University · Advanced Machine Learning (GR5074)**

**Team Members:**
- Chunlin An
- Xingyu Shi
- Yifan Zang

## Project Overview

This project develops a deep learning pipeline for medical image classification using the COVID-19 Radiography Dataset (Chowdhury et al., 2020). The primary goal is to explore convolutional neural networks (CNNs) and transfer learning techniques for classifying chest X-ray images into COVID-positive and negative cases.

We implemented multiple models, including a custom CNN, ResNet50, VGG16, DenseNet121, and EfficientNetB0, to compare their performance. The project also analyzes the impact of data augmentation and transfer learning on generalization.

## Objectives
1. Perform exploratory data analysis (EDA) and evaluate class imbalance.
2. Build a baseline CNN model from scratch.
3. Apply transfer learning with ResNet50 and fine-tune it.
4. Implement three additional architectures (VGG16, DenseNet121, EfficientNetB0).
5. Compare all models under consistent preprocessing and evaluation settings.
6. Investigate data augmentation effects on model robustness.
7. Reflect on performance differences, and clinical relevance.

## Dataset

Source: COVID-19 Radiography Database

**Classes:**
- Normal
- Viral Pneumonia
- COVID-19

We used a stratified 70/15/15 split for training, validation, and testing.
Class imbalance was mitigated using data augmentation (rotation, flipping, zoom, and brightness adjustment).

## Methods

### 1. Baseline CNN
- **Architecture:** 3 convolutional blocks and dense layers
- **Loss:** Categorical Cross-Entropy
- **Optimizer:** Adam (learning rate = 0.001)
- **Metrics:** Accuracy, F1-score

### 2. Transfer Learning (ResNet50)
- Initialized with ImageNet weights
- Unfrozen final layers for fine-tuning
- Applied batch normalization and dropout
- Improved both convergence speed and validation accuracy

### 3. Additional Architectures
| Model | Type | Fine-tuned Layers | Validation Accuracy |
|-------|------|------------------|----------------------|
| **VGG16** | Transfer Learning | Last 4 convolutional blocks | Moderate generalization |
| **DenseNet121** | Transfer Learning | Last dense block | High accuracy and stability |
| **EfficientNetB0** | Transfer Learning | Entire model fine-tuned | Best validation and test performance |

## Key Takeaways
- Transfer learning significantly boosts performance with limited medical data.
- Data augmentation effectively mitigates class imbalance and improves generalization.

## Dataset Citation
- Chowdhury, M.E.H., Rahman, T., Khandakar, A., Mazhar, R., Kadir, M.A., Mahbub, Z.B., Islam, K.R., Khan, M.S., Iqbal, A., Al-Emadi, N., & Reaz, M.B.I. (2020).
Can AI help in screening Viral and COVID-19 pneumonia?
arXiv preprint, https://arxiv.org/abs/2003.13145
