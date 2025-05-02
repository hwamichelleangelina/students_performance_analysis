# Students' Performance Analysis & Dropout Early Prediction

This project explores the **key factors influencing student dropout** at Jaya Jaya Institut through **Exploratory Data Analysis (EDA)**, statistical testing, machine learning models for early prediction, and dashboard visualization to support proactive academic interventions and improve student retention.

## Background
Jaya Jaya Institute is a higher education institution established in 2000 that has produced many high-quality graduates. However, the institution is currently facing a serious challenge: a high dropout rate among students.

This issue not only affects the institution’s reputation but also impacts operational efficiency and the individual success of students. Therefore, Jaya Jaya Institute aims to detect students at risk of dropping out as early as possible in order to provide them with targeted interventions and guidance.

## Business Understanding:

* **Objective:** Help Jaya Jaya Institute identify and predict students who are at risk of dropping out as early as possible, so they can receive special guidance before they actually leave the institution.

* **Main Problem:** The high dropout rate poses a major challenge to the institution's reputation and quality. A lack of understanding of the main causes makes preventive efforts less effective.

* **Problem Statement (Business Questions):**

  * What are the main factors that most influence a student's decision to drop out?
  * What are the decision-supporting features that indirectly influence these factors?
  * How can the institution efficiently monitor student performance and take timely action?

* **Target:**

  * Explore and understand student data patterns through machine learning to predict dropout probability.
  * Identify data-driven strategies and solutions to reduce the dropout rate and improve student retention.
  * Provide data visualizations for academic staff to monitor student performance and take data-based preventive actions.

### Project Scope

* Exploration and processing of student dataset to determine feature importance related to student status.
* Feature engineering to create derived attributes that support prediction.
* Training and evaluation of multiple machine learning models (Random Forest, XGBoost, Deep Learning).
* Ensemble modeling to improve prediction accuracy.
* Development of a Machine Learning model using Python to display prediction results.
* Prototyping of a user-facing application using Streamlit.
* Development of a data visualization dashboard.

### Preparation

**Data source**: [students' performance](https://github.com/hwamichelleangelina/students_performance_analysis/blob/main/data.csv)

**Environment setup**:
Ensure the Python environment is equipped with the following libraries:

```
pip install -r requirements.txt
```

**Project structure**:

```
├─── `app.py` – Streamlit application
├─── `notebook.ipynb` – Notebook for exploration and model training
├─── `requirements.txt` – Library requirements
├─── model
  ├─── `xgb_model.pkl` – XGBoost model
  ├─── `rf_model_compressed.pkl` – Random Forest model
  ├─── `dl_model.h5` – Deep Learning (Keras) model
  ├─── `meta_model.pkl` – Ensemble model
  ├─── `scaler.pkl` – StandardScaler object
  ├─── `scaler_columns.pkl` – StandardScaler with column names
  └─── `label_encoders.pkl` – Label encoders
└─── data.csv – Dataset
```

## Business Dashboard

The dashboard is designed to visualize and monitor key factors affecting student status in an interactive way. The visualizations include:

* Distribution and comparison of student status based on key features such as tuition payment, student grades, etc.
* Monitoring of student demographics.
* Insights based on student group segmentation.
* **Business Dashboard**: [Jaya Jaya Institute Students' Performance Analysis Dashboard](https://lookerstudio.google.com/reporting/275ca653-22b8-4fde-a66d-e35619cd6f57)

## Running the Machine Learning System

To run the prediction system:

1. Make sure all model files (`.pkl` and `.h5`) are in the same directory. Also ensure Streamlit is installed:

```
pip install streamlit
```

2. Run `app.py`:

```
python app.py
```

3. Follow the prompts to input student data.
4. The system will process the input and display the predicted student status.

**Sample output**:

```
Predicted Student Status: Graduate
```

Deployment is available at Streamlit Cloud: [https://jaya-jaya-students-status.streamlit.app/](https://jaya-jaya-students-status.streamlit.app/)

## Utilized Tools

* **Jupyter Notebook**: For data processing, EDA, and model development
* **Looker Studio Dashboard**: Jaya Jaya Institute Students' Performance Analysis Dashboard for Academic Monitoring

## Project Overview

The primary objective of this project is to identify and predict significant factors that influence student status—whether a student will **drop out**, **remain enrolled**, or **graduate**—to support early intervention and strategic academic support planning.

## Steps Taken

1. **Exploratory Data Analysis (EDA)**

   * Analyzed relationships between academic, financial, and demographic features and student outcomes
   * Utilized visual tools such as correlation heatmaps, bar charts, and distribution plots.

2. **Statistical Testing**

   * Conducted **Chi-Square Tests** and **T-Tests** to identify features with significant impact on student status.

3. **Machine Learning & Deep Learning Models**

   * Trained and evaluated multiple models:

     * **Random Forest (RF)**
     * **XGBoost**
     * **Deep Learning (Neural Network)**
   * Achieved a prediction accuracy of **\~78%**
   * Handled imbalanced class distribution using **SMOTE**
   * Applied **hyperparameter tuning** to boost model performance and avoid overfitting.

4. **Dashboard with Looker Studio**

   * Developed an interactive dashboard to visualize trends and monitor student performance
   * Designed for clarity and actionable insights for academic decision-makers
   * Dashboard available here: [Students' Performance Dashboard](https://lookerstudio.google.com/reporting/275ca653-22b8-4fde-a66d-e35619cd6f57)

## Key Results

* Identified key features influencing student status (e.g., GPA, tuition payment status)
* Built predictive models with reliable performance on balanced, optimized data
* Delivered a usable dashboard to help academic staff intervene early and track student trends

## Tools & Technologies

* **Python**: Pandas, Matplotlib, Seaborn, SciPy, Scikit-learn, XGBoost, TensorFlow/Keras, Imbalanced-learn (SMOTE)
* **Looker Studio**: Interactive dashboard for academic monitoring
* **Statistical Analysis**: Chi-Square Test, T-Test
* **Visualization**: Correlation Heatmap, Feature Importance Plots

## Future Improvements
* Improve model interpretability using **SHAP** or **LIME**
