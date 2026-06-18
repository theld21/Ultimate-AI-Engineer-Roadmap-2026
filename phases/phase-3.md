## 🗺️ PHASE 3 - Machine Learning Fundamentals

> **Goal:** Understand the classic ML algorithms that power AI feature engineering and evaluation.

### 3.1 Core ML Concepts

- Supervised vs Unsupervised vs Reinforcement Learning
- Training set, validation set, test set
- Overfitting and underfitting
- Bias-variance tradeoff
- Cross-validation (k-fold)
- Evaluation metrics: Accuracy, Precision, Recall, F1, AUC-ROC

### 3.2 Linear & Logistic Regression

- Linear regression - closed form and gradient descent
- Logistic regression - sigmoid output, binary classification
- Cost functions: MSE, Binary Cross-Entropy
- Regularization: Ridge (L2), Lasso (L1)
- Multi-class classification: One-vs-Rest

### 3.3 Decision Trees & Ensembles

- Decision trees - splitting criteria (Gini, entropy)
- Random forests - bagging of decision trees
- Gradient boosting - XGBoost, LightGBM (used in ML features)
- Feature importance

### 3.4 Unsupervised Learning

- K-Means clustering
- DBSCAN
- PCA - dimensionality reduction (connects to embeddings)
- t-SNE / UMAP - visualization of high-dimensional data (embedding visualization)

### 3.5 Hyperparameter Tuning

- Grid search, random search
- Bayesian optimization
- Learning rate, batch size, epochs, layers
- Early stopping

### 3.6 ML with Scikit-Learn

- Pipelines: `Pipeline()` class
- Preprocessors: `StandardScaler`, `MinMaxScaler`, `OneHotEncoder`
- Model selection: `GridSearchCV`, `cross_val_score`
- Saving models: `joblib`
- Understanding the sklearn API pattern (fit/transform/predict)

---

### 📦 Phase 3 Projects

**🟢 Easy: Spam Classifier**
- Build a spam/not-spam email classifier with TF-IDF + Logistic Regression
- Evaluate with precision, recall, F1
- Stack: Scikit-learn, Pandas, NLTK

**🟡 Medium: Customer Churn Prediction System**
- Full pipeline: data cleaning → feature engineering → model training → evaluation
- Try Logistic Regression vs Random Forest vs XGBoost
- Add SHAP for explainability
- Stack: Scikit-learn, XGBoost, SHAP, Pandas, Matplotlib

**🔴 Hard: AutoML Mini-Framework**
- Build a framework that automatically tries multiple models and hyperparameters
- Generate a full evaluation report
- Add feature importance, confusion matrix, ROC curve
- Stack: Scikit-learn, Optuna (Bayesian optimization), Pandas, Matplotlib

---

