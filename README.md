# Translation-Aware Ensemble Transformers for Multilingual Sentiment Analysis

## 📌 Project Overview

This repository presents a **translation-aware ensemble Transformer framework** for **multilingual sentiment analysis** of social media texts.  
The proposed system translates texts from multiple languages into English and applies an ensemble of Transformer-based sentiment classifiers to achieve robust and scalable sentiment prediction.

The framework is designed to address:
- Linguistic diversity across language families
- Limited annotated resources in low-resource languages
- Sentiment distortion caused by machine translation

The study focuses on **Arabic, Chinese, French, and Italian** texts and demonstrates that **ensemble learning combined with translation-based processing** significantly improves robustness and generalization.

---

## 🧠 What Does This Project Do?

- Collects and harmonizes multilingual sentiment datasets  
- Applies extensive text preprocessing and label normalization  
- Translates texts into English using:
  - **Google Translate (Neural Machine Translation)**
  - **LibreTranslate (Open-source NMT)**
- Fine-tunes multiple Transformer-based models:
  - **DeBERTa-v3**
  - **RoBERTa**
  - **BERTweet**
- Combines model predictions using **majority voting ensemble**
- Evaluates performance using **Stratified 5-Fold Cross Validation**
- Reports metrics such as Accuracy, Precision, Recall, F1-score, and Specificity

---

## 📊 Dataset Information

A balanced multilingual dataset of **12,000 samples** was constructed:
- **3,000 samples per language**
- Languages:
  - Arabic (ar)
  - Chinese (zh)
  - French (fr)
  - Italian (it)

All datasets were harmonized into a **three-class sentiment structure**:
- `NEG` (Negative)
- `NEUTRAL`
- `POS` (Positive)

---

## 📂 Third-Party Data Sources

The datasets used in this study are publicly available:

- **ASTD (Arabic Sentiment Tweets Dataset)**  
  https://github.com/mahmoudnabil/ASTD/tree/master/data

- **Amazon Reviews Multi – French**  
  https://huggingface.co/datasets/mteb/amazon_reviews_multi/tree/main/fr

- **Amazon Reviews Multi – Chinese**  
  https://huggingface.co/datasets/mteb/amazon_reviews_multi/tree/main/zh

- **SENTIPOLC-2016 (Italian Sentiment Dataset)**  
  https://github.com/evalita2016/data/tree/master/sentipolc

These datasets are used **strictly for research and academic purposes**.

---

## ⚙️ Code Description

The codebase includes:
- Dataset merging and label harmonization scripts
- Text cleaning and preprocessing pipelines
- Translation pipelines (Google Translate, LibreTranslate, mBART)
- Model fine-tuning scripts using Hugging Face Transformers
- Stratified 5-Fold Cross Validation
- Ensemble prediction with majority voting
- Performance evaluation and visualization scripts

---

## ▶️ How to Run / Usage

### 1️⃣ Install Dependencies

```bash
pip install -U transformers datasets evaluate accelerate torch pandas scikit-learn tqdm emoji seaborn matplotlib
```

### 2️⃣ Dataset Preparation
- Download datasets from the links above
- Place them in the appropriate directory structure
- Run preprocessing and label harmonization scripts

### 3️⃣ Translation
Choose one translation pipeline:
- Google Translate
- LibreTranslate
- mBART-50  

Intermediate checkpoints are saved periodically to avoid data loss.

### 4️⃣ Model Training
Fine-tune the following models:
- DeBERTa-v3
- RoBERTa
- BERTweet  

All models are trained using **Stratified 5-Fold Cross Validation**.

### 5️⃣ Ensemble Evaluation
- Load the best checkpoints from each model
- Apply majority voting for final predictions
- Generate evaluation metrics and confusion matrices

---

## 🧪 Materials & Methods

### 🖥️ Computational Environment

- **Operating System:** Linux (Google Colab environment)
- **CPU:** Intel Xeon (Colab backend)
- **GPU:** NVIDIA Tesla T4 / A100 (CUDA-enabled)
- **RAM:** 12–40 GB
- **Python Version:** 3.9+

**Frameworks and Libraries:**
- PyTorch
- Hugging Face Transformers
- Datasets
- Scikit-learn

---

## 🔬 Methodology Summary

1. **Data Collection & Harmonization**  
   Unified heterogeneous labels into a three-class sentiment structure

2. **Text Preprocessing**  
   Removal of noise (URLs, mentions, emojis, duplicates)

3. **Machine Translation**  
   Comparison of Google Translate and LibreTranslate

4. **Model Fine-Tuning**  
   DeBERTa-v3, RoBERTa, BERTweet

5. **Ensemble Learning**  
   Majority voting to reduce model and translation bias

6. **Evaluation**  
   Accuracy, Precision, Recall, F1-score, Specificity

---

## 📚 References & Citations

If you use this repository, please cite:

> **Kartoglu, C. S., Can, Ü., & Aslan, S.**  
> *Translation-Aware Ensemble Transformers for Multilingual Sentiment Analysis of Social Media Texts.*

Dataset references:
- ASTD: Nabil et al., EMNLP 2015  
- Amazon Reviews Multi: Keung et al., EMNLP 2020  
- SENTIPOLC-2016: Barbieri et al., EVALITA 2016  

---

## 📜 License

This project is licensed under the **MIT License**.

You are free to use, modify, and distribute this work for **research and educational purposes**, provided that proper attribution is given.

---

## ✉️ Contact

**Celal Şamil Kartoğlu**  
Malatya Turgut Ozal University  
Department of Software Engineering
