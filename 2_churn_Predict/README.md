# Project 2: Customer Churn Prediction - Ensembles vs. Deep Learning

## 1. Project Goal
The objective of this project is to predict customer churn for a telecommunications company using a tabular dataset. The primary goal is to compare the performance of traditional, powerful ensemble methods (Random Forest, XGBoost) against a custom-built Deep Neural Network (DNN).

This project demonstrates proficiency in:
- End-to-end data preprocessing for tabular data: handling missing values, categorical encoding, and numerical scaling.
- Implementing and tuning powerful ensemble models like Random Forest and XGBoost.
- Building, training, and regularizing a DNN for a classification task on tabular data.
- Addressing class imbalance using the SMOTE (Synthetic Minority Over-sampling Technique).
- Comprehensive model evaluation using metrics appropriate for imbalanced datasets (Precision, Recall, F1-score, ROC AUC).
- Drawing insightful comparisons between different modeling approaches.

## 2. Dataset
- **Source:** [Telco Customer Churn on Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)
- **Description:** The dataset contains customer information including demographics, services they've signed up for, account information, and a target column `Churn` indicating whether the customer left within the last month.
- **Features:** A mix of categorical (e.g., `gender`, `InternetService`) and numerical (e.g., `tenure`, `MonthlyCharges`) features.
- **Challenge:** The dataset has a moderate class imbalance, with significantly fewer "Churn" instances than "No Churn".

## 3. Models Implemented

### Model 1: Random Forest Classifier
A robust ensemble method based on bagging. It builds multiple decision trees on different subsets of the data and averages their predictions. It's known for its high accuracy and resistance to overfitting.

### Model 2: XGBoost Classifier
A state-of-the-art gradient boosting model. It builds trees sequentially, where each new tree corrects the errors of the previous ones. It is often a top performer in machine learning competitions on tabular data.

### Model 3: Deep Neural Network (DNN)
A custom-built DNN using TensorFlow/Keras. The architecture includes:
- Multiple `Dense` layers with `ReLU` activation.
- `BatchNormalization` layers to stabilize and accelerate training.
- `Dropout` layers for regularization to prevent overfitting.
- A `Sigmoid` activation in the final layer for binary classification output.

## 4. Key Steps in the Notebook
1.  **Data Loading & EDA:** Load the dataset, perform an initial Exploratory Data Analysis (EDA) to understand feature distributions, correlations, and the class imbalance.
2.  **Data Preprocessing:**
    -   Clean and prepare the data for modeling.
    -   Encode categorical features using One-Hot Encoding.
    -   Scale numerical features using `StandardScaler`.
3.  **Handling Class Imbalance:** Apply `SMOTE` to the training data to create synthetic samples of the minority class (Churn), leading to a balanced training set.
4.  **Model Training:**
    -   Train the `RandomForestClassifier` and `XGBoostClassifier`.
    -   Train the custom `DNN`, utilizing `EarlyStopping` to prevent overfitting.
5.  **Evaluation:**
    -   Evaluate all models on the *original, un-SMOTEd* test set to get a realistic performance measure.
    -   Key metrics used are `Accuracy`, `Precision`, `Recall`, `F1-score` (especially for the 'Churn' class), and `ROC AUC Score`.
    -   Visualize results with Confusion Matrices and ROC Curves.
6.  **Comparison & Conclusion:** Compare the models based on their performance metrics, training time, and interpretability.

## 5. Results
| Model                 | ROC AUC Score | F1-Score (Churn) | Key Observation                                                |
|-----------------------|---------------|------------------|----------------------------------------------------------------|
| Random Forest         | ~0.84         | ~0.61            | Strong baseline performance, good interpretability of features.  |
| **XGBoost**           | **~0.85**     | **~0.63**        | Often the top performer, highly efficient and powerful.        |
| Deep Neural Network   | ~0.83         | ~0.60            | Competitive performance, but requires more careful tuning and scaling. |

The results show that for this structured, tabular dataset, well-tuned ensemble methods like XGBoost often have a slight edge in performance and are typically faster to train and easier to interpret than a DNN. The DNN is a powerful tool but may be overkill for this type of problem unless the dataset is extremely large and contains very complex non-linearities. This project highlights the importance of choosing the right tool for the job.