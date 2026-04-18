#  Neural Network from Scratch (NumPy)

This project implements a fully functional neural network **from scratch using NumPy**, including forward pass, backpropagation, and training on the XOR problem.

The goal was not just to “make it work”, but to **understand how neural networks actually learn under the hood**—without relying on frameworks like PyTorch or TensorFlow.

---

## What This Project Covers

* Manual implementation of:

  * Forward propagation
  * Backpropagation (chain rule)
  * Gradient descent optimization
* Binary classification using:

  * Sigmoid activation (output layer)
  * ReLU activation (hidden layer)
* Cross-entropy loss with numerical stability
* Training on the **XOR problem** (non-linearly separable)

---

##  Problem: Why XOR?

The XOR dataset is a classic example that:

* ❌ Cannot be solved using a single-layer (linear) model
* ✅ Requires a hidden layer to learn non-linear patterns

This project demonstrates **why neural networks need depth**.

---

##  Model Architecture

```
Input (2) → Hidden Layer (4 neurons, ReLU) → Output (1 neuron, Sigmoid)
```

* Hidden layer extracts non-linear features
* Output layer predicts probability (0–1)

---

##  Key Components

### 🔹 Activation Functions

* **ReLU (Hidden Layer)**
  Introduces non-linearity and avoids vanishing gradients

* **Sigmoid (Output Layer)**
  Converts output into probability

---

### 🔹 Loss Function

* Binary Cross-Entropy:

  Handles probabilistic outputs and provides stable gradients

---

### 🔹 Optimization

* Gradient Descent
* Carefully tuned learning rate
* Weight initialization (He initialization for ReLU)

---

##  Training Results

The model successfully learns the XOR pattern:

```
Loss:
0.81 → 0.43 → 0.08 → 0.01 → ~0.0007
```

Final predictions:

```
[[~0],
 [~1],
 [~1],
 [~0]]
```

---
##  Key Learnings

This project provided deep insights into:

### 1. Model Capacity Matters

* A single neuron cannot solve XOR
* Hidden layers enable learning of non-linear relationships

### 2. Activation Functions Must Align with Task

* ReLU works well in hidden layers
* Sigmoid is required for binary classification output

### 3. Numerical Stability is Critical

* Log(0) issues handled using clipping
* Small implementation mistakes can cause NaNs

### 4. Optimization is Not Just Code

* Learning rate dramatically affects convergence
* Poor initialization slows learning

### 5. Debugging is a Core Skill

Common issues encountered:

* Incorrect sigmoid implementation
* Loss stuck at ~0.693 (random guessing)
* Gradient flow issues
* Shape mismatches

---

## 🛠️ Mistakes & Fixes

| Issue                            | Fix                              |
| -------------------------------- | -------------------------------- |
| Wrong sigmoid formula            | Corrected to standard definition |
| ReLU used in output layer        | Replaced with sigmoid            |
| Loss = NaN                       | Applied clipping for stability   |
| Slow convergence                 | Tuned learning rate              |
| Dead code in bias initialization | Removed unnecessary scaling      |

---

## 📌 Why This Project Matters

Most implementations rely on high-level libraries.
This project builds intuition for:

* How gradients flow through layers
* How weights actually update
* Why certain design choices matter

---

## 🚀 Next Steps

* Generalize to arbitrary number of layers
* Implement Softmax + multi-class classification
* Train on real datasets like MNIST
* Rebuild using PyTorch for comparison
* Move towards real-world AI systems (tokenization, embeddings, RAG)

---

## 📎 Tech Stack

* Python
* NumPy
* Google Colab

