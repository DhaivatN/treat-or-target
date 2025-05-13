# 🎯 treat-or-target  
**Machine learning meets causal targeting in digital marketing.**

[![Python](https://img.shields.io/badge/Python-3.10-blue.svg)](https://www.python.org/)  
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](./LICENSE)  
[![Built with Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](./notebook/Uplift_Model.ipynb)

---

## 🧠 Overview

Traditional classifiers predict who will convert — but not *why*.  
This project applies **uplift modeling** on the Criteo Uplift Dataset to estimate **incremental conversion impact**: identifying users who respond *because of* treatment.

We simulate uplift-based marketing using three modeling strategies:

- ✅ **Solo Model (SM)** – one model, combined data  
- ✅ **Two Models (TM)** – separate treatment/control models  
- ✅ **LGWUM** – causal class transformation into a multinomial target

> The goal: smarter campaign targeting based on **true persuasion**, not just raw probabilities.

---

## 📦 Dataset

- **Source**: [Criteo Uplift Dataset](https://www.kaggle.com/datasets/criteo-uplift-prediction)
- **Rows**: ~14 million (sampled for balance)
- **Features**:  
  - 12 continuous: `f0` to `f11`  
  - `exposure` (treatment)  
  - `visit` (response)  
  - `target_class` (derived label: CN, CR, TN, TR)

> ⚠️ Large class imbalance required careful sampling and label engineering.
---

## ⚙️ Methodology Summary

| Step              | Description                                                        |
|-------------------|--------------------------------------------------------------------|
| 📊 Data Prep      | Chunked reads, exposure/control split, label engineering           |
| 🔍 Modeling       | SM, TM, and LGWUM estimators                                       |
| 🧮 Evaluation     | Uplift score prediction, gain curves, decile uplift analysis       |
| 📈 Visualization  | ROC-like uplift plots, distribution curves, feature correlation    |

---

## 📈 Key Visuals

### 📊 Cumulative Gain Curve
![Gain Curve](assets/gain_curve.png)

LGWUM showed superior targeting capability, especially in the top 30% of users.

---

### 🪜 Uplift Score Deciles
![Deciles](assets/deciles.png)

Conversion rates increase per decile — indicating strong uplift ranking behavior.

---

### 🧮 Score Distribution
![Uplift Distribution](assets/uplift_dist.png)

Scores cluster around zero with slight positive skew — ideal for targeting the persuadable.

---

## 🗂️ Folder Structure

```bash
treat-or-target/
├── 📁 notebook/               # Jupyter notebook with full modeling pipeline
│   └── Uplift_Model.ipynb
├── 📁 src/                    # Python module for reusable functions
│   └── uplift_model.py
├── 📁 data/                   # Kaggle dataset reference
│   └── README.md
├── 📁 assets/                 # Visuals for README
│   ├── gain_curve.png
│   ├── deciles.png
│   └── uplift_dist.png
├── requirements.txt
├── LICENSE
└── README.md

```
