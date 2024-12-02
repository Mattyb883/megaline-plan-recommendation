# Predicting Mobile Plans with Machine Learning

## Overview
This project aims to build a machine learning model that analyzes subscriber behavior and recommends one of two mobile plans offered by Megaline:
1. **Smart Plan**
2. **Ultra Plan**

By leveraging historical data and predictive modeling, the system assists Megaline in optimizing plan recommendations for its subscribers.

## Dataset
The dataset contains monthly behavior information for Megaline subscribers, including:
- **calls**: Number of calls made.
- **minutes**: Total call duration in minutes.
- **messages**: Number of text messages sent.
- **mb_used**: Internet traffic used in megabytes.
- **is_ultra**: Target variable indicating the current plan (1 = Ultra, 0 = Smart).

## Project Workflow
1. **Data Cleaning and Preparation**:
   - Addressed missing values, duplicates, and outliers to ensure a high-quality dataset.
2. **Data Splitting**:
   - Divided the dataset into training, validation, and test sets using a 60/20/20 split with stratification.
3. **Model Training and Evaluation**:
   - Evaluated three models:
     - Logistic Regression
     - Decision Tree
     - Random Forest
   - Hyperparameter tuning was performed on the Random Forest model to optimize its performance.
4. **Addressing Class Imbalance**:
   - Adjusted for class imbalance using `class_weight="balanced"` in the Random Forest model to improve recall for the minority class (Ultra Plan).
5. **Model Testing**:
   - Evaluated the final model on the test dataset to ensure robust performance.

## Results
- **Best Model**: Random Forest
- **Test Set Accuracy**: 0.7588
- **Key Metrics**:
  - **Class 0 (Smart Plan)**:
    - Precision: 0.83, Recall: 0.85, F1-Score: 0.84
  - **Class 1 (Ultra Plan)**:
    - Precision: 0.54, Recall: 0.50, F1-Score: 0.52
- **Confusion Matrix**:
  |               | Predicted: Smart (0) | Predicted: Ultra (1) |
  |---------------|-----------------------|-----------------------|
  | **Actual: Smart (0)** | 376                   | 66                    |
  | **Actual: Ultra (1)** | 78                    | 77                    |

## Tools and Libraries
- **Python**: Programming language for data processing and model training.
- **Libraries Used**:
  - `pandas` and `numpy` for data manipulation.
  - `scikit-learn` for machine learning models, hyperparameter tuning, and evaluation.

## Recommendations and Future Work
- Address further class imbalance using oversampling techniques like SMOTE to improve recall for the Ultra Plan.
- Explore advanced models such as Gradient Boosting (e.g., XGBoost or LightGBM) for potentially better performance.
- Investigate feature engineering to enhance predictive power.

## How to Run
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-repo-name/predicting-mobile-plans.git
