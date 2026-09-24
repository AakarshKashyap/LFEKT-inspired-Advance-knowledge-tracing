# LFEKT-Inspired Advanced Knowledge Tracing

An ensemble-learning framework for **student performance prediction and knowledge tracing**, inspired by the principles of **Learning Factors Analysis (LFA)** and **Ebbinghaus forgetting dynamics**.

The project models how a student's knowledge evolves over time by combining temporal learning behaviour, forgetting patterns, question difficulty, and historical interaction features with modern gradient-boosting ensemble models.

---

## 📌 Overview

Knowledge Tracing (KT) aims to estimate a student's evolving knowledge state from their historical interactions with educational content.

This project explores a feature-engineered approach that combines:

* **Item Response Theory (IRT)** concepts
* **Ebbinghaus forgetting curve**
* Temporal learning dynamics
* Student interaction history
* Question and skill-level information
* Feature engineering and selection
* Ensemble machine learning

The resulting feature space contains **106+ engineered features** designed to capture different aspects of student learning behaviour.

The final prediction system uses a **stacking ensemble of XGBoost, LightGBM, and CatBoost**, with Bayesian hyperparameter optimization performed using Optuna.

---

## 🎯 Objectives

The project focuses on:

1. Modeling student knowledge progression over time.
2. Capturing the effect of forgetting between learning interactions.
3. Incorporating temporal and behavioural learning features.
4. Combining multiple gradient-boosting models through stacking.
5. Evaluating model performance using robust statistical and ML metrics.
6. Understanding which features contribute most to prediction performance.

---

## 🧠 Methodology

The overall pipeline follows:

```text
Student Interaction Data
          │
          ▼
   Data Preprocessing
          │
          ▼
   Feature Engineering
          │
          ├── Student History Features
          ├── Question / Skill Features
          ├── Temporal Features
          ├── Forgetting Features
          └── IRT-inspired Features
          │
          ▼
   106+ Feature Representation
          │
          ▼
 Bayesian Hyperparameter Optimization
             (Optuna)
          │
          ▼
 ┌─────────┼─────────┐
 │         │         │
 ▼         ▼         ▼
XGBoost  LightGBM  CatBoost
 │         │         │
 └─────────┼─────────┘
           ▼
    Stacking Ensemble
           │
           ▼
   Student Performance
      Prediction
           │
           ▼
   Evaluation & Analysis
```

---

## 🔬 Feature Engineering

The framework incorporates multiple categories of features to represent student learning behaviour.

### Temporal Features

Features describing the student's interaction history and learning progression over time.

### Forgetting Features

Features inspired by the **Ebbinghaus forgetting curve**, capturing the potential effect of elapsed time between learning interactions.

### Knowledge / Skill Features

Features representing historical performance and interaction behaviour associated with questions and concepts.

### IRT-Inspired Features

Features motivated by **Item Response Theory**, incorporating relationships between student ability and question difficulty.

### Behavioural Features

Historical interaction statistics are used to represent student-specific learning patterns.

Together, these transformations produce a feature space containing **106+ features**.

---

## 🤖 Machine Learning Models

Three gradient-boosting models are used as base learners:

### XGBoost

Used to model nonlinear relationships between engineered learning features and student outcomes.

### LightGBM

Used as a highly efficient gradient-boosting learner capable of handling a large engineered feature space.

### CatBoost

Used as an additional diverse gradient-boosting learner to improve ensemble diversity.

### Stacking Ensemble

The predictions from the three base models are combined using a stacking architecture to produce the final prediction.

---

## ⚙️ Hyperparameter Optimization

The project uses **Optuna** for Bayesian-style hyperparameter optimization.

The optimization process searches for effective configurations for:

* XGBoost
* LightGBM
* CatBoost

This allows the ensemble to be tuned systematically rather than relying only on manually selected hyperparameters.

---

## 📊 Results

The final stacking ensemble achieved:

| Metric                    |                    Result |
| ------------------------- | ------------------------: |
| ROC-AUC                   |                 **0.832** |
| Engineered Features       |                  **106+** |
| Dataset                   | **ASSISTments 2009–2010** |
| Interaction Records       |                 **500K+** |
| Improvement over baseline |       **+3.1 AUC points** |

The project also includes feature-importance analysis and ablation experiments to investigate the contribution of different feature groups.

---

## 📈 Model Evaluation

The project evaluates the model using:

* ROC-AUC
* Accuracy
* Precision
* Recall
* F1-score
* Ablation analysis
* Feature importance
* SHAP-based interpretability
* Statistical significance testing

A **Wilcoxon signed-rank test** is used as part of the statistical analysis.

---

## 🔍 Interpretability

To better understand the model's decisions, the project uses **SHAP-based feature importance analysis**.

This allows the contribution of individual features to the model's predictions to be examined and helps identify which learning-related factors have the greatest influence on student performance prediction.

---

## 🧪 Ablation Analysis

Ablation experiments are used to study the contribution of different feature groups.

In particular, temporal and forgetting-related features are investigated to understand how much additional predictive information they provide beyond conventional student-interaction features.

---

## 📚 Dataset

The experiments use the **ASSISTments 2009–2010** educational dataset.

The dataset contains more than **500K student interaction records**, representing student responses to educational exercises.

> The original dataset is not included in this repository.

Please obtain the dataset from its official source and follow its applicable terms of use.

---

## 🛠️ Technology Stack

**Programming**

* Python

**Machine Learning**

* Scikit-learn
* XGBoost
* LightGBM
* CatBoost

**Optimization**

* Optuna

**Data Processing**

* pandas
* NumPy

**Interpretability**

* SHAP

**Statistical Analysis**

* SciPy

**Development**

* Jupyter Notebook
* Git / GitHub

---

## 📁 Repository Structure

```text
LFEKT-inspired-Advance-knowledge-tracing/
│
├── advanced_knowledge_tracing_CLEAN.ipynb
│
├── Devulapally Aakarsh_research_paper.pdf
│
└── README.md
```

### `advanced_knowledge_tracing_CLEAN.ipynb`

Contains the main experimental workflow, including data processing, feature engineering, model development, evaluation, and analysis.

### `Devulapally Aakarsh_research_paper.pdf`

Contains the detailed research methodology, experiments, results, analysis, and conclusions.

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/AakarshKashyap/LFEKT-inspired-Advance-knowledge-tracing.git

cd LFEKT-inspired-Advance-knowledge-tracing
```

### 2. Install dependencies

Create a Python environment and install the required packages:

```bash
pip install numpy pandas scikit-learn xgboost lightgbm catboost optuna shap scipy matplotlib seaborn jupyter
```

### 3. Prepare the dataset

Download the ASSISTments 2009–2010 dataset from its official source.

Place the dataset in the location expected by the notebook.

### 4. Run the notebook

Launch Jupyter:

```bash
jupyter notebook
```

Then open:

```text
advanced_knowledge_tracing_CLEAN.ipynb
```

and execute the cells sequentially.

> Dataset paths and preprocessing configuration may need to be adjusted according to your local environment.

---

## 📄 Research Paper

The complete research paper is available in this repository:

**[Devulapally Aakarsh — Research Paper](./Devulapally%20Aakarsh_research_paper.pdf)**

---

## 🔬 Research Highlights

* **106+ engineered learning features**
* **500K+ student interaction records**
* Hybrid knowledge-tracing feature design
* IRT-inspired modelling
* Ebbinghaus forgetting dynamics
* Temporal learning features
* XGBoost + LightGBM + CatBoost ensemble
* Bayesian hyperparameter optimization with Optuna
* SHAP-based interpretability
* Ablation experiments
* Statistical significance testing
* ROC-AUC of **0.832**

---

## 🔮 Future Work

Potential directions for extending the project include:

* Incorporating Transformer-based sequential knowledge tracing.
* Learning concept-specific forgetting rates.
* Adding richer student behavioural signals.
* Exploring graph-based relationships between concepts and questions.
* Incorporating sequence embeddings.
* Evaluating the framework on additional knowledge-tracing datasets.
* Developing a real-time inference API for personalized learning systems.

---

## 👤 Author

**Aakarsh Devulapally**

B.Tech — Computer Science Engineering
Specialization: Artificial Intelligence & Machine Learning
SR University, Warangal, India

**GitHub:** [AakarshKashyap](https://github.com/AakarshKashyap)

---

## ⭐ Project

If you find this project useful for research or experimentation, consider giving the repository a ⭐.
