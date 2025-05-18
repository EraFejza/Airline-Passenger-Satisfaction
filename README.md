

##  Introduction

This project focuses on **airline passenger satisfaction prediction**, using a dataset that captures various aspects of the passenger flight experience. The dataset includes both training and testing subsets and is intended for **supervised binary classification**.

Each record in the dataset represents a single passenger and includes:

* **Demographic attributes** (e.g., Age, Type of Travel)
* **Service quality indicators** (e.g., In-flight Wi-Fi service, Seat comfort, Food and drink)
* **Flight-related details** (e.g., Departure/Arrival delays, Flight distance)

The **target variable** is binary:

* `0` → Dissatisfied passenger
* `1` → Satisfied passenger

Given the real-world nature of the features, this dataset offers a valuable opportunity to explore classification models and understand the **key drivers of customer satisfaction**. Through machine learning, we aim to uncover actionable patterns that airlines can leverage to **enhance customer experience and service delivery**.

---

##  Methodology

This project frames the task as a **binary classification problem** to predict whether a passenger is satisfied with their flight experience.

###  Class Balancing with SMOTE

Although not severely imbalanced, the dataset still showed **moderate class imbalance**. To address this and improve model fairness, we applied **SMOTE (Synthetic Minority Over-sampling Technique)** to balance the class distribution.

---

###  Data Preprocessing Pipeline

####  Data Cleaning & Handling Missing Values

* Inspected the dataset for missing or inconsistent values.
* Removed or imputed records with null entries (e.g., `NaN`).
* Ensured data consistency for features like `In-flight Wi-Fi service`, `Seat comfort`, and `Flight delays`.
* Converted non-numeric entries to numerical formats when needed.

####  Categorical Encoding

* Encoded categorical variables such as `Gender`, `Customer Type`, `Type of Travel`, and `Class`.
* Used a combination of **Label Encoding** and **One-Hot Encoding** depending on the context.

####  Feature Scaling

* Applied **StandardScaler** to standardize numeric features.
* Ensured all features have zero mean and unit variance.
* This step was crucial for algorithms like **SVM** and **kNN** that rely on distance metrics.

---

###  Train-Test Split

* Split the dataset into **80% training** and **20% testing** subsets.
* Used cross-validation to ensure **robust model performance** and **prevent overfitting**.

---

###  Model Tuning & Evaluation

* Used **Grid Search** and **Randomized Search** for hyperparameter tuning.
* Focused on models such as **MLP**, **LightGBM**, **Logistic Regression**, **SVM**, and **kNN**.
* Tuned key hyperparameters like:

  * Learning rate
  * Number of leaves
  * Hidden layer sizes
  * Activation functions
* Evaluated model performance using:

  * **Accuracy**
  * **Precision**
  * **Recall**
  * **F1-Score**

This comprehensive methodology allowed us to not only improve model accuracy but also **better understand the importance of each feature** in predicting passenger satisfaction.

