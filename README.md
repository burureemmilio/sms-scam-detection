# sms-scam-detection
# SMS Scam Detection Using Explainable Machine Learning

### An End-to-End Data Science Project for Detecting Fraudulent SMS Messages in the Kenyan Mobile Money Context

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Scikit--learn-orange)
![NLP](https://img.shields.io/badge/NLP-TF--IDF-green)
![Streamlit](https://img.shields.io/badge/Deployment-Streamlit-red)
![Status](https://img.shields.io/badge/Status-Research%20Prototype-yellow)

## Project Overview

SMS scams pose a significant cybersecurity and financial risk, particularly in countries such as Kenya, where mobile money services are widely used.

Fraudsters exploit SMS communication through fake transaction notifications, phishing links, impersonation, fraudulent rewards, and social engineering techniques.

This project develops an **Explainable Machine Learning System for SMS Scam Detection**, combining Natural Language Processing (NLP), supervised machine learning, statistical evaluation, and explainable artificial intelligence.

Unlike conventional SMS classification projects, this research places particular emphasis on:

- Data quality and leakage prevention
- Duplicate and near-duplicate detection
- Rigorous model comparison
- Nested cross-validation
- Classification threshold optimization
- Statistical confidence intervals
- Explainable predictions
- Interactive model deployment

The final solution uses a trained classification pipeline integrated into a Streamlit application.

---

## Problem Statement

Traditional rule-based SMS filtering systems struggle to adapt to evolving fraud techniques.

Machine learning provides an alternative by learning patterns from previously labeled messages.

However, SMS datasets often contain duplicated messages, repeated templates, class imbalance, and labeling inconsistencies that can produce misleading evaluation results.

This project investigates whether machine learning models can reliably identify suspicious SMS messages while minimizing data leakage and providing interpretable predictions.

## Project Objectives

1. Develop a supervised machine learning system for SMS scam classification.
2. Investigate data quality issues and potential sources of leakage.
3. Apply NLP techniques to transform SMS messages into numerical features.
4. Compare multiple classification algorithms.
5. Optimize model hyperparameters using cross-validation.
6. Evaluate model performance using robust statistical methods.
7. Investigate the effects of duplicate and near-duplicate messages.
8. Optimize classification thresholds to prioritize scam detection.
9. Explain predictions using interpretable machine learning techniques.
10. Develop an interactive application for testing SMS messages.

---

## Dataset

The project uses a labeled SMS dataset relevant to the Kenyan mobile money environment.

| Attribute | Description |
|---|---|
| Data Type | SMS Text Messages |
| Target Variable | `label` |
| Classification Type | Binary Classification |
| Positive Class | Scam |
| Negative Class | Legitimate |
| Unique Messages After Cleaning | 643 |
| Held-Out Test Messages | 128 |

### Data Preprocessing

The preprocessing pipeline includes:

- Data auditing
- Duplicate identification
- Conflicting-label investigation
- Text normalization
- Data cleaning
- Near-duplicate grouping
- Data leakage prevention
- Stratified group-aware splitting

Potentially target-revealing columns were excluded from model training.

---

## Exploratory Data Analysis

Exploratory Data Analysis was conducted to understand the characteristics of fraudulent and legitimate SMS messages.

### Areas Investigated

- Class distribution
- SMS length distribution
- Word frequencies
- Character patterns
- URL occurrences
- Phone number patterns
- Numerical features
- Urgency-related language
- Threat-related vocabulary
- Differences between scam and legitimate messages

These findings informed feature engineering and model development.

---

## Methodology

The project follows a structured end-to-end machine learning workflow:

```text
Raw SMS Dataset
       |
       v
Data Auditing
       |
       v
Data Cleaning & Preprocessing
       |
       v
Exploratory Data Analysis
       |
       v
Feature Engineering
       |
       v
Train-Test Splitting
       |
       v
Model Training
       |
       v
Hyperparameter Optimization
       |
       v
Nested Cross-Validation
       |
       v
Model Selection
       |
       v
Threshold Optimization
       |
       v
Final Model Evaluation
       |
       v
Explainable AI
       |
       v
Streamlit Application
```

---

## Natural Language Processing

The project uses **Term Frequency–Inverse Document Frequency (TF-IDF)** to convert textual SMS messages into numerical representations.

Techniques investigated include:

- Text normalization
- Word-level TF-IDF
- Unigrams
- Character n-grams
- Vocabulary analysis
- Linguistic feature extraction
- Combining textual and numerical features

### Feature Engineering

Additional features capture characteristics commonly associated with suspicious messages.

Examples include:

- URL presence
- Number of digits
- Phone number patterns
- USSD codes
- Monetary references
- Capitalization patterns
- Exclamation marks
- Urgency-related vocabulary
- Threat-related expressions

---

## Machine Learning Models

Three supervised classification algorithms were developed and evaluated.

| Model | Description |
|---|---|
| Multinomial Naive Bayes | Probabilistic text classifier |
| Logistic Regression | Linear binary classifier |
| Linear Support Vector Machine | Maximum-margin classifier |

### Model Optimization

The project incorporates:

- Scikit-learn pipelines
- Stratified group cross-validation
- Nested cross-validation
- Hyperparameter tuning
- Regularization
- Class weighting
- ROC-AUC-based model selection
- Decision threshold optimization

Model selection was performed using a predefined evaluation procedure to reduce selection bias.

---

## Data Leakage Investigation

A major contribution of this project is investigating the effects of duplicated and highly similar messages on classification performance.

### Experimental Results

| Evaluation Strategy | Logistic Regression F1 |
|---|---:|
| Naive Evaluation | 0.923 |
| Exact Duplicate Grouping | 0.915 |
| Deduplicated Dataset | 0.909 |
| Deduplication + Near-Duplicate Grouping | 0.908 |

### Key Finding

Evaluation strategies that fail to account for duplicated or highly similar messages can produce overly optimistic performance estimates.

This demonstrates the importance of leakage-aware evaluation when developing machine learning systems for text classification.

---

## Model Evaluation

Logistic Regression was selected as the final model through the predefined nested cross-validation procedure.

### Final Test Performance

| Metric | Score |
|---|---:|
| Accuracy | 89.8% |
| Precision | 87.8% |
| Recall | 96.0% |
| F1-Score | 91.7% |
| ROC-AUC | 93.3% |

### Interpretation

The model achieved a recall of **96.0%**, indicating that it successfully identified a high proportion of scam messages within the held-out test dataset.

The F1-score of **91.7%** demonstrates a strong balance between precision and recall on this dataset.

However, these results should not be interpreted as guaranteed real-world performance.

### Threshold Optimization

The final classification threshold was approximately **0.32**.

The threshold was optimized using out-of-fold predictions with the objective of maintaining at least 95% scam recall.

This approach prioritizes detecting potentially fraudulent messages while acknowledging the possibility of false positives.

---

## Explainable Artificial Intelligence

Explainability is an important component of the project.

Rather than producing only a classification label, the system provides information about the factors influencing its predictions.

### Explainability Techniques

- Global feature importance
- Logistic Regression coefficient analysis
- Local prediction explanations
- Feature contribution analysis
- Coefficient stability analysis
- False-positive investigation
- False-negative investigation

These techniques improve the interpretability of predictions and support more transparent model behavior.

---

## Streamlit Application

The project includes an interactive web application developed using Streamlit.

### Application Features

- Enter an SMS message
- Classify messages as scam or legitimate
- Display the model's scam score
- Highlight suspicious indicators
- Provide interpretable prediction explanations
- Present model limitations

The application integrates the trained classification pipeline with a user-friendly interface.

**Deployment status:** The application is included in the repository, but successful execution should be verified locally before treating it as a fully tested deployment.

---

## Technologies Used

| Category | Technologies |
|---|---|
| Programming | Python |
| Data Manipulation | Pandas, NumPy |
| Data Visualization | Matplotlib, Seaborn |
| Machine Learning | Scikit-learn |
| NLP | TF-IDF |
| Statistical Analysis | SciPy |
| Model Serialization | Joblib |
| Web Application | Streamlit |
| Development Environment | Jupyter Notebook |
| Version Control | Git, GitHub |

---

## Project Structure

```text
sms-scam-detection/
│
├── data/
│   ├── scam_detection_labeled.csv
│   ├── cleaned_messages.csv
│   └── split.csv
│
├── notebooks/
│   ├── 01_data_audit.ipynb
│   ├── 02_eda.ipynb
│   ├── 03_model_training.ipynb
│   ├── 04_evaluation_explainability.ipynb
│   └── 05_optional_three_class.ipynb
│
├── src/
│   ├── __init__.py
│   ├── preprocessing.py
│   ├── train.py
│   ├── evaluation.py
│   ├── predict.py
│   └── make_figures.py
│
├── models/
│   ├── final_model.joblib
│   ├── dev_models.joblib
│   ├── final_config.json
│   ├── selection.json
│   └── model_card.json
│
├── reports/
│   ├── figures/
│   ├── final_report.md
│   ├── final_report.docx
│   ├── presentation.pptx
│   ├── test_results.csv
│   ├── tuning_grid_results.csv
│   ├── leakage_experiment.csv
│   └── feature_experiment.csv
│
├── app.py
├── requirements.txt
└── README.md
```

---

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/burureemmilio/sms-scam-detection.git
```

### 2. Navigate to the Project Directory

```bash
cd sms-scam-detection
```

### 3. Create a Virtual Environment

```bash
python -m venv venv
```

Activate the environment:

**Windows**

```bash
venv\Scripts\activate
```

**macOS/Linux**

```bash
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Launch the Streamlit Application

```bash
streamlit run app.py
```

The application should open in your browser.

### 6. Explore the Notebooks

```bash
jupyter notebook
```

Navigate to the `notebooks/` directory to explore the experiments.

---

## Research Questions

The research investigates:

1. How effectively can supervised machine learning models distinguish scam SMS messages from legitimate messages?
2. Which textual and structural features are most informative for SMS scam classification?
3. How do duplicate messages and near-duplicate templates influence model evaluation?
4. How does classification threshold optimization affect precision and recall?
5. How can explainable machine learning improve transparency in SMS scam detection?

---

## Key Findings

- Logistic Regression demonstrated strong classification performance.
- TF-IDF features were effective for representing SMS text.
- Duplicate and near-duplicate messages influenced evaluation results.
- Leakage-aware evaluation provided a more conservative assessment of model performance.
- Threshold optimization supported high scam recall.
- Coefficient-based explanations helped identify influential textual features.

---

## Project Limitations

Despite promising results, several limitations remain:

- The dataset contains only 643 unique messages.
- Dataset annotations are not independently verified ground truth.
- The dataset may not fully represent real-world SMS traffic.
- Some legitimate messages may be incorrectly flagged as scams.
- New scam techniques may not resemble examples in the training dataset.
- Generalization to other languages, regions and messaging platforms has not been established.
- The system is a research prototype and not a production-grade fraud detection solution.

---

## Future Improvements

Potential extensions include:

- Expanding the dataset with additional Kenyan SMS messages.
- Evaluating the model on an independent external dataset.
- Incorporating SHAP explainability.
- Investigating multilingual SMS scam detection.
- Exploring LSTM and transformer-based classifiers.
- Evaluating model performance over time.
- Improving application security and privacy.
- Deploying a production-ready version.

---

## Skills Demonstrated

This project demonstrates practical knowledge of:

- Python Programming
- Data Cleaning and Preprocessing
- Exploratory Data Analysis
- Statistical Analysis
- Natural Language Processing
- Feature Engineering
- Supervised Machine Learning
- Model Selection
- Hyperparameter Optimization
- Cross-Validation
- Data Leakage Prevention
- Classification Metrics
- Explainable Artificial Intelligence
- Model Deployment
- Research Methodology
- Technical Documentation

---

## Author

**Emmilio Burure**

Data Science | Machine Learning | NLP | Explainable AI

**GitHub:** https://github.com/burureemmilio

**LinkedIn:** https://www.linkedin.com/in/emmilio-burure-17b7963b4/

---

## Disclaimer

This project was developed for educational and research purposes.

The classification system should not be considered a definitive fraud detection tool. Predictions may contain false positives or false negatives.

Users should independently verify suspicious messages through official communication channels before taking action.
