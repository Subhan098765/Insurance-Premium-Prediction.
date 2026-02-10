# Medical Insurance Cost Prediction 🏥📊

This project implements a **Linear Regression** model to predict personal medical insurance costs based on the `insurance.csv` dataset. The goal is to identify how variables like age, BMI, and lifestyle choices impact healthcare charges.

## 🚀 Model Performance
- **Adjusted R² Score:** 79%  
- **Method:** Linear Regression (Scikit-Learn)

## 🔍 Project Workflow
1. **Exploratory Data Analysis (EDA):** Visualizing data distributions for age, BMI, and insurance charges using `Seaborn` and `Matplotlib`.
2. **Data Preprocessing:** Handling categorical variables (sex, smoker, region) and checking for missing values.
3. **Correlation Analysis:** Investigating relationships between features and the target variable (`charges`).
4. **Model Building:** Training a Linear Regression model using a train-test split.
5. **Evaluation:** Assessing performance using the Adjusted R² metric.

## 🛠️ Tech Stack
- **Language:** Python
- **Libraries:** Pandas, NumPy, Scikit-Learn, Matplotlib, Seaborn

## 📂 Dataset
The dataset contains 1,338 observations with the following features:
- `age`: Age of primary beneficiary
- `sex`: Insurance contractor gender
- `bmi`: Body mass index
- `children`: Number of children covered by health insurance
- `smoker`: Smoking status
- `region`: Beneficiary's residential area in the US
- `charges`: Individual medical costs billed by health insurance (TargetS)