Cardiovascular Disease Prediction Using Machine Learning
Project Overview
This project aims to predict whether a given sample has cardiovascular disease (cardio) or not using machine learning techniques. The dataset contains health-related attributes such as age, gender, height, weight, blood pressure, cholesterol levels, and lifestyle factors (smoking, alcohol consumption, physical activity).

We implemented a complete machine learning pipeline, including data preprocessing, feature engineering, model training, evaluation, and visualization. Finally, we created a stacked ensemble model for robust predictions.

Steps in the Project
1. Data Preprocessing
Converted raw features into meaningful formats (e.g., age in days to years).

Handled categorical variables by mapping them to descriptive categories (e.g., cholesterol levels: Normal → 1).

Scaled numerical features using StandardScaler for algorithms sensitive to feature magnitudes.

Dropped redundant columns after feature engineering.

2. Feature Engineering
Created derived features such as:

BMI: Calculated from height and weight.

Age Categories: Grouped age into bins such as "30–49", "50–59", etc.

Blood Pressure Categories: Classified systolic and diastolic values into stages (e.g., Normal, Hypertension Stage 1).

Encoded categorical features into integers for machine learning models.

3. Exploratory Data Analysis (EDA)
Analyzed the distribution of features and their relationship with the target variable (cardio).

Visualized key insights using histograms, box plots, and correlation matrices.

4. Model Implementation
We implemented several machine learning algorithms to predict cardiovascular disease:

Logistic Regression

K-Nearest Neighbors (KNN)

Decision Tree

Support Vector Machine (SVM)

Random Forest

Gradient Boosting Algorithms:

LightGBM

XGBoost

Naive Bayes

5. Model Evaluation
Each algorithm was evaluated using metrics such as:

Accuracy

Precision

Recall

F1-score

The results were visualized using:

Bar charts for accuracy comparison.

Heatmaps for classification reports.

6. Ensemble Learning
After analyzing individual model performances:

We selected high-performing algorithms (LightGBM, XGBoost, Decision Tree, Logistic Regression, Random Forest) as base models.

Created a stacked ensemble pipeline with Logistic Regression as the meta-model.

The ensemble model achieved an accuracy of ~73%, with balanced precision and recall across classes.

7. Prediction Pipeline
We implemented a pipeline to preprocess new input samples and make predictions using the trained stacked ensemble model. The pipeline:

Processes raw input data into the required format.

Applies scaling using the pre-fitted scaler.

Uses base models to generate meta-features.

Makes final predictions using the meta-model.

How to Use the Project
1. Requirements
Install the following Python libraries:

bash
pip install pandas numpy scikit-learn lightgbm xgboost matplotlib seaborn joblib
2. Run the Project
Clone this repository:

bash
git clone <repository_url>
cd <repository_folder>
Preprocess the dataset and train the models by running:

bash
python train.py
Use the saved model (stacked_ensemble_model.pkl) to make predictions on new samples by running:

bash
python predict.py
3. Example Input
Provide input data in the following format:

text
age;gender;height;weight;ap_hi;ap_lo;cholesterol;gluc;smoke;alco;active
18393;2;168;62.0;110;80;1;1;0;0;1
4. Example Output
The output will indicate whether the sample has cardiovascular disease (cardio) or not:

text
Prediction: No Cardiovascular Disease (0)
Project Results
The stacked ensemble model achieved:

Accuracy: ~73%

Balanced precision and recall across classes.
The model is robust and suitable for real-world applications in predicting cardiovascular disease risk.

Potential Future Improvements
Hyperparameter tuning for base models and meta-model.

Incorporating additional features such as genetic data or family history of cardiovascular disease.

Exploring deep learning models for complex relationships in data.