# 🌦️ Weather Classification System Using EfficientNetB3

This documentation provides a detailed explanation of a Weather Classification System implemented using transfer learning with EfficientNetB3 in Python. The goal of this system is to classify weather conditions into four categories (Fog, Rain, Snow, Sunny) based on image data.

---

## Overview

The project employs a custom dataset containing images representing different weather conditions. The model uses transfer learning with EfficientNetB3 as the base model and achieves an impressive accuracy of 99%.

## Libraries Used

The following Python libraries were used to implement the model:

- **NumPy:** For numerical operations
- **Pandas:** For data manipulation and analysis
- **Matplotlib & Seaborn:** For data visualization
- **TensorFlow/Keras:** For building and training the deep learning model
- **PIL (Pillow):** For image processing
- **Scikit-learn:** For data preprocessing and evaluation metrics
- **OpenCV (cv2):** For additional image processing capabilities

## Project Structure

**1. Data Loading and Preprocessing:**
- Images are loaded from the directory structure and organized into a DataFrame
- Data is split into training, validation, and test sets using `train_test_split`
- `ImageDataGenerator` is used to load and preprocess images in batches

**2. Model Architecture:**
- **Base Model:** Pre-trained EfficientNetB3 with ImageNet weights
- **Additional Layers:**
  - BatchNormalization
  - Dense layer (256 units) with L1 and L2 regularization
  - Dropout layer (45% dropout rate) to prevent overfitting
  - Output layer with softmax activation for 4 classes
- The model is compiled with Adamax optimizer, categorical crossentropy loss, and multiple metrics

**3. Model Training:**
- The model is trained for 25 epochs with the specified batch size
- Training history (accuracy and loss) is recorded for visualization

**4. Model Evaluation:**
- The model's accuracy and loss are plotted for both training and validation sets
- A classification report and confusion matrix are generated to evaluate the model's performance
- Final evaluation on test data shows 99% accuracy

**5. Results:**
- **Test Accuracy:** 99%
- **Class Performance:**
  - Fog: Precision 0.94, Recall 1.00, F1-score 0.97
  - Rain: Precision 1.00, Recall 1.00, F1-score 1.00
  - Snow: Precision 1.00, Recall 1.00, F1-score 1.00
  - Sunny: Precision 1.00, Recall 0.94, F1-score 0.97

## Conclusion

The weather classification system built with EfficientNetB3 demonstrates excellent accuracy (99%) in classifying different weather conditions from images. The model shows perfect performance on Rain and Snow classes, with slightly lower but still impressive results for Fog and Sunny classes.

This model can be deployed for various applications including automated weather monitoring systems, smart cameras that adjust settings based on weather conditions, and augmenting traditional weather forecasting systems with visual confirmation.
