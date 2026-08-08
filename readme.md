# NeuroNav — Single-Layer Perceptron from Scratch

> A foundational machine learning project implementing a **single-layer perceptron from scratch** for binary classification of Forest and Urban areas using satellite-inspired features.

## Overview

This project explores the fundamentals of binary classification by building a single-layer perceptron without relying on a high-level machine learning classifier.

The problem is inspired by **NeuroNav**, a satellite-analysis scenario where the goal is to distinguish between:

- 🌳 **Forest**
- 🏙️ **Urban**

using two features:

- **Greenness Index**
- **Building Density**

The main objective of this project is not only to obtain predictions, but to understand what happens internally during the learning process—from the forward pass and activation function to loss calculation, gradient computation, parameter updates, and decision-boundary formation.

---

## Learning Objectives

This project focuses on understanding the mathematical and computational foundations of a basic neural network.

Key objectives include:

- Understanding activation functions
- Understanding Sigmoid for binary classification
- Implementing Binary Cross-Entropy loss
- Implementing a perceptron forward pass
- Implementing gradient descent manually
- Training model parameters from scratch
- Visualizing the learned decision boundary
- Understanding the limitations of linear classifiers

---

## Problem Formulation

The task is formulated as a **binary classification problem**:

```text
Input Features
    │
    ├── Greenness Index
    └── Building Density
            │
            ▼
    Single-Layer Perceptron
            │
            ▼
         Sigmoid
            │
            ▼
    Probability of Class 1
            │
      ┌─────┴─────┐
      ▼           ▼
   Urban        Forest
   Class 0      Class 1
```

---

## Dataset

The dataset is synthetically generated using `make_blobs` to create:

- **200 samples**
- **2 input features**
- **2 classes**
- **2 centers**
- `random_state=42`

The two features represent:

| Feature | Description |
|---|---|
| Greenness Index | Represents the level of vegetation |
| Building Density | Represents the concentration of buildings |

The features are normalized before training to provide a more stable learning process.

---

## Model Architecture

The model is intentionally kept simple:

```text
X
│
▼
Linear Combination
Z = XW + b
│
▼
Sigmoid
A = σ(Z)
│
▼
Prediction
```

The Sigmoid function is:

\[
\sigma(z) = \frac{1}{1 + e^{-z}}
\]

Since its output lies between 0 and 1, it is suitable for interpreting the model output as a probability in a binary classification problem.

---

## Loss Function

The model uses **Binary Cross-Entropy (BCE)** to measure the difference between the predicted probabilities and the actual labels.

\[
L =
-\frac{1}{m}
\sum
\left[
y\log(\hat{y}) +
(1-y)\log(1-\hat{y})
\right]
\]

The objective of training is to minimize this loss.

---

## Training from Scratch

Instead of using a pre-built classifier, the learning process is implemented manually using gradient descent.

The training loop follows:

```text
Forward Pass
     ↓
Prediction
     ↓
Calculate Loss
     ↓
Calculate Gradients
     ↓
Update Weights & Bias
     ↓
Repeat
```

### Training Configuration

| Parameter | Value |
|---|---:|
| Epochs | 500 |
| Learning Rate | 0.5 |
| Model | Single-Layer Perceptron |
| Activation | Sigmoid |
| Loss | Binary Cross-Entropy |

The weight and bias updates follow:

\[
W := W-\alpha dW
\]

\[
b := b-\alpha db
\]

where \(\alpha\) is the learning rate.

---

## Decision Boundary

After training, the learned weights and bias are used to visualize the model's decision boundary.

Because a single-layer perceptron is a **linear classifier**, its decision boundary is linear.

For this dataset, the two classes are clearly separated, allowing the perceptron to learn an effective boundary between Forest and Urban regions.

```text
Forest Region
      🌳 🌳 🌳
      🌳 🌳 🌳
--------------------  ← Learned Decision Boundary
      🏙️ 🏙️ 🏙️
      🏙️ 🏙️ 🏙️
Urban Region
```

---

## Key Concepts Demonstrated

### 1. Activation Function

Activation functions transform the output of a neuron and allow neural networks to model relationships beyond a simple linear transformation.

### 2. Sigmoid

Maps the linear output into the range `[0, 1]`, making it useful for binary classification.

### 3. Binary Cross-Entropy

Measures how well the predicted probabilities match the true binary labels.

### 4. Gradient Descent

Iteratively updates the model parameters to minimize the loss.

### 5. Decision Boundary

Represents the boundary learned by the classifier between the two classes.

---

## Important Limitation

A single-layer perceptron can only learn a **linear decision boundary**.

Therefore, if the classes are not linearly separable, a single perceptron cannot represent the required decision boundary effectively.

This limitation provides an important motivation for studying deeper neural networks and nonlinear architectures.

---

## Project Structure

```text
.
├── Assignment_01(1).ipynb
├── README.md
└── requirements.txt
```

---

## Technologies Used

- Python
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook

---

## What I Learned

This project helped me move beyond simply using machine learning libraries and understand the internal mechanics of a basic neural model.

In particular, I gained practical understanding of:

- Forward propagation
- Activation functions
- Loss functions
- Gradient computation
- Gradient descent
- Parameter optimization
- Linear decision boundaries
- Limitations of single-layer models

The project also strengthened my understanding of how mathematical concepts translate into an executable machine learning training process.

---

## Future Work

As a natural extension of this project, the following experiments would be interesting:

- Introduce non-linearly separable datasets
- Compare the perceptron with multi-layer neural networks
- Implement ReLU and other activation functions
- Investigate different optimization strategies
- Analyze convergence under different learning rates
- Compare model behavior under noisy and overlapping data
- Extend the experiment toward real satellite imagery

---

## Academic Context

This project was completed as part of a Machine Learning coursework assignment and is intended to demonstrate a fundamental understanding of neural-network-based classification through implementation from first principles.

Rather than treating the perceptron as a black-box model, the project focuses on understanding the relationship between:

**Mathematics → Algorithm → Implementation → Learning Behavior**

---

## Author

### Md. Maidul Islam

**B.Sc. in Computer Science & Engineering**  
China University of Petroleum, Beijing

**Research Interests**

- Machine Learning
- Artificial Intelligence
- Data Mining
- Pattern Recognition
- Healthcare AI
- Applied Machine Learning

---

## Repository Purpose

This repository is maintained as part of my academic and machine learning portfolio, documenting practical experiments and implementations that support my preparation for future **MSc/PhD-level study and research in Artificial Intelligence and Machine Learning**.

> **Learning the mathematics behind the model, implementing the algorithm, and understanding why it works — rather than treating machine learning as a black box.**