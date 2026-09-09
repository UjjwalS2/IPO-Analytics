# IPO Analytics 📈

A machine-learning based IPO analytics project that uses historical IPO characteristics to estimate the probability of a successful listing and generate apply/no-apply recommendations for upcoming IPOs.

## 🎯 Objective

Build a data-driven framework to analyze IPO characteristics such as issue size, subscription, IPO price and GMP, engineer predictive features, train a Random Forest classifier, and use the model to estimate success probabilities for upcoming IPOs.

## 🧠 Approach

```text
Historical IPO Data
        ↓
Data Cleaning & Preprocessing
        ↓
Feature Engineering
        ↓
Train / Test Split
        ↓
Random Forest Classifier
        ↓
Model Evaluation + Feature Importance
        ↓
Upcoming IPO Data
        ↓
Success Probability
        ↓
Apply / Do Not Apply Recommendation
```

## 🔧 Feature Engineering

The model uses the following predictors:

- IPO Size
- Subscription
- GMP
- IPO Price
- GMP-to-IPO Price Ratio
- Log IPO Size
- Subscription-to-GMP interaction
- IPO Price-to-Size Ratio

The historical target is defined from listing performance: an IPO is labelled successful when its listing price exceeds the IPO price by more than 20%.

## 🤖 Model

**Random Forest Classifier**

- Number of trees: 100
- Train/test split: 80/20
- Random state: 42
- Output: probability of successful listing
- Recommendation threshold: probability ≥ 0.50

## 📊 Model Results

Evaluation on the held-out test set produced:

| Metric | Class 0 | Class 1 |
|---|---:|---:|
| Precision | 0.82 | 0.83 |
| Recall | 0.92 | 0.67 |
| F1-score | 0.87 | 0.74 |
| Support | 25 | 15 |

**Overall accuracy: 82%**

| Aggregate | Precision | Recall | F1-score |
|---|---:|---:|---:|
| Macro average | 0.83 | 0.79 | 0.80 |
| Weighted average | 0.83 | 0.82 | 0.82 |

### Feature Importance

The model's feature importance scores were:

| Feature | Importance |
|---|---:|
| GMP-to-IPO Ratio | 0.2557 |
| GMP | 0.1820 |
| Subscription | 0.1727 |
| Subscription-to-GMP | 0.1470 |
| IPO Price | 0.0675 |
| IPO Size | 0.0665 |
| Log IPO Size | 0.0631 |
| IPO Price-to-Size Ratio | 0.0455 |

The results indicate that **GMP-to-IPO ratio, GMP, and subscription** are the strongest predictors among the engineered features in this model.

## 🔮 Upcoming IPO Predictions

The notebook generates probability-based recommendations for upcoming IPOs. The recorded output includes:

| IPO | Success Probability | Recommendation |
|---|---:|---|
| Scoda Tubes | 0.46 | Do not apply |
| Aegis Vopak Terminals | 0.30 | Do not apply |
| Leela Hotels | 0.31 | Do not apply |
| Belrise Industries | 0.71 | Apply |
| Borana Weaves | 0.51 | Apply |
| Prostarm Info Systems | 0.60 | Apply |

## 📓 Notebook

The complete analysis is available in [`IPO_Analytics_Main.ipynb`](IPO_Analytics_Main.ipynb), including preprocessing, feature engineering, model training, evaluation, visualizations, feature importance analysis, and upcoming-IPO predictions.

## 🛠️ Tech Stack

Python · Pandas · NumPy · Scikit-learn · Matplotlib · Seaborn · Jupyter Notebook

## ⚠️ Disclaimer

This is an educational machine-learning project. IPO probabilities and recommendations are model outputs based on the available historical/features and should not be interpreted as investment advice.

## 👤 Author

**Ujjwal Sinha**  
GitHub: https://github.com/UjjwalS2
