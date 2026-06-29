# Urban Expansion Detection using Convolutional Neural Networks

## Overview

This project was developed as part of the **Machine Learning Course Project (Phase III)** for the **M.Sc. Data Science** program at the **University of Europe for Applied Sciences, Germany**.

The objective of this research is to develop and evaluate Convolutional Neural Network (CNN) models for automated land use and land cover classification using satellite imagery. The project compares a Custom CNN architecture with transfer learning models to identify the most effective approach for urban expansion detection.

---

## Dataset

* **Dataset:** EuroSAT
* **Source:** https://www.kaggle.com/datasets/apollo2506/eurosat-dataset
* **Images:** Approximately 27,000 RGB satellite images
* **Classes:** 10 land-use categories

---

## Models Implemented

* Custom CNN
* MobileNetV2 (Transfer Learning)
* ResNet50 (Frozen)
* Fine-Tuned ResNet50

---

## Image Preprocessing

* Image resizing (224 × 224)
* Pixel normalization
* Data augmentation

  * Rotation
  * Horizontal Flip
  * Width and Height Shift
  * Zoom

---

## Experimental Setup

* Framework: TensorFlow / Keras
* Optimizer: Adam
* Loss Function: Categorical Cross-Entropy
* Batch Size: 32
* Epochs: 20
* Early Stopping Enabled

---

## Results

| Model               | Accuracy |
| ------------------- | -------- |
| Custom CNN          | **91%**  |
| MobileNetV2         | 85%      |
| Fine-Tuned ResNet50 | 64%      |
| ResNet50 (Frozen)   | 23%      |

The Custom CNN achieved the highest performance and demonstrated superior classification capability for the EuroSAT dataset.

---

## Explainable AI

Grad-CAM was used to visualize the regions of satellite images that contributed to the model's predictions, improving the interpretability and reliability of the proposed framework.

---

## Repository Contents

* Urban_Expansion_Detection.ipynb
* Final Report (PDF)
* Presentation Slides
* CNN Accuracy Curve
* CNN Loss Curve
* Confusion Matrix
* Model Comparison
* Grad-CAM Visualization
* Sample Images

---

## Technologies Used

* Python
* TensorFlow
* Keras
* Google Colab
* NumPy
* Pandas
* Matplotlib
* Scikit-learn

---

## Author

**Athiqur Rahman M**

M.Sc. Data Science

University of Europe for Applied Sciences, Germany

Machine Learning Course Project – Phase III




