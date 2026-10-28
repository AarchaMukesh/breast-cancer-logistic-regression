# Logistic Regression on Breast Cancer Wisconsin Dataset

## Overview

This project implements a **Logistic Regression** model to classify breast tumours as benign or malignant using the Breast Cancer Wisconsin (Diagnostic) dataset.

The project demonstrates a beginner-level machine learning workflow, including data exploration, data cleaning, feature scaling, model training, and evaluation using classification metrics.

## Dataset

The dataset was downloaded from Kaggle:

- **Dataset:** [Breast Cancer Wisconsin (Diagnostic) Data Set](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data)
- **Original source:** UCI Machine Learning Repository
- **File used:** `data/breast-cancer.csv`
- **Number of samples:** 569
- **Number of numerical features:** 30
- **Target variable:** `diagnosis`

The dataset contains numerical measurements computed from digitized images of breast mass samples.

### Target Variable

The `diagnosis` column represents the tumour diagnosis:

- `0` — Benign
- `1` — Malignant

## Project Workflow

The following steps were performed in this project:

1. **Data Loading:** Loaded the dataset using Pandas.
2. **Data Exploration:** Examined the dataset structure, column names, descriptive statistics, and missing values.
3. **Data Cleaning:** Removed unnecessary columns such as `id` and `Unnamed: 32`.
4. **Target Encoding:** Converted diagnosis labels into numerical values.
5. **Feature-Target Separation:** Separated the input features (`X`) from the target variable (`y`).
6. **Train-Test Split:** Split the dataset into training and testing sets using an 80:20 ratio.
7. **Feature Scaling:** Standardized the features using `StandardScaler`. The scaler was fitted on the training data and then applied to the test data to prevent data leakage.
8. **Model Training:** Trained a Logistic Regression classifier using Scikit-learn.
9. **Model Evaluation:** Evaluated the model using accuracy, precision, recall, F1-score, and a confusion matrix.

## Model

**Algorithm:** Logistic Regression

Logistic Regression is a supervised machine learning algorithm used for classification. It estimates the probability of a sample belonging to a particular class.

In this project, the model predicts whether a tumour is benign or malignant based on the 30 numerical input features.

## Results

The model achieved the following performance on the held-out test set:

| Metric | Result |
|---|---:|
| Total test samples | 114 |
| Correct predictions | 110 |
| Incorrect predictions | 4 |
| Test accuracy | 96.49% |

### Confusion Matrix

| Actual / Predicted | Benign (0) | Malignant (1) |
|---|---:|---:|
| Benign (0) | 71 | 1 |
| Malignant (1) | 3 | 39 |

### Interpretation

- **True Negatives (71):** Benign tumours correctly classified as benign.
- **False Positives (1):** Benign tumours incorrectly classified as malignant.
- **False Negatives (3):** Malignant tumours incorrectly classified as benign.
- **True Positives (39):** Malignant tumours correctly classified as malignant.

The model achieved approximately **96.49% test accuracy** on this split.

Although the accuracy is high, the three false negatives demonstrate why recall and other classification metrics are important, especially in medical classification problems.

These results represent one train-test split and do not establish clinical reliability.

## Technologies Used

- Python
- Pandas
- Scikit-learn
- Matplotlib
- Seaborn
- Jupyter Notebook

## Repository Structure

```text
logistic-regression/
├── data/
│   └── breast-cancer.csv
├── notebooks/
│   └── logistic-reg-with-python.ipynb
├── README.md
└── .gitignore
```

## How to Run the Project

### 1. Clone the repository

```bash
git clone <your-github-repository-url>
```

### 2. Navigate to the project directory

```bash
cd logistic-regression
```

### 3. Install the required libraries

```bash
pip install pandas scikit-learn matplotlib seaborn jupyter
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open `notebooks/logistic-reg-with-python.ipynb` and run the cells in order.

## Key Learnings

Through this project, I learned:

- How Logistic Regression works for binary classification.
- How to explore and clean a real-world dataset.
- How to separate features and target variables.
- How to split data into training and testing sets.
- Why feature scaling is important for Logistic Regression.
- How to avoid data leakage during preprocessing.
- How to evaluate classification models using accuracy, precision, recall, F1-score, and a confusion matrix.
- How to interpret classification errors.

## Limitations

This is an educational machine learning project intended to demonstrate a basic classification workflow. The model has not been validated for clinical use and must not be used to diagnose medical conditions.

## Acknowledgements

- [Kaggle — Breast Cancer Wisconsin (Diagnostic) Dataset](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data)
- [UCI Machine Learning Repository](https://archive.ics.uci.edu/)

