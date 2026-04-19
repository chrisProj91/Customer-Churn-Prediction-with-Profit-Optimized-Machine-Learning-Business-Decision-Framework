# 📊 Customer Churn Prediction with Profit Optimization

## 🧠 Project Overview

This project builds an **end-to-end customer churn prediction system** that goes beyond traditional classification by incorporating **business-driven decision making**.

Instead of optimizing for accuracy alone, the model focuses on **profit maximization**, enabling a realistic customer retention strategy based on expected value.

The workflow includes:
- Machine learning modeling
- Probability calibration
- Profit-based threshold optimization
- Customer segmentation
- Lift curve analysis
- Model explainability using SHAP

---

## 🎯 Business Objective

The goal is to identify customers at risk of churning and optimize retention campaigns to maximize **return on investment (ROI)**.

Each retention action has:
- 💰 Cost per customer: €50  
- 💰 Value of retained customer: €500  

---

## 📊 Dataset

- Telco Customer Churn dataset  
- Binary classification problem:
  - 1 = Churn
  - 0 = Retain

---

## 🤖 Model Performance

### Classification Metrics

- **ROC-AUC:** 0.8376  
- **Accuracy:** 0.78  
- **F1-score (Churn class):** 0.52  

| Class | Precision | Recall | F1-score |
|------|----------|--------|----------|
| 0 (No churn) | 0.82 | 0.91 | 0.86 |
| 1 (Churn) | 0.63 | 0.45 | 0.52 |

---

## 📈 Optimal Decision Strategy

Instead of using a default threshold (0.5), the model optimizes for business profit.

- **Best threshold:** `0.7367`
- **Best ROI:** `7.13`

---

## 💰 Business Impact

At optimal threshold:

- 👥 Retained customers: 83  
- 💰 Value saved: €41,500  
- 💸 Campaign cost: €5,100  
- 📈 ROI: **7.13x**

---

## 🧠 Explainability (SHAP)

The model uses SHAP to interpret feature contributions and ensure transparency in predictions.

- Output shape: (1407, 35)
- Enables global and local feature importance analysis

---

## 📊 Customer Segmentation

Customers are segmented into risk groups based on predicted churn probability:

| Segment | Profit (€) |
|--------|-----------|
| Low | -14,800 |
| Medium | 3,300 |
| High | 41,600 |
| Very High | 86,550 |

👉 Insight: Most business value comes from High and Very High risk segments.

---

## 📉 Key Visualizations

The project includes:

- ROC-AUC evaluation
- Confusion Matrix (optimized threshold)
- ROI vs Threshold curve (`plot_roi_curve`)
- Profit vs Threshold analysis (`plot_roi_profit`)
- Lift Curve (`plot_lift_curve`)
- Churn rate by segment
- Cumulative profit analysis

---

## 🔍 Key Functions

- `find_best_threshold_profit()` → optimizes decision threshold based on profit  
- `plot_roi_curve()` → analyzes ROI sensitivity  
- `plot_lift_curve()` → measures model lift vs random targeting  
- `plot_cumulative_profit()` → evaluates segment profitability  

---

## 🚀 Key Insights

- Accuracy is not sufficient for churn problems  
- Profit optimization significantly improves decision quality  
- High-risk segmentation drives the majority of business value  
- Threshold selection is a business decision, not a modeling decision  

---

## 🛠 Tech Stack

- Python  
- pandas, numpy  
- scikit-learn  
- matplotlib, seaborn  
- SHAP  

---

## 📌 Conclusion

This project demonstrates how machine learning can be transformed into a **decision-making system**, where predictions are directly linked to financial outcomes.

Instead of building a model that predicts churn, we build a system that **optimizes business profit from churn prediction.**
