# 🧠 ML-05: SHAP (SHapley Additive exPlanations)

<p align="center">

![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Explainable%20AI-blue?style=for-the-badge)
![XAI](https://img.shields.io/badge/Explainable-AI-success?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-SHAP-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Notes-Completed-brightgreen?style=for-the-badge)

</p>

> **📅 Date:** July 14, 2026
> **📂 Module:** Machine Learning
> **📖 Topic:** SHAP (SHapley Additive exPlanations)
> **🎯 Difficulty:** Beginner → Intermediate

---

# 📚 Table of Contents

1. Why Explainable AI?
2. What is SHAP?
3. Black Box vs White Box Models
4. Why SHAP is Based on Game Theory
5. SHAP Values Explained
6. Baseline Prediction
7. Positive & Negative SHAP Values
8. Properties of SHAP
9. SHAP Workflow
10. SHAP Plots
11. Python Implementation
12. Applications
13. Advantages
14. Limitations
15. Interview Notes
16. Key Takeaways

---

# 🌍 Why Explainable AI?

Modern Machine Learning models are becoming:

* More accurate ✅
* More powerful ✅
* More complex ✅

However, increasing complexity creates a new problem.

> **How did the model reach this prediction?**

Imagine applying for a bank loan.

The bank replies:

> **"Your loan application has been rejected by an AI model."**

Naturally, your next question would be:

> **"Why?"**

Simply receiving a prediction is not enough.

People deserve explanations, especially in sensitive domains such as:

* 🏦 Banking
* 🩺 Healthcare
* ⚖️ Law
* 🚗 Autonomous Vehicles
* 💼 Hiring Systems

This is where **Explainable AI (XAI)** becomes important.

---

# 🤖 Black Box vs White Box Models

## White Box Models

These models are easy to understand.

Examples:

* Linear Regression
* Small Decision Trees

We can directly explain why a prediction was made.

---

## Black Box Models

Examples:

* Random Forest
* XGBoost
* LightGBM
* Neural Networks

These models often provide excellent accuracy but do not naturally explain their reasoning.

You know:

```
Input
   ↓
Prediction
```

But the internal reasoning is hidden.

Hence the name:

> **Black Box Model**

---

# 🌟 What is SHAP?

**SHAP (SHapley Additive exPlanations)** is an Explainable AI technique that explains how each feature contributes to a machine learning model's prediction.

Instead of only saying:

```
Loan Rejected
```

SHAP explains:

| Feature       | Contribution |
| ------------- | -----------: |
| Income        |        +0.42 |
| Credit Score  |        +0.31 |
| Existing Loan |        -0.28 |
| Late Payments |        -0.44 |

This allows us to understand **why** the model made its prediction.

---

# 🎮 Why is SHAP Based on Game Theory?

SHAP is built upon **Shapley Values**, a concept from Game Theory.

Imagine four friends complete a group project and score **100 marks**.

Now we need to distribute credit fairly.

Should everyone receive equal credit?

❌ No.

Each student should receive credit according to their contribution.

Machine Learning follows the same idea.

### Game Theory

| Game Theory  | Machine Learning |
| ------------ | ---------------- |
| Players      | Features         |
| Reward       | Model Prediction |
| Contribution | SHAP Value       |

SHAP fairly distributes the contribution of each feature toward the final prediction.

---

# 🧩 What are SHAP Values?

A SHAP value measures:

> **How much a feature contributed to increasing or decreasing the model's prediction.**

Each feature can:

* Increase the prediction (Positive SHAP Value)
* Decrease the prediction (Negative SHAP Value)

The magnitude indicates the strength of that contribution.

---

# 🏠 Example

Suppose the model predicts:

```
House Price = ₹80 Lakh
```

SHAP explains it like this:

| Feature   | SHAP Contribution |
| --------- | ----------------: |
| Area      |         +₹12 Lakh |
| Location  |         +₹10 Lakh |
| House Age |          -₹2 Lakh |

Instead of simply giving the answer,

SHAP explains **how the answer was constructed.**

---

# 📈 Baseline Prediction

One of the most important concepts in SHAP.

Before making any prediction, SHAP asks:

> **"If I knew nothing about this observation, what would I predict?"**

This is called the **Baseline Prediction** (Expected Value).

Example:

```
Average House Price

₹60 Lakh
```

Now each feature modifies this value.

```
Baseline

₹60 Lakh

+ Area

+₹12 Lakh

+ Location

+₹10 Lakh

- House Age

-₹2 Lakh

──────────────────

Final Prediction

₹80 Lakh
```

This is why SHAP is called **Additive Explanations**.

---

# ➕ Positive vs Negative SHAP Values

| SHAP Value | Meaning                  |
| ---------- | ------------------------ |
| Positive   | Pushes prediction higher |
| Negative   | Pushes prediction lower  |

Example (Loan Prediction)

| Feature       |  SHAP |
| ------------- | ----: |
| Income        | +0.45 |
| Credit Score  | +0.30 |
| Existing Loan | -0.20 |
| Late Payments | -0.35 |

Positive features increase the probability of approval.

Negative features reduce it.

---

# 📐 Properties of SHAP

## 1️⃣ Additivity

Feature contributions add together.

```
Prediction

=

Baseline

+

Feature 1

+

Feature 2

+

Feature 3
```

---

## 2️⃣ Local Accuracy

The sum of all SHAP values exactly equals:

```
Prediction

-

Baseline
```

This ensures every individual prediction is explained completely.

---

## 3️⃣ Missingness

If a feature does not contribute to a prediction,

```
SHAP Value = 0
```

Irrelevant or unused features do not affect the explanation.

---

## 4️⃣ Consistency

If a feature becomes more influential in a newer model,

its SHAP value should not decrease.

This ensures stable and reliable explanations.

---

# 🌳 SHAP Workflow

```
Train ML Model
        │
        ▼
Create SHAP Explainer
        │
        ▼
Calculate SHAP Values
        │
        ▼
Visualize Contributions
        │
        ▼
Explain Predictions
```

---

# 📊 SHAP Visualizations

## Summary Plot

**Purpose**

Shows overall feature importance.

Best for:

* Global Explainability

---

## Dependence Plot

**Purpose**

Shows how one feature affects predictions.

Useful for:

* Understanding feature behaviour
* Discovering feature interactions

---

## Force Plot

**Purpose**

Explains one individual prediction.

Shows which features push the prediction:

➡️ Higher

⬅️ Lower

---

## Decision Plot

Shows cumulative feature contributions across multiple predictions.

Useful for comparing model decisions.

---

# 💻 Basic Python Implementation

```python
import shap

explainer = shap.Explainer(model, X_train)
shap_values = explainer(X_test)
```

Summary Plot

```python
shap.summary_plot(shap_values, X_test)
```

Force Plot

```python
shap.plots.force(
    explainer.expected_value,
    shap_values[0],
    X_test.iloc[0]
)
```

---

# 🌍 Applications of SHAP

* Explain individual predictions
* Detect model bias
* Model debugging
* Feature importance analysis
* Fairness auditing
* Regulatory compliance
* Increase user trust

---

# ✅ Advantages

* Model-agnostic
* Works with many ML algorithms
* Fair feature attribution
* Local and global explanations
* Strong theoretical foundation
* Widely used in Explainable AI

---

# ❌ Limitations

* Can be computationally expensive
* Interpretation becomes difficult with many features
* Requires domain knowledge for meaningful insights
* Different explainers are used for different model families (e.g., TreeExplainer, LinearExplainer, DeepExplainer)

---

# 🎤 Interview Notes

### What is SHAP?

SHAP is an Explainable AI technique that explains how each feature contributes to a machine learning model's prediction using Shapley Values from Game Theory.

---

### Why is SHAP based on Game Theory?

Because it fairly distributes the contribution of each feature toward the final prediction, similar to fairly distributing rewards among players in a cooperative game.

---

### What does a positive SHAP value mean?

The feature increases the model's prediction.

---

### What does a negative SHAP value mean?

The feature decreases the model's prediction.

---

### What is the Baseline Prediction?

The prediction the model would make if it knew nothing about the current observation.

---

### What is Additivity?

Final Prediction = Baseline + Sum of all SHAP Values

---

### Which SHAP plot explains one prediction?

**Force Plot**

---

### Which SHAP plot shows overall feature importance?

**Summary Plot**

---

### Is SHAP model-agnostic?

Yes. SHAP can explain many machine learning models, although different explainers are optimized for different model types.

---

# 📝 Key Takeaways

* SHAP stands for **SHapley Additive exPlanations**.
* It explains **why** a model made a prediction.
* Features are treated as **players** in a cooperative game.
* SHAP values represent each feature's contribution.
* Positive values increase predictions.
* Negative values decrease predictions.
* The prediction starts from a **baseline value** and each feature adds or subtracts from it.
* SHAP provides both **local** (single prediction) and **global** (overall model) explanations.
* It is widely used for Explainable AI in finance, healthcare, cybersecurity, and business analytics.

---

# 💭 Learning Reflection

Today I learned that building an accurate machine learning model is only part of the solution. In many real-world applications, understanding **why** a model made a prediction is just as important as the prediction itself.

SHAP provides a fair and mathematically grounded way to explain model decisions by assigning each feature a contribution toward the final prediction. This makes complex models more transparent, trustworthy, and easier to debug.

---

> **💡 Final Memory Line**

> **"Machine Learning predicts. SHAP explains why."** 🚀
