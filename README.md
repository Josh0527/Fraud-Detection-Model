# Fraud Detection Model README

## Project Overview
This project aims to develop a robust fraud detection model that identifies suspicious transactions. The model leverages data preprocessing techniques, feature engineering, and machine learning algorithms to achieve balanced performance.

## Objective
The objective was to build a model that accurately detects fraudulent transactions without overfitting or relying heavily on specific high-impact features.

## Workflow
### 1. Data Collection
- Collected transactional data with features like user activity, payment details, and risk indicators.

### 2. Data Preprocessing
- Handled missing values through imputation.
- Converted categorical variables such as `Authentication_Method` and `Transaction_Type` into numeric format using **one-hot encoding**.
- Created a **temporary DataFrame** excluding `Risk_Score` and `Failed_Transaction_Count_7d` to isolate their influence on model performance.

### 3. Feature Engineering
- Created new features like transaction frequency counts and calculated risk scores.
- Identified high-correlation features (`Risk_Score` and `Failed_Transaction_Count_7d`) that led to overfitting. These were excluded to improve model performance.

### 4. Data Balancing
- Applied **SMOTE (Synthetic Minority Over-sampling Technique)** to address class imbalance and improve recall for minority (fraud) cases.

### 5. Model Architecture
- Utilized a **RandomForestClassifier** for its robustness and ability to handle tabular data.
- Implemented **SelectKBest** for feature selection to enhance efficiency and performance.

### 6. Model Training
- Trained the RandomForestClassifier with optimal hyperparameters.
- Employed **Mean Squared Error (MSE)** as the primary loss function.

### 7. Evaluation & Validation
- Evaluated model performance using:
  - **Accuracy**
  - **Precision**
  - **Recall**
  - **F1-score**
  - **ROC-AUC score**

### Results
- Post-exclusion accuracy dropped to **67%**, confirming the model's initial reliance on `Risk_Score` and `Failed_Transaction_Count_7d`.
- After refining the feature set and applying SMOTE, the model achieved:
  - **Accuracy:** 92%
  - **ROC-AUC Score:** 0.93

### Key Learnings
- Creating a **temporary DataFrame** was crucial in identifying overfitting features and improving model generalization.
- SMOTE effectively balanced the dataset and improved recall for fraudulent cases.

## Installation
To run the model locally:
1. Clone this repository:
```bash
git clone https://github.com/your-repo/fraud-detection.git
```
2. Install dependencies:
```bash
pip install -r requirements.txt
```
3. Run the model training script:
```bash
python model_F.py
```

## Dependencies
- Python 3.10+
- Pandas
- NumPy
- Scikit-learn
- Imbalanced-learn

## Future Improvements
- Implement advanced ensemble techniques for improved prediction accuracy.
- Incorporate real-time anomaly detection methods.
- Fine-tune hyperparameters for optimized model performance.

For further inquiries, please contact [Sunkanmi](mailto:tojoshua0527@gmail.com).

