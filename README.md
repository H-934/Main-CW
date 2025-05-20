
# M32895 Big Data Applications – Coursework

 
**Image Classification with Convolutional Neural Networks using CIFAR-10**

UP2116690 - William Cole, UP2113629 - Harry Hallett

---

## Introduction  
This project shows the use of a complete machine learning pipeline using a Convolutional Neural Network (CNN) for image classification. We chose to use the CIFAR-10 dataset, consisting of 60,000 32x32 color images organised into 10 classes. The project involves data preprocessing, exploratory data analysis (EDA), CNN model construction, evaluation and prediction.

---

## Objectives  
The goal is to develop an effective image classifier using CNN that can accurately predict image classes from unseen test data. The target is to achieve a high classification accuracy while minimizing validation loss and overfitting.

---

## ML Pipeline

### 1. Data Collection  
- **Dataset**: CIFAR-10, loaded using `tensorflow.keras.datasets`.
- **Validation**: Data shape and type were verified (50000 training samples, 10000 test samples, 32x32x3 RGB images).
- **Preprocessing**:
  - Normalized pixel values to the range [0, 1].
  - Labels were one-hot encoded using `to_categorical`.
  - The training data was split into 80% training and 20% validation using `train_test_split`.

### 2. Exploratory Data Analysis (EDA)  
- A class distribution plot was generated using `seaborn` to confirm dataset balance, reducing the risk of model bias towards dominant categories. 
- Plotted 10 sample images from different classes to understand class distribution and verify correct labeling.

### 3. Model Building  
Three different CNN models were developed to compare architectural complexity and performance:

Model 1:
- Three convolutional layers with 32, 64, and 128 filters. Increasing the number of filter per layer allows the network to learn more abstract features progressively which improves classification accuracy.
- MaxPooling after each layer.
- Flattened layer.
- Dense layer with 256 units and dropout (0.5).
- Softmax output (10 units).

Model 2:
- Two convolutional layers (32, 64 filters).
- Smaller dense layer with 128 units and dropout (0.4).
- Reduced learning rate (0.0008).

Model 3:
- Four convolutional layers (including two consecutive 32-filter layers).
- Dense layer with 512 units and dropout (0.3).
- Learning rate of 0.0005.

All models were compiled with the Adam optimiser and categorical cross-entropy loss function.

### 4. Model Evaluation  
- Model was trained for 20 epochs with batch size 64.
- `EarlyStopping` was implemented to reduce overfitting, monitoring validation loss.
- Validation accuracy and loss were plotted for all models.
- `custom compare_histories()` was used to visualise model performance trends.
- Final model performance was assessed on the test set.

### 5. Prediction  
- The best-performing model (Model 3) was tested on unseen test data.
- A classification report was generated showing precision, recall, and F1-score per class.
- A confusion matrix visualised prediction performance across categories.
- `show_predictions()` was used to display example image predictions with confidence scores.

---

## Jupyter Notebook Structure  
- **Imports and setup**
- **Data loading and preprocessing**
- **EDA: visual inspection of images**
- **Model definitions**
- **Training and validation**
- **Performance comparison and accuracy visualisation**
- **Testing on unseen data**
- **Prediction visualisation**

---

## Libraries Used
- **TensorFlow / Keras** – Constructing and training CNN models efficiently using high-level API layers like `Conv2D`, `MaxPooling2D` and optimisers like Adam.
- **NumPy** – Efficient numerical computations and matrix operations
- **Matplotlib** – Plotting training metrics and displaying images
- **Seaborn** – Enhanced visualisations such as confusion matrices and class distribution
- **Pandas** – Data inspection
- **Sklearn** – Evaluation metrics like classification reports and tools like `train_test_split`.

---

### Acknowledgements and References 
All core ML pipeline components (preprocessing, training, evaluation, EDA) were based on lecture and tutorial content.
The functions `compare_histories()` and `show_predictions()` were created using online guides such as Tensorflow documentation and suggestions from GitHub's inbuilt Microsoft Copilot assistant, then customised for the CIFAR-10 dataset.
>>>>>>> 261f195d7cd9a58ebb037c8fa5df4f76d486a75a
