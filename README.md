# Hybrid Penalized Regression–MLP Models for Diabetes Prediction  
**EE782 – Advanced Topics in Machine Learning (IIT Bombay)**  
**Author:** Mithra D K  

This repository contains all code, analysis, and the final project report for the study:  
**“Hybrid Penalized Regression–MLP Models for Outcome Prediction in HDLSS Health Data.”**  
The project evaluates whether combining penalized linear models with a compact multilayer perceptron can improve diabetes prediction performance on the NHANES health survey dataset.

---

## Project Overview  
High-dimensional low-sample-size (HDLSS) conditions commonly appear in health analytics.  
Pure linear models offer stability and interpretability, whereas neural networks capture nonlinear patterns but tend to overfit when the number of features is large.

This project develops and evaluates:

- **L1 Logistic Regression (LASSO)**
- **L2 Logistic Regression**
- **Full-Feature MLP**
- **Hybrid Penalized Regression → MLP Top-k Architecture**

A refined feature-selection strategy (top-k per fold) significantly stabilizes performance and improves recall/F1 compared to the initial prototype.

---

## 📊 Dataset  
The analysis uses **NHANES** (National Health and Nutrition Examination Survey) combining:

- demographics (`demo.csv`)
- examinations (`exam.csv`)
- laboratory results (`labs.csv`)
- medications (`medications.csv`)
- questionnaires (`questionnaire.csv`)

Final processed dataset:  
- **N ≈ 4863 samples**  
- **P ≈ 1657 features**

Outcome label: diabetes status using fasting glucose, HbA1c, and self-reported diagnosis.

> Raw NHANES files are not included in this repo.  
> Instructions to download are provided in `data/README.md`.

---

## Models Implemented

### **1. Penalized Regression Baselines**
- LASSO (L1)  
- Ridge (L2)  
Provides sparse coefficients and acts as the feature-selection backbone.

### **2. Full-Feature MLP**
Two-layer neural network trained on all processed features with:
- ReLU activations  
- early stopping  
- L2 regularization  

### **3. Hybrid Penalized Regression → MLP**
A controlled, stable hybrid pipeline consisting of:
1. **Top-k feature selection** using:  
   - absolute L1 coefficients  
   - elastic net weights  
   - mutual information  
2. A deeper MLP on the reduced feature subset  
3. Unified 3-fold cross-validation  

---

## Results Summary

### **Initial Prototype (Unstable L1 Selection)**  
- High AUC but feature counts varied widely (430–477 per fold)  
- Hybrid underperformed the L1 baseline  

### **Refined Hybrid Pipeline**  
A fixed **k = 100** top features per fold produced:

- Improved recall  
- Stronger F1-score  
- AUC comparable to L1 baseline  
- Significantly higher stability  

Detailed metrics are available in the report (`report/EE782_Final_Project.pdf`).

---

## Repository Structure


