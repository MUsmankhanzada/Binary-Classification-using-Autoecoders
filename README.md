# 🧠 Trolley Status Classification using Autoencoders

This project uses a **convolutional autoencoder** combined with **reconstruction error analysis** and **Kernel Density Estimation (KDE)** to classify images of trolleys as **empty (normal)** or **not empty (anomalous)**.

---

## 🎯 Project Goal

The goal is to build an unsupervised learning system that:
- Learns the structure of **empty trolley images**.
- Flags **non-empty (anomalous)** trolleys based on:
  - High reconstruction error **or**
  - Low KDE probability score.

---

## 🧰 Tools and Technologies Used

- **Python**
- **TensorFlow / Keras** – for building and training the autoencoder
- **OpenCV** – for image processing
- **NumPy, Pandas** – for data manipulation
- **Matplotlib** – for visualizations
- **Scikit-learn** – for KDE

---

## 📁 Dataset

The dataset contains trolley images categorized as empty or not empty (manually labeled for validation purposes).  
Due to size constraints, the dataset is hosted on **Google Drive**:

👉 [**Click here to access the dataset folder**](https://drive.google.com/drive/folders/14qtb_QxzKBdz9-ScAGUs_Mcx6z_D08J2?usp=sharing)

After downloading, place the dataset into a local `data/` directory for use with the notebook.

---

## 🏗️ Model Overview

The model consists of:
- A **Convolutional Autoencoder** trained only on images of empty trolleys.
- During inference:
  - Each test image is passed through the autoencoder.
  - The **reconstruction error** is calculated.
  - The **KDE score** is computed based on the latent (bottleneck) representation.

---

## 🧪 Anomaly Detection Logic

An image is flagged as **not empty (anomalous)** if:
- Its **reconstruction error is high** (above a chosen threshold) **or**
- Its **KDE score is low** (below a chosen threshold)

Otherwise, it's considered a **normal (empty)** image.

> Both thresholds were determined using **trial and error** based on qualitative evaluation of randomly selected test images.

---

## 🔧 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/trolley-autoencoder.git
   cd trolley-autoencoder
