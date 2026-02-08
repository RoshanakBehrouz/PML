
# MNIST Anomaly & Shift Detection

This project explores the intersection of classification and generative modeling to detect data shifts and anomalies. It implements a **CNN Digit Classifier**, a **Convolutional Autoencoder (CAE)**, and various **Variational Autoencoders (VAEs)** to analyze how different architectures perceive and reconstruct out-of-distribution (OOD) data.

## 🚀 Project Overview

The core objective is to determine how well generative models can act as "distributional monitors" for a standard classifier. By monitoring **Reconstruction Loss** and **Latent Space Drift**, we can identify when a model is encountering data it was not trained to handle.

### Included Models

* **CNN Classifier:** Baseline for predictive accuracy.
* **Convolutional Autoencoder (CAE):** Deterministic reconstruction used for anomaly detection baseline.
* **FC-VAE:** Fully connected Variational Autoencoder to assess linear vs. spatial latent structures.
* **Conv-VAE (Beta=1):** Standard convolutional VAE for high-fidelity reconstruction.
* **Conv-VAE (Beta=4):** Highly regularized VAE to encourage latent disentanglement.

---

## 📊 Data Shifts & Perturbations

Models are evaluated on five test sets to simulate real-world data degradation:

* **Standard:** Clean MNIST test data.
* **Rotated30:** Images rotated by  degrees.
* **Noisy:** Addition of Gaussian noise ().
* **Occluded:**  pixel patches removed from the image.
* **Label Shift:** Evaluation on a subset containing only digits 0–4.

---

## 📈 Key Results

### Anomaly Detection (ROC-AUC)

Using reconstruction loss as an anomaly score, the models demonstrated varying sensitivities to data shifts:

* **Noisy Data:** All models achieved a perfect **1.000 AUC**, showing extreme sensitivity to pixel-level noise.
* **Rotated Data:** The **CAE** was the top performer with an **0.691 AUC**, followed closely by the Conv-VAE at 0.685.
* **Occluded Data:** The **Conv-VAE (Beta=1)** led with a **0.662 AUC**.

### The -VAE Trade-off

Beta=1 **:** Prioritizes reconstruction quality, resulting in sharper images but higher KL Divergence.
Beta=4 **:** Prioritizes latent regularization, resulting in a smoother, more standard-normal latent space at the cost of blurrier reconstructions.

---
