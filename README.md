# 🎧 Urban Soundscape Modeling using UrbanSound8K 🌆

This project focuses on **urban sound classification** using machine learning and deep learning techniques.  
The aim is to identify *what types of sounds* dominate urban environments rather than only measuring noise levels, which has strong implications for **public health**, **urban planning**, and **smart cities**.

---

## 📌 Project Overview

Urban noise is a major contributor to stress and health issues.  
This project uses the **UrbanSound8K dataset** to classify short audio clips into common urban sound categories such as traffic, drilling, street music, sirens, and human activities.

The work compares **classical ML models**, **deep learning CNN architectures**, and **AutoML** approaches.

---

## 🎼 Dataset

- **Dataset:** UrbanSound8K  
- **Total Samples:** 8,732 audio clips  
- **Classes (10):**
  - Air Conditioner
  - Car Horn
  - Children Playing
  - Dog Bark
  - Drilling
  - Engine Idling
  - Gun Shot
  - Jackhammer
  - Siren
  - Street Music

🔗 **UrbanSound8K Dataset:**  https://urbansounddataset.weebly.com/urbansound8k.html

---

## 🧠 Feature Engineering

- **MFCCs (Mean & Standard Deviation)** for classical ML models  
- **MFCC Sequences** for 1D CNN  
- **Mel-Spectrogram Images (128×128)** for 2D CNN  

Audio preprocessing was done using `librosa`.

---

## 🤖 Models Implemented

### Classical Machine Learning
- Logistic Regression
- Support Vector Machine (RBF Kernel)
- Random Forest (Optuna tuned)
- Multi-Layer Perceptron (MLP)

### Deep Learning
- 1D CNN on MFCC sequences
- **2D CNN on Mel-Spectrograms** ⭐

### AutoML
- AutoGluon (Tabular)

---

## 📊 Results Summary

| Model | Accuracy |
|------|----------|
| Logistic Regression | ~75% |
| Random Forest (Optuna) | ~90% |
| MLP | ~93–94% |
| SVM (RBF) | ~94% |
| AutoGluon | ~94–95% |
| **2D CNN (Mel-Spectrogram)** | **~96% ✅** |

🎯 **Best Performance:** 2D CNN using mel-spectrogram images.

---

## 🧪 Key Observations

- **Spectrogram-based CNNs** capture rich **time–frequency representations** of audio signals and consistently outperform models trained only on MFCC statistical features.
- Most **misclassifications** occur between **acoustically similar sound classes**, such as *drilling* vs *engine idling* or *street music* vs *children playing*.
- **AutoML frameworks** provide strong baseline performance with minimal manual tuning, making them effective for rapid prototyping and benchmarking.

---

## 🚀 Future Improvements

- Implement **Transformer-based audio models** such as **Audio Spectrogram Transformer (AST)** or **wav2vec 2.0** for improved contextual understanding.
- Extend analysis to **cross-city and cross-environment datasets** to study geographic noise patterns.
- Deploy the trained model as a **REST API or interactive dashboard** for real-time urban sound classification.
- Perform **temporal and spatial noise trend analysis** to support long-term urban planning and public health insights.
