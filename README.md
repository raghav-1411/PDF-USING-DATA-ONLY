📊 Learning Probability Density Function using GAN

Generative modeling of an unknown transformed distribution using adversarial learning.

🔍 Project Overview

This project aims to learn the probability density function (PDF) of a transformed random variable using only data samples.

Instead of assuming a known parametric distribution (Gaussian, Exponential, etc.), a Generative Adversarial Network (GAN) is trained to implicitly model the distribution.

The learned distribution is then visualized using Kernel Density Estimation (KDE).

📁 Dataset

Dataset: India Air Quality Data

Feature Used: NO₂ concentration

Source: Kaggle

Samples Used: __________

The NO₂ concentration values are treated as the original random variable 
𝑥
x.

🔄 Transformation

Each data point is transformed as:

𝑧
=
𝑥
+
𝑎
𝑟
sin
⁡
(
𝑏
𝑟
𝑥
)
z=x+a
r
	​

sin(b
r
	​

x)

Where:

𝑎
𝑟
=
0.5
(
𝑟
 
m
o
d
 
7
)
a
r
	​

=0.5(rmod7)
𝑏
𝑟
=
0.3
(
(
𝑟
 
m
o
d
 
5
)
+
1
)
b
r
	​

=0.3((rmod5)+1)
📌 My Parameters

Roll Number: __________

a_r: __________

b_r: __________

The transformed variable 
𝑧
z is assumed to be sampled from an unknown distribution.

🧠 GAN Architecture
🎯 Generator

Input: 1D Gaussian noise 
𝑁
(
0
,
1
)
N(0,1)

Fully connected layers

Activation: ReLU

Output: 1D generated sample

🕵️ Discriminator

Input: Real or generated sample

Fully connected layers

Activation: LeakyReLU

Output: Probability (Real / Fake)

⚙️ Training Setup

Loss Function: Binary Cross Entropy

Optimizer: Adam

Epochs: __________

Batch Size: __________

Device: CPU / GPU

📈 PDF Estimation

After training:

A large number of synthetic samples were generated.

Kernel Density Estimation (KDE) was applied.

The estimated probability density function was plotted.

📊 Final Estimated PDF

(Insert your plot image here)

🔎 Results & Observations
📌 Mode Coverage

Did the generator capture all density peaks?

Any missing regions?

📌 Training Stability

Loss convergence behavior

Oscillations or instability observed?

Evidence of mode collapse?

📌 Distribution Quality

Similarity between real and generated distributions

Smoothness of KDE

Outliers or artifacts

(Write this section carefully in your own analysis tone.)

🚀 Key Learnings

GANs can approximate complex distributions without assuming analytical form.

Proper normalization improves training stability.

Adversarial balance is crucial for stable convergence.

KDE provides smooth visualization of learned density.

🛠 Technologies Used

Python

PyTorch

NumPy

Pandas

Matplotlib

SciPy

📂 Project Structure
