# 🇮🇩 Language Classifier: Indonesian, Javanese, and Sundanese Speech Recognition

**Group 5 Final Project — Audio Data Recognition**  
*Department of Computer Science and Electronics, Universitas Gadjah Mada*

## 📌 Overview

This project classifies spoken audio in **Indonesian**, **Javanese**, and **Sundanese** using traditional acoustic features and machine learning techniques. It aims to enhance the inclusivity of speech recognition systems in linguistically diverse regions like Indonesia.

## 🔍 Problem Statement

Modern speech recognition systems often underperform in multi-language environments. This project builds a lightweight system to identify three major Indonesian languages by analyzing core speech features.

## 🛠️ Methodology

### 1. Data Acquisition
- **Datasets Used**:
  - [OpenSLR 35: Javanese Corpus](https://www.openslr.org/35/)
  - [OpenSLR 36: Sundanese Corpus](https://www.openslr.org/36/)
  - [Nexdata: 359-Hours Indonesian Speech Corpus](https://github.com/Nexdata-AI/359-Hours-Indonesian-Speech-Data-by-Mobile-Phone_Reading)

### 2. Preprocessing
- Resampled all audio to **16 kHz**
- Removed low-pitch (silent) segments
- Skipped unreadable/corrupt files automatically

### 3. Feature Extraction
Extracted a total of **35+ features** per utterance:
- **Zero Crossing Rate (ZCR)**: mean, std
- **Short-Time Energy (STE)**: mean, std
- **Pitch Frequency**: mean, std, min, max
- **Voiced Frame Ratio**
- **MFCCs (Mel-Frequency Cepstral Coefficients)**: 13 coefficients × (mean, std)

### 4. Classification Models
Used four machine learning models:
- Support Vector Machine (SVM)
- Decision Tree
- Random Forest
- XGBoost

Split data into **70% training**, **30% testing** using stratified sampling.

### 5. Evaluation Metrics
- Accuracy
- Precision
- Recall
- F1-Score

## 📊 Results

| Model          | Accuracy | F1-Score (Macro) |
|----------------|----------|------------------|
| **SVM**        | **88.89%** | **0.89**         |
| Random Forest  | 84.44%   | 0.84             |
| XGBoost        | 76.67%   | 0.77             |
| Decision Tree  | 75.56%   | 0.76             |

SVM showed the most consistent and accurate performance.

## ⚠️ Limitations
- Limited training data volume and dialect diversity
- Less effective in noisy or spontaneous speech
- Feature-based method lacks the nuance of deep learning

## 🔮 Future Work
- Use more diverse and real-world datasets
- Apply deep learning (e.g., CNNs, RNNs)
- Explore phoneme-level language modeling
- Improve model robustness in mixed-language and noisy contexts


## 📚 References
- Hanifa et al., “Voiced and Unvoiced Separation in Malay Speech”
- Madiha et al., “Short-time Energy, ZCR, and Autocorrelation for Speech Signals”
- OpenSLR and Nexdata datasets

## 👥 Contributors
- Satwika Nino Wandhana - 23/516202/PA/22066
- Michael Satpelin Williamtu - 23/517103/PA/22151
- Andi Fayza Maharani - 23/516238/PA/22074
- Mario Aloysius Lukman - 23/516320/PA/22091
- Muhammad Razan Alamudi - 3/511396/PA/21784

