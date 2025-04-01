
# M32895 Big Data Applications – Coursework

 
**Image Classification with Convolutional Neural Networks using CIFAR-10**
UP2116690 - William Cole, UP2113629 - Harry Hallett
---

## Introduction  
This project shows the use of a complete machine learning pipeline using a Convolutional Neural Network (CNN) for image classification. The CIFAR-10 dataset, consisting of 60,000 32x32 color images in 10 classes, is used. The project involves data preprocessing, exploratory data analysis (EDA), CNN model construction, evaluation, and prediction.

---

## Business Objectives  
The goal is to develop an effective image classifier using CNN that can accurately predict image classes from unseen test data. The target is to achieve a high classification accuracy while minimizing validation loss and overfitting.

---

## ML Pipeline

### 1. Data Collection  
- **Dataset**: CIFAR-10, loaded via `tensorflow.keras.datasets`.
- **Validation**: Data shape and type were verified (50000 training samples, 10000 test samples, 32x32x3 RGB images).
- **Preprocessing**:
  - Normalized pixel values to the range [0, 1].
  - Labels were one-hot encoded using `to_categorical`.
  - The training data was split into 80% training and 20% validation using `train_test_split`.

### 2. Exploratory Data Analysis (EDA)  
- Plotted 10 sample images from different classes to understand class distribution and verify correct labeling.

### 3. Model Building  
- Used a sequential CNN architecture:
  - 3 convolutional layers (32, 64, 128 filters)
  - MaxPooling after each conv layer
  - A dense layer with 256 units and dropout for regularization
  - Softmax output layer for classification
- Used Adam optimizer and categorical cross-entropy loss.

### 4. Model Evaluation  
- Model was trained for 20 epochs with batch size 64.
- Training/validation accuracy and loss were plotted.
- Final test accuracy was evaluated on unseen test data.
- Classification report and confusion matrix were generated for detailed insight.

### 5. Prediction  
- The model was tested on unseen test data.
- Predictions were compared to true labels and visualized via confusion matrix.

---

## Jupyter Notebook Structure  
- **Imports and setup**
- **Data loading and preprocessing**
- **EDA: visual inspection of images**
- **CNN model creation and training**
- **Evaluation and visualization**
- **Final testing and prediction analysis**

---

## Libraries Used

- **TensorFlow/Keras** – Deep learning framework used for building and training CNN.
- **NumPy** – Numerical operations and data manipulation.
- **Matplotlib** – Visualization of training metrics and images.
- **Seaborn** – Enhanced plotting (confusion matrix).
- **Pandas** – Data handling and inspection.
- **Sklearn** – For splitting data and evaluation metrics like confusion matrix, classification report.

---
