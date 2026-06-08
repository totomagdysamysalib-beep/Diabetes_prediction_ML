# 🩺 Diabetes Prediction & Classifier Benchmarking

An end-to-end Machine Learning project focused on predicting diabetes using the *Pima Indians Diabetes Dataset*. This project benchmarks multiple classification algorithms using scikit-learn, evaluating them on overall accuracy, data distribution, and clinical safety.

---

## 📊 Dataset & Preprocessing Overview
The dataset contains medical diagnostic measurements from female patients. 
* *Target Variable:* Outcome (0: Non-diabetic, 1: Diabetic)
* *Pre-processing:* Missing values (zeros in physical attributes like Glucose/BMI) were handled using SimpleImputer, and features were scaled using StandardScaler.
* *Test Set Split:* 192 samples (*123* Healthy vs. *69* Diabetic instances).

---

## 🥊 Model Performance Comparison

The models were evaluated using the Test Set. Since clinical diagnostic tasks require minimizing False Negatives (missing a diabetic patient), *Recall* for Class 1 is a crucial metric alongside *Accuracy*.

| Model | Accuracy (Raw) | Accuracy (%) | Confusion Matrix (TN, FP / FN, TP) |
| :--- | :---: | :---: | :---: |
| *KNN (k=5)* | 0.7916 | *79.2%* | [114, 9] / [31, 38] |
| *Logistic Regression* | 0.7812 | *78.1%* | [108, 15] / [27, 42] |
| *SVM (RBF Kernel)* | 0.7812 | *78.1%* | [106, 17] / [25, 44] |
| *Naive Bayes (Gaussian)* | 0.7656 | *76.6%* | [101, 22] / [23, 46] |
| *Random Forest (10 trees)* | 0.7083 | *70.8%* | [105, 18] / [26, 43] |
| *Decision Tree (Entropy)* | 0.6979 | *69.8%* | [94, 29] / [29, 40] |

### 🔍 Key Insights from Data:
1. *Best Performer:* *KNN (k=5)* achieved the highest overall accuracy of *79.2%*, correctly classifying 114 non-diabetic cases.
2. *The Clinical Catch:* While KNN has the highest accuracy, *Naive Bayes* and *SVM* successfully captured more actual diabetic cases (46 and 44 True Positives respectively), making them highly relevant when prioritizing a higher Recall rate over overall Accuracy.
3. *Tree-Based Models:* Decision Tree and Random Forest (with 10 estimators) underperformed compared to distance-based and linear classifiers on this specific feature space.

---

## 🛠️ Tech Stack
* *Language:* Python 3
* *Environment:* Google Colab / Jupyter Notebook
* *Key Libraries:* scikit-learn, pandas, numpy, seaborn, matplotlib

---

## 🚀 Future Roadmap
To further elevate the model benchmarks:
* [ ] Implement *Hyperparameter Tuning* via GridSearchCV (especially for Random Forest n_estimators and KNN n_neighbors).
* [ ] Handle class imbalance using Synthetic Minority Over-sampling Technique (*SMOTE*) or adjusting class_weight.
* [ ] Explore Feature Selection based on the correlation matrix insights.

---
💡 Feel free to fork this repository, open issues, or submit pull requests!
