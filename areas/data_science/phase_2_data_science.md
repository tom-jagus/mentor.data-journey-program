# 🧠 Phase 2 – Data Science (Weeks 5–10)

**Area**: Data Science – Hands-on Modeling & Evaluation
**Part of**: _Data Journey Program_
**Objective**: Move from conceptual understanding to practical application of data science techniques. Introduce model building, basic evaluation, and structured experimentation in a real-world context.

---

## 🌟 Learning Goals

- Build basic predictive models using Python (or a preferred platform)
- Understand how to structure a machine learning workflow
- Learn to split data for training and testing appropriately
- Evaluate models using accuracy, precision, recall, etc.
- Communicate the purpose and results of a model to stakeholders

---

## 🧩 Topics Covered

### 1. **ML Workflow & Problem Framing**

A repeatable structure for building models:

1. Define the question (classification vs regression)
2. Prepare and clean data
3. Select model type (e.g., decision tree, logistic regression)
4. Train/test split
5. Train model
6. Evaluate performance
7. Iterate or deploy

Start with small goals: “Can we predict X from Y?”

### 2. **Data Preparation for Modeling**

Before modeling, data must be ready:

- Handle missing values (imputation, dropping)
- Encode categorical data (one-hot, label encoding)
- Normalize or scale numeric fields
- Split into train/test (commonly 80/20 or stratified)

> Garbage in, garbage out – clean input enables good predictions.

### 3. **Model Building Basics**

Focus on interpretable and beginner-friendly models:

- **Classification**: Logistic Regression, Decision Tree, KNN
- **Regression**: Linear Regression, Ridge, Lasso

Use `scikit-learn` for a clean API and fast feedback loop.

### 4. **Model Evaluation Metrics**

Understand which metric fits the goal:

- **Accuracy**: General correctness
- **Precision & Recall**: Important for imbalanced classes
- **F1 Score**: Balances precision and recall
- **R² / MAE / RMSE**: Common for regression problems

Visual aids: confusion matrix, ROC curve, residual plots

### 5. **Interpreting & Communicating Results**

A good data scientist explains:

- What the model does and why it matters
- How accurate and useful the model is
- What limitations or assumptions exist

Use plain language summaries and simple charts to deliver impact.

---

## 🛠️ Activities & Practice

| Activity                     | Description                                                       |
| ---------------------------- | ----------------------------------------------------------------- |
| **ML Walkthrough**           | Step-by-step project from problem to model using a public dataset |
| **Data Prep Notebook**       | Focus only on preparing and transforming raw data for modeling    |
| **Metric Match Game**        | Given business scenarios, pick appropriate evaluation metrics     |
| **Model Evaluation Journal** | Log metrics and reflections from different models and datasets    |
| **Mini ML Challenge**        | Predict a target using any model of choice and present findings   |

---

## ✅ To-Do Checklist

- [ ] Complete 1 end-to-end classification project
- [ ] Prepare a dataset (cleaning, encoding, splitting)
- [ ] Train and evaluate at least 2 different models
- [ ] Compare 2 evaluation metrics and explain pros/cons
- [ ] Present results with visuals and non-technical summary

---

## 📚 Resources

- Guide: [Scikit-learn Getting Started](https://scikit-learn.org/stable/getting_started.html)
- Course: [Intro to ML with Python (Kaggle)](https://www.kaggle.com/learn/intro-to-machine-learning)
- Book: _Hands-On ML with Scikit-Learn and TensorFlow_ (Chapter 2–3)
- Dataset: [UCI ML Repository](https://archive.ics.uci.edu/ml/index.php), [Kaggle Datasets](https://www.kaggle.com/datasets)

---

## 📝 Reflection & Notes (Mentee)

- What type of model felt easiest to understand?
- What surprised you during evaluation?
- How did you simplify your explanation for a non-technical audience?

---

## 🗓️ Suggested Timeline

| Week    | Focus                                 |
| ------- | ------------------------------------- |
| Week 5  | ML workflow & problem scoping         |
| Week 6  | Data preparation and cleaning         |
| Week 7  | First models and training runs        |
| Week 8  | Evaluation metrics and interpretation |
| Week 9  | Mini project and results presentation |
| Week 10 | Review and feedback cycle             |

---

**Next Step**: Move on to Phase 2 – Methodology & Analytical Maturity
