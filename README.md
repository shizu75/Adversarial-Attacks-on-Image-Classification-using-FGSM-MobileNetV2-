# Adversarial Attacks on Image Classification using FGSM (MobileNetV2)

## Overview
This project demonstrates **adversarial attacks on deep neural networks** using the **Fast Gradient Sign Method (FGSM)**. A pretrained **MobileNetV2** model (trained on ImageNet) is used to show how imperceptible perturbations can significantly alter model predictions, highlighting vulnerabilities in modern computer vision systems.

## Motivation
Deep learning models are widely deployed in safety-critical applications such as autonomous vehicles, medical imaging, and surveillance systems. However, these models are susceptible to adversarial attacks—small, human-imperceptible changes to inputs that cause incorrect predictions. This project explores such vulnerabilities using a well-established attack method.

---

## Model Architecture
- **Backbone Model:** MobileNetV2
- **Dataset:** ImageNet (pretrained weights)
- **Framework:** TensorFlow / Keras
- **Training:** Frozen pretrained model (no retraining)

---

## Methodology

### 1. Image Preprocessing
- Resize input image to `224 × 224`
- Normalize pixel values using MobileNetV2 preprocessing
- Add batch dimension

### 2. Baseline Prediction
- Perform classification on a clean input image
- Extract top-1 predicted class and confidence

### 3. Adversarial Pattern Generation (FGSM)
- Compute gradient of loss with respect to input image
- Apply sign of gradient to generate perturbations
- Scale perturbations using epsilon (ε)


### 4. Adversarial Evaluation
- Apply increasing ε values
- Visualize confidence degradation
- Observe label changes under perturbation

---

## Key Components

- **Pretrained Model:** `tf.keras.applications.MobileNetV2`
- **Loss Function:** Categorical Cross-Entropy
- **Attack Method:** Fast Gradient Sign Method (FGSM)
- **Visualization:** Matplotlib

---

## Results & Observations
- Even very small perturbations (ε ≤ 0.01) reduce model confidence
- Higher ε values cause complete misclassification
- Perturbations are visually imperceptible to humans
- Demonstrates critical robustness issues in CNNs

---

## Example Output
- Original image classification with high confidence
- Gradual confidence drop as epsilon increases
- Final adversarial image classified incorrectly

---

## Applications
- Model robustness evaluation
- Adversarial defense research
- Security testing of vision systems
- Academic demonstrations of adversarial ML

---

## Limitations
- Single attack method (FGSM)
- Single image evaluation
- No adversarial training applied

---

## Future Improvements
- Implement PGD and CW attacks
- Add adversarial training defense
- Evaluate multiple ImageNet classes
- Quantitative robustness metrics

---

## Technologies Used
- Python
- TensorFlow / Keras
- NumPy
- Matplotlib

---

## References
- Goodfellow et al., *Explaining and Harnessing Adversarial Examples*
- TensorFlow Adversarial ML Tutorials
- ImageNet Dataset

---

## Author
**Soban Saeed**  
AI | Computer Vision | Adversarial Machine Learning

---

> *This project is intended for academic, research, and educational purposes.*

