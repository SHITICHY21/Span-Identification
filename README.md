# 🌐 UNLP-2025: Manipulation Span Identification  
🔍 Detecting Manipulative Text in Ukrainian / Russian Telegram Posts

This repository contains code and experiments for the **UNLP-2025 Shared Task**, focused on identifying exact manipulative text spans inside Telegram posts.

## 🎯 Task Objective

Given a Telegram post, the model must:

> **Locate exact character spans of manipulative text — not just classify whether manipulation exists.**

Unlike traditional classification tasks, this challenge focuses on sequence labeling—predicting span boundaries, not just determining whether the text is manipulative.

## 🛠️ Pipeline Overview

### 🧹 1. Preprocessing
- Clean raw text  
- Parse `(start, end)` span lists  
- Tokenize posts using **XLM-RoBERTa**  
- Convert spans → **BIO token labels**

### 🤖 2. Model
- **XLM-RoBERTa-Large + BiLSTM Head**  
- Token-level classification  
- Multilingual (Ukrainian + Russian)  
- Effective boundary detection for manipulative sequences  

### 🏋️ 3. Training
- **AdamW** optimizer  
- **FP16** mixed precision  
- **Gradient accumulation**  
- **Early stopping** for stability  

## 🚀 Inference & Submission

Run predictions:
```bash
python inference.py
```
Output saved as:
```
final_submission.csv
```
📝 Submission Format
```
id,trigger_words
123abc,[(27,63),(90,183)]
```

## 👥 Contributors

> 🧑‍💻 **Shiti Chowdhury**
> 🧑‍💻 **Adnan Faisal**

⭐ Support
If you like this project, consider giving the repository a star ⭐ on GitHub!
