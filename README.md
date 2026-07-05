# Employee Attrition Prediction (Naive Bayes)

## 📌 Project Overview

This project is built to predict employee attrition using machine learning. The goal is not just to build a model, but to understand how machine learning decisions change based on real business needs.

While working on this project, I focused on understanding *why employees leave* and how a model can help the HR take early action.

---

## 🧠 My Thought Process

While building this project, I did not directly focus only on accuracy / Recall. I started thinking from a real-world HR perspective.

My thinking was:

- If an employee is actually going to leave but the model predicts they will stay, it is a serious loss for the company in terms of finances.
- If the model incorrectly predicts an employee will leave but they actually stay, HR can still investigate them — which is acceptable.
- So I realized that **False Negatives are more costly than False Positives** in this case.

Because of this, I decided to prioritize **Recall over Precision**.

---

## ⚙️ Approach Used

- Used **Naive Bayes classifier** as the base model
- Dataset was **imbalanced**, so accuracy alone was not reliable
- Used `predict_proba()` to get probability outputs
- Instead of default threshold (0.5), I experimented with multiple thresholds
- Tried different values like 0.2, 0.3, 0.38, etc.

---

## 🔄 What I Observed

While changing thresholds:

- Lower threshold → higher recall, more false positives
- Higher threshold → better precision, but more missed employees
- I realized there is always a **trade-off between precision and recall**

Even though **F2-score suggested 0.2 as best**, I personally observed that **0.38 gave a better balance between recall, precision, and accuracy**

---

## ⚖️ Final Understanding

In real-world HR problems:

- We cannot rely only on accuracy
- We must understand business cost of errors
- In my case:
  - False Negatives (employee leaves unnoticed) = high cost
  - False Positives (extra HR attention) = acceptable cost

So I focused on improving recall while still maintaining reasonable accuracy.

---

## 📌 Key Learnings

- Accuracy is not enough for imbalanced datasets
- Business understanding is more important than just model score
- Recall becomes critical when missing a positive case is costly
- Threshold tuning is powerful without retraining the model
- Real machine learning is about trade-offs, not perfect scores

---

## 🚀 Final Conclusion

This project helped me understand that machine learning is not just about building models, but about aligning model behavior with business decisions. By tuning thresholds and prioritizing recall, I was able to make the model more useful for real-world HR decision-making.
