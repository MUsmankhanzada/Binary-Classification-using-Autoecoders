# 🧠 Trolley Status Classification using Autoencoders

This project uses **autoencoders** for a **binary image classification** task to determine whether a **trolley is empty or not** based on camera images.

## 🎯 Project Goal

The primary objective is to train an unsupervised deep learning model that can:
- Learn normal patterns from images of **empty trolleys**.
- Detect **anomalies** (i.e., non-empty trolleys) by reconstruction error.
- Classify images into two categories:
  - `0` → Trolley is **empty**
  - `1` → Trolley is **not empty**

---

## 🧰 Tools and Technologies Used

- **Python**
- **TensorFlow / Keras** – for building and training the autoencoder
- **OpenCV** – for image preprocessing
- **NumPy & Pandas** – for data handling
- **Matplotlib** – for visualizations
- **Scikit-learn** – for evaluation (e.g., ROC, confusion matrix)

---

## 📁 Dataset

The dataset contains images of trolleys under different conditions.  
Due to size constraints, the dataset is hosted on **Google Drive**:

👉 [**Click here to access the dataset folder**](https://drive.google.com/drive/folders/14qtb_QxzKBdz9-ScAGUs_Mcx6z_D08J2?usp=sharing)

- The dataset should be downloaded and placed in a local folder (e.g., `./data/`).
- Images are preprocessed (resized, normalized) before being fed into the model.

---

## 🏗️ Model Overview

The model architecture is a **convolutional autoencoder**, consisting of:

- **Encoder**: Compresses the input image to a low-dimensional representation.
- **Decoder**: Reconstructs the image from this compressed form.
- The **reconstruction error** is used to flag abnormal (non-empty) images.

---

## 📊 Evaluation

- Images with reconstruction errors **above a threshold** are classified as "not empty".
- Evaluation metrics include:
  - ROC curve
  - Confusion matrix
  - Accuracy, precision, recall, F1-score

---

## 🚀 Getting Started

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/trolley-autoencoder.git
   cd trolley-autoencoder
