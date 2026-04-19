# 📊 Customer Churn Prediction with Profit-Optimized Machine Learning

## 🧠 Project Overview

This project is an **end-to-end machine learning system for customer churn prediction**, designed not only to predict churn but to **optimize business decisions under different operational strategies**.

Instead of focusing solely on predictive performance, the system emphasizes:
- Probability calibration
- Profit-driven decision thresholds
- Business constraint trade-offs (coverage vs efficiency)
- Customer segmentation
- Model explainability (SHAP)

The final output is not just a model — it is a **decision-making framework for customer retention**.

---

## 🎯 Business Objective

The objective is to identify customers likely to churn and design a **retention strategy that maximizes profit (ROI)**.

### Business Assumptions
- 💰 Cost per retention action: €50  
- 💰 Value of retained customer: €500  

---

## 📊 Dataset

- Telco Customer Churn dataset  
- Binary classification:
  - `1` → Customer churns  
  - `0` → Customer stays  

---

## 🤖 Model Performance

### Classification Metrics

- **ROC-AUC:** 0.8376  
- **Accuracy:** 0.78  

| Class | Precision | Recall | F1-score |
|------|----------|--------|----------|
| 0 (No churn) | 0.82 | 0.91 | 0.86 |
| 1 (Churn) | 0.63 | 0.45 | 0.52 |

### Key Insight
The model performs better at identifying non-churners than churners, which is typical in **imbalanced classification problems**.

---

## 🧠 Explainability (SHAP)

<img width="786" height="771" alt="image" src="https://github.com/user-attachments/assets/696e0487-c047-46db-bd95-9b78a30bcb05" />

<img width="793" height="765" alt="image" src="https://github.com/user-attachments/assets/350e4e55-06f7-4a19-9d33-c737630eb440" />


- SHAP output shape: `(1407, 35)`
- Provides global feature importance
- Ensures interpretability of predictions

---

## 🎯 Decision Strategy (Threshold Optimization)

This project does NOT use a fixed 0.5 threshold.

Instead, it evaluates multiple operating points based on business value.

<img width="757" height="486" alt="image" src="https://github.com/user-attachments/assets/e334061d-407c-4649-8ff3-576084a429dc" />

<img width="894" height="465" alt="image" src="https://github.com/user-attachments/assets/3434e2ce-5d3b-49c6-9481-53a55092b638" />

---

## ⚙️ Two Operating Strategies

### 🔵 Strategy 1: High-Precision Targeting

- **Best threshold:** 0.74  
- **Retained customers:** 83  
- **Value saved:** €41,500  
- **Campaign cost:** €5,100  
- **ROI:** **7.13**

#### Interpretation
- Focuses only on highest-risk customers
- Maximizes efficiency per customer
- Low coverage, high precision strategy

---

### 🔴 Strategy 2: High-Coverage Targeting

- **Best threshold:** 0.10  
- **Retained customers:** 345  
- **Value saved:** €172,500  
- **Campaign cost:** €42,050  
- **ROI:** **3.10**

#### Interpretation
- Captures more potential churners
- Higher total business impact
- Lower efficiency but higher coverage

---

## 📊 Key Insight: Trade-off Between Strategies

This project demonstrates a fundamental business trade-off:

| Strategy | Precision | Recall | ROI per Customer | Total Impact |
|----------|-----------|--------|------------------|--------------|
| High Threshold (0.74) | High | Low | High | Medium |
| Low Threshold (0.10) | Low | High | Medium | High |

👉 There is no single “best threshold” — only **different business strategies**

---

## 📈 ROI vs Threshold Analysis

The ROI curve shows how business performance changes depending on the decision threshold.

Key observations:
- Higher thresholds reduce campaign size but increase efficiency
- Lower thresholds increase coverage but reduce ROI efficiency
- Optimal operating point depends on business constraints

---

## 👥 Customer Segmentation

<img width="913" height="550" alt="image" src="https://github.com/user-attachments/assets/f10eab6f-38bd-45a1-9f13-a437ffab324c" />


Customers are grouped into risk segments based on predicted churn probability:

| Segment | Customers | Churn Rate | Avg Probability |
|--------|----------|------------|-----------------|
| Low | 356 | 1.7% | 0.02 |
| Medium | 354 | 11.8% | 0.11 |
| High | 368 | 32.6% | 0.33 |
| Very High | 329 | 62.6% | 0.65 |

### Key Insight
- Risk is strongly separated across segments
- High and Very High segments represent the **core revenue opportunity**

---

## 📉 Lift Curve

The lift curve demonstrates how effectively the model prioritizes churners compared to random targeting.

- The model significantly outperforms random selection
- Highest lift is observed in the top-ranked customers

---

## 🔍 Key Functions

- `find_best_threshold_profit()` → optimizes business profit  
- `business_impact()` → evaluates campaign ROI  
- `plot_roi_curve()` → threshold sensitivity analysis  
- `plot_lift_curve()` → targeting effectiveness  
- `segment_analysis()` → customer risk segmentation  

---

## 🧠 Key Insights

- Accuracy is not sufficient for churn problems
- Threshold selection is a **business decision, not a modeling decision**
- Different thresholds correspond to different business strategies
- Profit optimization provides better decision-making than classification metrics
- Customer segmentation enables targeted retention strategies

---

## 🛠 Tech Stack

- Python  
- pandas, numpy  
- scikit-learn  
- matplotlib, seaborn  
- SHAP  

---

## 📌 Conclusion

This project demonstrates a complete **machine learning decision system**, where predictions are directly translated into business actions.

Instead of building a static classifier, we build a **dynamic decision framework** that adapts to business goals such as:

- Maximizing ROI
- Maximizing coverage
- Balancing cost vs value

👉 The key takeaway:  
**In real-world data science, the best model is not the most accurate one — but the one that makes the best decisions.**
