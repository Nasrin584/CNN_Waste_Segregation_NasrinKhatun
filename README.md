# CNN_Waste_Segregation_NasrinKhatun

## 🧠 Waste Classification Using CNN

This project aims to automate waste segregation using deep learning. By training a Convolutional Neural Network (CNN) on labeled images of waste materials, the model can predict categories like **Plastic**, **Glass**, **Metal**, **Cardboard**, **Food Waste**, **Other**, and **Paper**. The goal is to support environmentally friendly waste management systems using AI-driven solutions.

---

### 📁 Project Overview

This CNN-based image classification pipeline includes the following steps:

1. **Data Preparation**

   * Unzipping and loading image dataset.
   * Visualizing sample images across all classes (5 images/class).
   * Identifying smallest and largest image dimensions (all images found to be 256x256).
   * Normalizing pixel values (0–1 scale).
   * Encoding labels and splitting data into training and validation sets.

2. **Data Augmentation & Class Balancing**

   * Used Keras’ `ImageDataGenerator` to apply transformations like rotation, zoom, flips.
   * Augmented minority class images to balance dataset and reduce bias.

3. **Model Building**

   * Built a CNN with 3 convolutional layers, batch normalization, dropout (to reduce overfitting), and fully connected layers.
   * Included L2 regularization in convolution layers.
   * Used Adam optimizer and categorical cross-entropy loss.

4. **Model Training**

   * Included callbacks like `EarlyStopping` and `ReduceLROnPlateau`.
   * Trained the model using augmented data, with training and validation monitoring.

5. **Evaluation**

   * Evaluated performance on validation data.
   * Generated classification report and confusion matrix.
   * Visualized training/validation loss and accuracy over epochs.

---

### 📊 Analysis & Results

* **Validation Accuracy Achieved**: \~67%
* **Final Training Accuracy**: \~100% (signs of overfitting observed)
* **Class-wise Performance**:

  * Best precision/recall: **Plastic**, **Cardboard**
  * Lower performance: **Other**, **Paper** (indicating need for more diverse data)
* **Confusion Matrix**: Showed common misclassifications between visually similar categories (e.g., paper vs. cardboard).
* **Overfitting Mitigation**:

  * Used dropout layers and L2 regularization.
  * Augmented training data to reduce overfitting.

---

### 🔍 Key Learnings

* Data quality and class balance heavily influence classification performance.
* Regularization techniques like dropout and L2 help mitigate overfitting.
* Visual similarity between classes can confuse even a well-trained CNN.
* Validation performance is a more realistic indicator of generalization than training accuracy.
