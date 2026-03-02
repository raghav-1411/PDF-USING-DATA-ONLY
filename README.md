# 📊 Learning Probability Density Function using GAN

**Generative modeling of an unknown transformed distribution using adversarial learning**

---

## 🔍 Project Overview

This project aims to learn the **probability density function (PDF)** of a transformed random variable using only data samples.

Instead of assuming a known parametric distribution (Gaussian, Exponential, etc.), a **Generative Adversarial Network (GAN)** is trained to implicitly model the distribution. The learned distribution is then visualized using **Kernel Density Estimation (KDE)**.

---

## 📁 Dataset

- **Dataset:** India Air Quality Data  
- **Feature Used:** NO₂ concentration  
- **Source:** Kaggle  
- **Link:** https://www.kaggle.com/datasets/shrutibhargava94/india-air-quality-data  
- **Samples Used:** All valid NO₂ observations after removing missing values  

The NO₂ concentration values are treated as the original random variable **x**.

---

## 🔄 Transformation

Each data point is transformed using:

z = x + a_r sin(b_r x)

Where:

a_r = 0.5 (r mod 7)  
b_r = 0.3 ((r mod 5) + 1)

---

## 📌 My Parameters

- **Roll Number:** 102303580  
- **a_r:** 0.5  
- **b_r:** 0.3  

The transformed variable **z** is assumed to be sampled from an unknown distribution.

---

## 🧠 GAN Architecture

### 🎯 Generator
- Input: 1D Gaussian noise N(0,1)
- Fully connected neural network
- Activation: ReLU
- Output: 1D generated sample

### 🕵️ Discriminator
- Input: Real or generated sample
- Fully connected neural network
- Activation: LeakyReLU
- Output: Probability (Real / Fake)

---

## ⚙️ Training Setup

| Parameter | Value |
|-----------|------|
| Loss Function | Binary Cross Entropy |
| Optimizer | Adam |
| Epochs | 3000 |
| Batch Size | 128 |
| Noise Dimension | 10 |
| Device | CPU / GPU (auto-detected) |

---

## 📈 PDF Estimation

After GAN training:

1. Synthetic samples are generated using the trained generator.
2. Kernel Density Estimation (KDE) is applied.
3. The estimated probability density function is plotted.

---

## 📊 Final Estimated PDF

![Estimated PDF](outputs/pdf_estimate.png)

---

## 🔎 Results & Observations

### 📌 Mode Coverage
The generator captures major density modes of the transformed distribution. Minor deviations appear in sparse regions due to adversarial learning limitations.

### 📌 Training Stability
- Initial oscillations observed during early training.
- Loss curves stabilize after sufficient epochs.
- No severe mode collapse detected.

### 📌 Distribution Quality
- Generated samples closely resemble the empirical distribution.
- KDE produces a smooth density estimate.
- Small stochastic outliers may appear.

---

## 🚀 Key Learnings

- GANs can approximate unknown probability distributions without analytical assumptions.
- Data normalization improves GAN convergence.
- Balance between generator and discriminator is crucial.
- KDE provides smooth visualization of learned densities.

---

## 🛠 Technologies Used

- Python
- PyTorch
- NumPy
- Pandas
- Matplotlib
- SciPy

---



