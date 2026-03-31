# Problem Set 01: Chest X-ray Classification using CNN

## Overview
This project aims to build a Convolutional Neural Network (CNN) model to classify chest X-ray images into two categories: NORMAL and PNEUMONIA.

---

## Dataset
The dataset contains 5,863 chest X-ray images divided into three folders: train, validation, and test. Each folder contains two classes: NORMAL and PNEUMONIA.

---

## Approach
The dataset was loaded from Google Drive using the given folder structure. Images were resized to 128×128 and normalized to improve model performance.

---

## Methodology
A Convolutional Neural Network (CNN) was used for classification. The model consists of convolutional layers, max pooling layers, flatten layer, dense layers, and dropout for regularization. The model was trained using the Adam optimizer and binary crossentropy loss. Early stopping was applied to prevent overfitting.

---

## Results

### Model Performance

| Metric              | Value |
|--------------------|------|
| Training Accuracy  | ~99% |
| Validation Accuracy | Up to 100% |
| Test Accuracy      | ~77% |   

### Confusion Matrix
[[ 93 141]
[ 2 388]]


### Classification Report

| Class       | Precision | Recall | F1-score |
|------------|----------|--------|----------|
| NORMAL     | 0.98     | 0.40   | 0.57     |
| PNEUMONIA  | 0.73     | 0.99   | 0.84     |

---

## Conclusion
The CNN model was successfully developed to classify chest X-ray images into NORMAL and PNEUMONIA categories. The model achieved high training accuracy and was able to detect pneumonia cases effectively. However, the test accuracy was comparatively lower, indicating some overfitting. Overall, the model demonstrates the potential of deep learning in medical image classification.


---

### Confusion Matrix
