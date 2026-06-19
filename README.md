# Cat vs Dog Image Classification using CNN

## Project Overview

This project implements a Convolutional Neural Network (CNN) using TensorFlow and Keras to classify images of cats and dogs. The model is trained on a dataset containing labeled images of cats and dogs and can predict whether a given image belongs to either category.

---

## Features

* Image classification using Deep Learning
* Convolutional Neural Network (CNN) architecture
* TensorFlow/Keras implementation
* Dataset preprocessing and normalization
* Model training with validation
* Accuracy, Precision, and Recall evaluation
* Prediction on custom images
* Model saving for future use

---

## Dataset

Dataset used:

**Cat and Dog Dataset**

* Source: KaggleHub
* Classes:

  * Cat
  * Dog

Dataset Structure:

```
dataset/
│
├── training_set/
│   ├── cats/
│   └── dogs/
```

---

## Technologies Used

* Python
* TensorFlow
* Keras
* NumPy
* Matplotlib
* OpenCV
* KaggleHub

---

## Installation

### Clone Repository

```bash
git clone <repository-url>
cd cat-dog-classification
```

### Install Dependencies

```bash
pip install tensorflow numpy matplotlib opencv-python kagglehub
```

---

## Model Architecture

The CNN consists of:

1. Convolution Layer (16 Filters)
2. Max Pooling Layer
3. Convolution Layer (32 Filters)
4. Max Pooling Layer
5. Convolution Layer (16 Filters)
6. Max Pooling Layer
7. Flatten Layer
8. Dense Layer (256 Neurons)
9. Output Layer (Sigmoid Activation)

---

## Data Preprocessing

* Images resized to **256 × 256**
* Batch size: **32**
* Pixel values normalized from **0-255** to **0-1**
* Dataset split:

  * 70% Training
  * 20% Validation
  * 10% Testing

---

## Training

Compile Model:

```python
model.compile(
    optimizer='adam',
    loss='binary_crossentropy',
    metrics=['accuracy']
)
```

Train Model:

```python
history = model.fit(
    train,
    epochs=25,
    validation_data=val
)
```

---

## Evaluation Metrics

The following metrics are used:

* Accuracy
* Precision
* Recall

Example:

```python
from tensorflow.keras.metrics import Precision, Recall, BinaryAccuracy
```

---

## Prediction

Predict on a custom image:

```python
img = cv2.imread('image.jpg')
resize = tf.image.resize(img, (256,256))

prediction = model.predict(
    np.expand_dims(resize/255, 0)
)
```

Output:

```text
Dog
```

or

```text
Cat
```

---

## Saving the Model

```python
model.save('image_classifier_models.h5')
```

---

## Results

The model achieves good performance in distinguishing between cats and dogs using CNN-based image classification. Training and validation graphs are plotted to monitor:

* Loss
* Accuracy

---

## Future Improvements

* Use Data Augmentation
* Apply Transfer Learning (VGG16, ResNet50, MobileNet)
* Hyperparameter Tuning
* Deploy as a Web Application
* Real-time Prediction using Webcam

---

## Author

**Radhil V**

B.Tech Information Technology
Cochin University of Science and Technology (CUSAT)

---
