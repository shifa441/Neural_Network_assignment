The problem set 01 :  Chest X-ray Classification with CNN.

## Introduction
The project is aimed at developing a Convolutional Neural Network (CNN) model to perform the two-way classification of the chest X-ray images into two groups of NORMAL and PNEUMONIA. The data is a collection of pediatric chest X-ray images of patients between one and five years old in the course of normal clinical treatment.This project aim is to come up with a model that can be used to automatically identify pneumonia on X-ray images which can aid in quicker and more accurate diagnosis of medical conditions.


---

## Dataset
The data set contains 5,863 JPEG images that are stored in three folders:
- Train
- Validation
- Test

Every folder is represented by two classes:
- NORMAL  
- PNEUMONIA  

---

## Approach
Keras ImageDataGenerator was used to load the dataset in Google Drive. All pictures were downsampled to 128x128 pixels and the values of the pixels were scaled to fall between 0 and 1. Rotation, zooming, and horizontal flipping are data augmentation methods that were used to enhance data variability. Training, validation and test data to develop the model were separated using the predefined folder structure directly.

---

## Methodology
Convolutional Neural Network (CNN) was created to classify binary images. It is made up of many convolutional layers which extract significant features out of the input images, and then max-pooling layers, which reduce the dimensions. 

The feature maps are then transformed into a one-dimensional feature vector after feature extraction through the use of flatten layer and then undergo classification through dense layers. To minimize overfitting a dropout layer was added where the neurons are randomly disabled to prevent overfitting.

The Adam optimizer and binary crossentropy loss function were used to compile the model. Early stopping was used to check loss in validation and halt training when no progress was being made, and this ensures improved generalization.

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
The model rightly categorized 179 NORMAL images, and 55 NORMAL images were wrongly categorized as PNEUMONIA. In the PNEUMONIA class, 361 photos were rightly recognized and 29 were wrongly recognized as NORMAL. It means that the model works effectively in both classes and the results are a little more effective in identifying the cases of pneumonia.

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
The classification report reveals that there was an equal performance of both classes. Normal class has a little less recall, that is some normal cases are wrongly classified. The PNEUMONIA class on the other hand is more recallable meaning that the model is very effective in detecting pneumonia cases. The generalization of the unseen data is good since the overall accuracy is approximately 87%.

---

## Conclusion
To categorize the images of the chest X-ray as either NORMAL or PNEUMONIA, the CNN model was created successfully. The model performed well on the training and test data which showed better generalization. It has a high ability to diagnose pneumonia cases and this is critical in medical diagnosis. All in all, the findings indicate the usefulness of deep learning methods in medical image classification.
