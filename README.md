# 🏥 Hospital Analytics & Machine Learning

An end-to-end data analytics and machine learning project focused on exploring hospital information, understanding hospital ratings, and building a model to predict overall hospital ratings using hospital characteristics.

Dashboard: https://app.powerbi.com/view?r=eyJrIjoiZDFmNzM3MjEtMzc1MS00MTU1LWI0YWItMzIyOWE0NjhmNDg4IiwidCI6ImJhZDEyODY0LTkxM2UtNGI5OS04N2Q2LWI4ZDJhZDQ1OWUyNyIsImMiOjEwfQ%3D%3D&embedImagePlaceholder=true 

## 📌 Project Overview

Healthcare data can provide valuable insights into hospital distribution, ownership, emergency service availability, and overall ratings. This project analyzes hospital information to identify patterns, compare rating distributions, and explore the relationship between hospital characteristics and overall ratings.

The project combines data analysis, statistical testing, machine learning, and interactive Power BI visualizations to turn raw hospital data into meaningful insights.

## 🎯 Project Objectives

- Understand and analyze hospital information across different states.
- Clean and prepare raw data for reliable analysis.
- Explore hospital ratings and distributions by ownership, type, and emergency service availability.
- Perform statistical tests to investigate differences in hospital ratings between groups.
- Develop and evaluate a machine learning model for predicting hospital ratings.
- Present key findings through a Power BI dashboard.

## 📊 Dataset Description

**Dataset:** Hospital General Information

The dataset contains hospital-level information, including:

- **State:** State where the hospital is located.
- **Hospital Type:** Classification of the hospital.
- **Hospital Ownership:** Ownership category of the hospital.
- **Emergency Services:** Whether emergency services are available.
- **Hospital Overall Rating:** Overall rating assigned to the hospital, ranging from 1 to 5 where available.

The original dataset contains approximately 5,419 records and 38 columns. The exact number of usable records can vary after data cleaning and the removal of records without valid ratings for model training.

## 🧹 Data Cleaning and Preparation

The raw dataset was prepared for analysis through the following steps:

- Inspected dataset dimensions, column names, and data types.
- Identified missing values and standardized different missing-value representations.
- Checked for duplicate records and repeated identifiers.
- Removed empty or unnecessary columns where appropriate.
- Cleaned column names and standardized data formats.
- Converted hospital overall ratings into numeric values.
- Saved the cleaned dataset for subsequent analysis.

These steps helped improve data consistency and prepare the dataset for exploratory analysis, statistical testing, and machine learning.

## 🔍 Exploratory Data Analysis (EDA)

Exploratory Data Analysis was performed to understand the structure and characteristics of the dataset.

Key analyses included:

- Distribution of hospital overall ratings.
- Number of hospitals across states.
- Distribution of hospitals by ownership category.
- Distribution of hospitals by hospital type.
- Availability of emergency services.
- Missing-value analysis and numerical summaries.
- Comparison of average and median ratings across hospital categories.
- Identification of patterns and differences in hospital ratings.

Visualizations and summary tables were used to make the results easier to interpret.

## 📈 Statistical Analysis

Statistical tests were used to examine whether hospital ratings differed across selected groups.

The analysis included:

- **Kruskal–Wallis test:** Used to compare rating distributions across multiple groups, such as hospital ownership categories, hospital types, and states.
- **Mann–Whitney U test:** Used to compare rating distributions between two groups, such as hospitals with and without emergency services.
- **P-values:** Used to assess statistical significance.
- **Adjusted p-values:** A multiple-testing adjustment was applied to account for the three planned comparisons.

A significance threshold of **0.05** was used when interpreting adjusted p-values. These tests help identify statistical differences but do not establish that a hospital characteristic causes a higher or lower rating.

## 🤖 Machine Learning Model

### Model Objective

The machine learning component predicts a hospital's overall rating using selected hospital characteristics.

**Target variable:** `hospital_overall_rating`

**Input features:**
- `state`
- `hospital_type`
- `hospital_ownership`
- `emergency_services`

Only features available in the dataset are used. Records without valid target ratings from 1 to 5 are excluded from model training.

### Algorithm Used

**Random Forest Classifier**

Random Forest is an ensemble classification algorithm that combines predictions from multiple decision trees. It is suitable for classification tasks involving categorical features and can capture complex relationships between input variables and the target.

A simple majority-class baseline model was also implemented to provide a reference point for evaluating the Random Forest model.

### Model Configuration

| Parameter | Value |
|---|---|
| Algorithm | Random Forest Classifier |
| Number of trees (`n_estimators`) | 200 |
| Random state | 42 |
| Class weighting | `balanced` |
| Minimum samples per leaf | 5 |
| Parallel processing (`n_jobs`) | -1 |
| Test dataset size | 20% |
| Training dataset size | 80% |

### Data Preprocessing

The machine learning pipeline includes:

- **Missing-value handling:** Missing categorical values are replaced with the label `Missing`.
- **Categorical encoding:** One-hot encoding converts categorical variables into a numerical representation.
- **Unknown categories:** `handle_unknown="ignore"` allows the encoder to handle categories not seen during training.
- **Train-test split:** The data is divided into training and testing sets using `random_state=42`. Stratified splitting is used when the class distribution permits it.

The preprocessing steps and classifier are combined into a single pipeline to maintain a consistent process during training and prediction.

### Model Evaluation

The model is evaluated using the following metrics and diagnostic tools:

- **Accuracy:** Measures the proportion of correct predictions.
- **Macro F1-score:** Calculates the F1-score for each rating class and gives each class equal weight.
- **Classification report:** Summarizes precision, recall, and F1-score for the rating classes.
- **Confusion matrix:** Shows the relationship between actual and predicted ratings.
- **Feature importance:** Helps identify which input features contribute most to the fitted Random Forest model.

The Random Forest results are compared with the majority-class baseline to assess whether the model provides useful predictive performance. Actual evaluation scores should be taken from the executed notebook results rather than assumed in advance.

The trained model is saved as a `.pkl` file using Joblib for later reuse.

## 📊 Power BI Dashboard

An interactive Power BI report was developed to present important findings from the hospital dataset.

The dashboard focuses on:

- Hospital distribution across states.
- Hospital overall rating distribution.
- Hospital ownership and hospital type.
- Emergency service availability.
- Key summary indicators and comparisons.

The report contains three pages designed to help users explore the data and understand its major patterns visually.

**Dashboard report:** `dashboard/Data_Analytics_project.pdf`

## 🛠️ Technologies and Tools

- **Python:** Data processing, analysis, statistical testing, and machine learning.
- **Pandas:** Data manipulation and tabular analysis.
- **NumPy:** Numerical operations.
- **Matplotlib:** Data visualization.
- **SciPy:** Statistical hypothesis testing.
- **Scikit-learn:** Data preprocessing, Random Forest classification, baseline modeling, and model evaluation.
- **Joblib:** Saving and loading the trained model.
- **Jupyter Notebook:** Executing and documenting the analysis workflow.
- **Power BI:** Interactive dashboard development.
- **Git and GitHub:** Version control and project hosting.

## 💡 Key Outcomes

This project brings together multiple stages of a practical analytics workflow:

- Prepared raw hospital information for analysis.
- Explored hospital distributions and rating patterns.
- Used statistical methods to compare ratings across hospital groups.
- Built a Random Forest classification pipeline with a baseline comparison.
- Evaluated model predictions using classification metrics and a confusion matrix.
- Presented findings through a Power BI report.

The project demonstrates how data analytics and machine learning can be applied to healthcare-related datasets. Model predictions are exploratory and should not be treated as a definitive measure of hospital quality or as a substitute for clinical or regulatory assessment.

## 👤 Author

**Vishal Chopra**

GitHub: [@vishchopra227](https://github.com/vishchopra227)

---

If you find this project useful, consider giving the repository a ⭐ on GitHub.
