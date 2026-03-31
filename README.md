This problem set is aimed at training a CNN to classify chest X-rays.

## Introduction
In this project, the researcher is aimed at constructing a Convolutional Neural Network (CNN) model to classify the images of chest X-rays into two categories: NORMAL and PNEUMONIA. The dataset is comprised of the X-ray imaging of the chest of patients aged between one and five years in their routine clinical care. 

The aim of the project is to create a model that will be able to identify pneumonia with X-ray images automatically and help in quicker and more accurate medical diagnosis.

---

## Dataset
There are 5,863 JPEG images in the dataset in three folders:
- Train
- Validation
- Test

In every folder, there are two classes:
- NORMAL  
- PNEUMONIA  

---

## Approach
Google drive was used to load the dataset using Keras ImageDataGenerator. All the images were scaled to 128x128 pixels and had their pixel values scaled to 0-1. Some of the data augmentation methods that were used are rotation, zooming and horizontal flipping that were used to augment data variability. The training, validation, and test data were directly separated in the predefined folder structure to be used to develop the model.

---

## Methodology
A Convolutional Neural Network (CNN) was developed in binary image classification. The model is made up of several convolutional layers that detect significant features of the input images, and then it is reduced to dimensions by max-pooling layers. 

Once the feature has been extracted, the feature maps are transformed into a one-dimensional vector by means of a flatten layer that is followed by dense layers. To minimize overfitting a dropout layer was added where the neurons are randomly disabled to prevent overfitting.

The loss function and the optimizer that was used to compile the model were binary crossentropy and Adam optimizer. Early stopping was used to check the loss of validation and the training was stopped when no improvement was found, thus giving improved generalization.

---

## Findings

### Model Performance

| Metric               | Value   |
|----------------------|--------|
| Training Accuracy    | ~87%   |
| Validation Accuracy  | Up to 93% |
| Test Accuracy        | 0.8654 |

---

### Confusion Matrix

|               | Predicted NORMAL | Predicted PNEUMONIA |
|---------------|----------------|---------------------|
| Actual NORMAL | 179            | 55                  |
| Actual PNEUMONIA | 29         | 361                 |

**Interpretation:**
The model rightly identified 179 NORMAL pictures and 55 NORMAL pictures were incorrectly identified as PNEUMONIA. In the PNEUMONIA class, 361 photos were rightly recognized and 29 were wrongly recognized as NORMAL. This means that the model is effective in both classes and more effective in identifying the cases of pneumonia.

---

### Classification Report

| Class       | Precision | Recall | F1-Score | Support |
|------------|----------|--------|----------|---------|
| NORMAL     | 0.86     | 0.76   | 0.81     | 234     |
| PNEUMONIA  | 0.87     | 0.93   | 0.90     | 390     |

| Metric        | Value |
|--------------|------|
| Accuracy     | 0.87 |
| Macro Avg    | 0.86 / 0.85 / 0.85 |
| Weighted Avg | 0.87 / 0.87 / 0.86 |

**Explanation:**
The classification report demonstrates an equal performance in the two classes. Normal class is a little less in recall, which implies that some normal cases are wrongly classified. On the contrary, PNEUMONIA class is more effective in recalling, meaning that the model is very efficient in detecting cases of pneumonia. The generalization of unseen data is good since the generalization accuracy is approximately 87%.

---

## Conclusion
The CNN model was also effectively created to classify the chest X-ray images as NORMAL and PNEUMONIA. The model performed well both on the training data and the test data hence better generalization. It is especially useful in identifying cases of pneumonia, which is significant in the diagnosis of medicine. Generally, the findings prove the efficiency of deep learning methods in the process of medical image classification.
