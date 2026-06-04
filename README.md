Using Convolutional Neural Networks To Detect Urban Expansion

## Summary of Project

Urban Expansion is one of the major factors driving land-use change and land-cover change globally. Therefore, it is essential to continuously monitor urban expansion as part of sustainable city planning and environmental management, infrastructure development and allocation of resources. Urban expansion is typically monitored by manually interpreting satellite imagery, which can be time-consuming and is not easily scalable.

This project researches the potential to use deep learning techniques to automatically classify satellite imagery from the EuroSAT dataset. Multiple convolutional neural network (CNN) architectures were developed and tested to evaluate how well they can distinguish between land-use types in urban and non-urban areas.

The study compares one custom CNN architecture with two commonly used transfer-learning models (MobileNetV2 and ResNet50) for the purpose of identifying suitable applications for remote sensing.

# Objectives

The goals of the project include:

* Establishing a complete automated satellite image classification workflow;
* Processing and augmenting remote-sensing images for deep learning applications;
* Designing and training a custom convolutional neural network;
* Evaluating the performance of MobileNetV2 and ResNet50 as transfer-learning models;
* Comparing different evaluation metrics between models;
* Investigating how to visualize the interpretability of model results using Grad-CAM;
* Determining the best network architecture(s).

# Dataset Description
EuroSAT Dataset

The EuroSAT dataset consists of Sentinel-2 satellite images covering ten land-use and land-cover categories commonly encountered in remote sensing applications.

Dataset Source:

https://www.kaggle.com/datasets/apollo2506/eurosat-dataset

Land-Use Classes
Class
AnnualCrop
Forest
HerbaceousVegetation
Highway
Industrial
Pasture
PermanentCrop
Residential
River
SeaLake
Dataset Split
Dataset Partition	Samples
Training Set	18,900
Validation Set	5,400
Test Set	2,700

Total Images Used: 27,000

# Methodology

Data Pre-Processing Steps
The following preprocessing steps were applied to the images prior to classification:
1. Image resizing of 224 pixels x 224 pixels
2. Normalizing pixel values
3. Dividing dataset into training/validation/testing sets
4. Encoding labels, transforming categories of labels

Data Augmentation
To improve model generalization and reduce model overfitting additional augmentation techniques were applied to the dataset as follows:
1. Random rotation
2. Horizontal flipping
3. Width shifting
4. Height shifting
5. Zoom transformation

Model Architectures

Custom CNN
Custom New Convolutional Neural Network (CNN) was developed consisting of:
1. Four convolutional blocks
2. Batch Normalization layer
3. Max Pooling layer
4. Dense classification layers
5. Dropout regularization

Architectural design was made for satellite image classification.

MobileNetV2
MobileNetV2 was developed as a transfer-learning model using pretrained weights from ImageNet and frozen the base of the model, added a classification head.

ResNet50
ResNet50 was developed and used to assess whether deeper residual architectures can provide an effective means for remote sensing image classification.

Fine-tuned ResNet50
Experimentation conducted with ResNet50 was to partially unfreeze final layers and retrain using a slower learning rate.

# Experimental Results
Model Performance Comparison
Model	Test Accuracy
Custom CNN	91%
MobileNetV2	85%
ResNet50 (Frozen)	23%
ResNet50 (Fine-Tuned)	64%

# Discussion

The experimental data reveal that the custom CNN demonstrated superior classification performance with an overall test accuracy of approximately 91%. An equivalent performance was observed with MobileNetV2 (85%) through its reliance on features acquired from natural image datasets.

The initial implementation of ResNet50 exhibited low performance; therefore, it is fair to say that the ImageNet representation pre-trained on the dataset has not transferred effectively to the satellite image domain with no fine-tuning of the model. Nevertheless, following the fine-tuning process on the satellite images, the model improved its performance from 23% to 64%, but it remained lower than that of the custom CNN.

It would seem that when applied to a specific remote sensing dataset, models that are specifically built for this domain will outperform pre-trained, more complicated models due to their specific architecture.

# Explainable AI (Grad-CAM)

To further develop the model's transparency and interpretability, Grad-CAM (Gradient-weighted Class Activation Mapping) was utilized.

The visualizations produced from the Grad-CAM technology show which parts of an image play a substantial role in generating the model's predictions through the provision of visual evidence for the qualitative validation of land use features that the model is utilizing to generate its predictions as opposed to extraneous image characteristics.

# Evaluation Metrics

The following evaluation metrics were used:

Accuracy
Precision
Recall
F1-Score
Confusion Matrix
Classification Report
Grad-CAM Visual Analysis
Repository Contents

#Urban-Expansion-Detection-CNN/

├── Urban_Expansion_Detection.ipynb
├── README.md
├── dataset_link.txt
├── class_distribution.png
├── cnn_accuracy_curve.png
├── cnn_loss_curve.png
├── cnn_confusion_matrix.png
├── model_comparison.png
├── gradcam_overlay.png
├── sample_images.png
├── dataset/
├── docs/
├── figures/
└── notebook/

# Technologies Used
Python
TensorFlow
Keras
NumPy
Pandas
Matplotlib
Seaborn
OpenCV
Google Colab
GitHub
Future Work

# Potential extensions of this study include:

Hyperparameter optimization
Cross-validation experiments
Vision Transformer (ViT) architectures
EfficientNet-based models
Multi-spectral satellite imagery analysis
Urban change detection using temporal satellite data



