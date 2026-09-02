# Medical Insurance Cost Prediction — Statistical Modeling & Linear Regression

[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E?style=flat&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Scipy](https://img.shields.io/badge/SciPy-Statistical%20Testing-8CAAE6?style=flat&logo=scipy&logoColor=white)](https://scipy.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=flat&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A statistical and Machine Learning regression analysis project modeling healthcare insurance premiums based on individual demographic, lifestyle, and health indicators, achieving an **Adjusted $R^2$ of 79%**.

---

## 📌 Project Overview

Healthcare premium pricing requires actuarial precision to estimate individual risk. This project performs an in-depth statistical investigation into 1,338 patient records (`insurance.csv`), executing hypothesis testing, feature transformation, and ordinary least squares multiple regression.

### 💡 Core Methodological Highlights
1. **Exploratory Data Analysis (EDA)**: Analyzes univariate and multivariate distributions of demographic and physical indicators (`age`, `bmi`, `children`, `sex`, `smoker`, `region`, `charges`).
2. **Clinical Feature Engineering**: Discretizes continuous BMI into 4 clinical categories (**Underweight**, **Normal**, **Overweight**, **Obese**) using World Health Organization (WHO) clinical thresholds.
3. **Statistical Hypothesis Testing**:
   - **Pearson Correlation**: Evaluates linear relationships between continuous attributes and target premiums.
   - **Chi-Square ($\chi^2$) Contingency Analysis**: Tests independence between categorical attributes and discretized target premium quartiles ($p < 0.05$).
4. **Multiple Linear Regression Modeling**: Fits an optimal feature subset to explain 79% of variance in insurance charges.

---

## ⚙️ Preprocessing & Statistical Pipeline

```
Raw Patient Records (insurance.csv)
  ├── 1. Data Cleaning (Duplicate removal & type casting)
  ├── 2. Categorical Encoding (Binary mapping: is_female, is_smoker; One-Hot: region)
  ├── 3. Clinical BMI Binning (Underweight, Normal, Overweight, Obese)
  ├── 4. Standardization (StandardScaler on continuous age, bmi, children)
  ├── 5. Hypothesis Testing (Chi-Square & Pearson correlation feature filtration)
  └── 6. Multiple Linear Regression (80/20 Stratified Split -> OLS Fit)
                                 │
                                 v
                Adjusted R² Score = 0.79 (79% Explained Variance)
```

---

## 📋 Feature Breakdown & Statistical Filtration

| Feature | Description | Encoding / Transformation | Statistical Significance ($\chi^2$ / Pearson) |
| :--- | :--- | :--- | :--- |
| **`age`** | Age of primary beneficiary | Standard Scaled | Highly Significant ($p < 0.001$) |
| **`bmi`** | Body mass index ($kg/m^2$) | Continuous Standard Scaled | Significant ($p < 0.001$) |
| **`is_smoker`** | Smoking status | Binary ($1 = \text{Yes}, 0 = \text{No}$) | Highest Single Predictor of Premium |
| **`children`** | Number of covered dependents | Integer Standard Scaled | Significant ($p < 0.05$) |
| **`bmi_category_Obese`** | Clinical obesity indicator | One-Hot Binary Flag | Crucial interaction with smoking status |
| **`region_southeast`** | Geographic region | One-Hot Binary Flag | Region with highest localized risk |

---

## 📊 Model Evaluation & Metrics

$$\text{Adjusted } R^2 = 1 - \left[ \frac{(1 - R^2)(n - 1)}{n - p - 1} \right] \approx 0.79$$

- **$R^2$ Score:** $\approx 0.793$
- **Adjusted $R^2$ Score:** $\approx 0.789$
- **Key Finding:** Smoking status combined with obesity (`bmi_category_Obese`) forms the dominant driver of catastrophic healthcare expenditure.

---

## 🚀 Quickstart & Execution

### 1. Environment Setup
```bash
# Clone the repository
git clone https://github.com/Subhan098765/Insurance-Premium-Prediction..git
cd Insurance-Premium-Prediction.

# Create and activate virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: .\venv\Scripts\activate

# Install dependencies
pip install scikit-learn scipy pandas numpy matplotlib seaborn jupyter
```

### 2. Run Analysis Notebook
```bash
jupyter notebook INS.ipynb
```

---

## 📂 Project Structure

```text
Insurance-Premium-Prediction./
├── INS.ipynb                       # Jupyter notebook containing statistical tests, EDA & regression modeling
├── insurance.csv                   # Healthcare insurance dataset
├── README.txt                      # Original summary notes
└── README.md                       # Complete statistical analysis report & technical documentation
```

---

## 👨‍💻 Author
Developed by **Muhammad Subhan Ali** ([@Subhan098765](https://github.com/Subhan098765)).
