# WineQualityPredictionSystem

This project focuses on predicting the **quality of wine** based on its physicochemical properties using **machine learning classification models**. The goal is to classify whether a wine is of *good quality* or *not* by learning patterns from a publicly available wine quality dataset.

The project demonstrates a complete **end-to-end machine learning workflow**, including data preprocessing, exploratory data analysis (EDA), feature engineering, model training, evaluation, and comparison of multiple algorithms.

---

## 📌 Problem Statement

Wine quality is influenced by various chemical properties such as acidity, sugar content, alcohol percentage, sulphates, and more. Manually assessing wine quality can be subjective and time-consuming. This project aims to:

* Analyze the relationship between wine features and quality
* Build machine learning models to **predict wine quality**
* Compare model performance and select the best-performing classifier

Wine quality is converted into a **binary classification problem**:

* `1` → Good Quality (quality > 5)
* `0` → Not Good Quality (quality ≤ 5)

---

## 🧰 Technology Stack

* **Programming Language:** Python
* **Data Handling:** Pandas, NumPy
* **Data Visualization:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-learn, XGBoost

---

## 📂 Dataset

* **Source:** Publicly available Wine Quality Dataset
* **Type:** Tabular data
* **Features:** Physicochemical properties of wine (continuous variables)
* **Target:** Wine quality score

Missing values are handled using **mean imputation**, and highly correlated features are removed to improve model performance.

---

## 🔍 Exploratory Data Analysis (EDA)

The following EDA techniques were applied:

* Inspection of data types and missing values
* Statistical summary of features
* Histogram plots to analyze feature distributions
* Bar plots to study wine quality distribution
* Correlation heatmap to identify redundant features

Highly correlated features such as **free sulfur dioxide** and **total sulfur dioxide** were analyzed, and one was removed to reduce multicollinearity.

---

## ⚙️ Data Preprocessing

* Handling missing values using mean imputation
* Encoding categorical variables (e.g., wine type: red/white)
* Feature scaling using **MinMaxScaler**
* Feature-target separation
* Train–test split (80:20)

---

## 🤖 Machine Learning Models Used

The following classification models were trained and evaluated:

* **Logistic Regression**
* **Support Vector Classifier (SVC)**
* **XGBoost Classifier**

Each model was evaluated using **ROC-AUC score** on both training and validation datasets.

---

## 📊 Model Performance

| Model                  | Training ROC-AUC | Validation ROC-AUC |
| ---------------------- | ---------------- | ------------------ |
| Logistic Regression    | ~0.69            | ~0.68              |
| SVC (RBF Kernel)       | ~0.72            | ~0.70              |
| **XGBoost Classifier** | **~0.97**        | **~0.80**          |

✅ **XGBoost Classifier** achieved the best validation performance.

---

## 🧪 Model Evaluation

The best-performing model (XGBoost) was further evaluated using:

* **Confusion Matrix**
* **Classification Report** (Precision, Recall, F1-score)

### Classification Report Summary:

* Accuracy: **~92.5%**
* Strong performance for both quality classes
* Balanced precision and recall

---

## 🎯 Key Learnings

* Hands-on experience with **classification algorithms**
* Feature selection using correlation analysis
* Importance of data scaling and preprocessing
* Model evaluation using ROC-AUC and confusion matrix
* Practical implementation of XGBoost

---

## ⚠️ Drawbacks / Limitations

* The model treats wine quality as a **binary classification problem**, which oversimplifies the original multi-class nature of the dataset and may lose nuanced quality distinctions.
* The dataset is relatively **small and static**, which may limit the model’s ability to generalize well to unseen or real-world wine data.
* **Class imbalance** exists between good and not-good quality wines, which may bias the model toward the majority class.
* Feature engineering is minimal and primarily relies on raw physicochemical attributes without domain-specific transformations.
* Hyperparameter tuning was not extensively performed, which may prevent models from achieving optimal performance.
* The project does not include **cross-validation**, relying instead on a single train–test split for evaluation.
* Model evaluation focuses on standard metrics; advanced techniques such as calibration curves or explainability methods (e.g., SHAP) are not applied.
* The solution is not deployed as an end-user application and remains limited to a notebook-based workflow.
