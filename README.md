# 🐶🐱 Dog vs Cat Classifier (Transfer Learning)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/dog_vs_cat_classifier/blob/main/Dog_vs_Cat_Classifier.ipynb)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)
![Transfer Learning](https://img.shields.io/badge/Architecture-MobileNetV2-brightgreen)

A computer vision project that classifies images of dogs and cats with high accuracy. Rather than training a Convolutional Neural Network (CNN) from scratch, this project utilizes **Transfer Learning** via Google's `MobileNetV2` architecture to achieve >95% accuracy in a fraction of the standard training time.

## 🚀 The Project Overview

Training deep image classification models from scratch requires massive computational resources and hundreds of thousands of images to prevent overfitting. This project demonstrates modern deep learning efficiency by utilizing a pre-trained feature extractor.

### Key Features
* **Transfer Learning:** Leverages `MobileNetV2` (pre-trained on the ImageNet dataset) as the base model, freezing its convolutional layers to retain its learned feature extraction capabilities (edges, textures, shapes).
* **Custom Classification Head:** Implements a custom dense layer pipeline with Global Average Pooling and Dropout for binary classification (`0 = Cat`, `1 = Dog`).
* **Interactive UI:** Features a Gradio-powered web interface allowing users to upload custom images for real-time inference.

## 🛠️ Tech Stack
* **Deep Learning:** TensorFlow, Keras, Transfer Learning
* **Data Ingestion:** TensorFlow Datasets (`tfds`)
* **Computer Vision:** OpenCV (`cv2`)
* **User Interface:** Gradio

## 📸 Preview
*(Drag and drop your screenshot of the Gradio app here!)*

## 🧠 The Architecture Pipeline Explained

1. **Data Pipeline:** The official Microsoft Dogs vs. Cats dataset is streamed directly into memory using `tfds`. The images are dynamically resized to 224x224 and normalized to a range of [-1.0, 1.0].
2. **Feature Extraction:** The image passes through `MobileNetV2`. The pre-trained weights identify complex patterns (like fur, eyes, and ears) without needing to be retrained.
3. **Classification:** A custom neural network head analyzes the extracted features. Using the Binary Crossentropy loss function and a Sigmoid activation, it outputs a probability score determining the species.

## 💻 How to Run Locally

1. Clone this repository:
   ```bash
   git clone https://github.com/nikamsudarshan/dog_vs_cat_classifier.git
   ```
2. Install dependencies:
  ```bash
  pip install -r requirements.txt
  ```
3. Open the notebook:
  ```bash 
  jupyter notebook Dog_vs_Cat_Classifier.ipynb
  ```
Author: Sudarshan Nikam
