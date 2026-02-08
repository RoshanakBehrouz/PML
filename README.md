

# MNIST Anomaly & Shift Detection

This project evaluates the robustness of discriminative and generative models—ranging from CNNs to VAEs—against data perturbations on the MNIST dataset.

##  Project Overview

The goal is to analyze how different architectures perceive and reconstruct out-of-distribution (OOD) data. We demonstrate that generative models serve as effective anomaly detectors via reconstruction loss.

### Included Models

* **CNN Digit Classifier:** Evaluates predictive stability.
* **Convolutional Autoencoder (CAE):** Evaluates deterministic reconstruction.
* **FC-VAE:** Assesses linear vs. non-linear latent structures.
* **Conv-VAE ():** Standard generative modeling.
* **Conv-VAE ():** Disentangled latent modeling with enhanced regularization.

## 📊 Data Shifts & Perturbations

Models are tested against:

* **Standard:** Clean MNIST test data.
* **Rotated30:** Random rotation .
* **Noisy:** Gaussian Noise ().
* **Occluded:**  black patches.
* **Label Shift:** Evaluation on digits 0–4 only.

##  Key Findings

* **Anomaly Detection:** All models achieved a perfect **1.000 AUC** for "Noisy" data.
* **Structural Sensitivity:** The **CAE** proved most sensitive to rotation with the highest AUC of **0.691**.
* **The  Trade-off:**  prioritizes reconstruction quality, while  prioritizes latent regularization (lower KL divergence).

---

### 3. Save and Upload

Once you have pasted the text:

1. **Save** the file.
2. If you are using the **GitHub Website**: Open your repository, click "Add file" -> "Upload files," and drag your `README.md` there.
3. If you are using the **Terminal**:
```bash
git add README.md
git commit -m "Add project documentation"
git push origin main

```



