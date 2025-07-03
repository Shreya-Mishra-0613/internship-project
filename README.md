# 📊 HR Analytics: Predict Employee Attrition

## 📌 Objective
Use predictive analytics to identify key drivers of employee attrition and develop actionable prevention strategies for HR departments.

---

## 🛠️ Tools & Technologies
- **Python**: pandas, numpy, matplotlib, seaborn, scikit-learn, SHAP
- **Power BI**: Visual exploration & dashboards
- **Jupyter Notebook**: EDA, preprocessing, modeling
- **PDF/Excel**: Reporting & final deliverables

---

## 🔄 Workflow

### 1. Exploratory Data Analysis (EDA)
- Conducted detailed univariate and bivariate analysis
- Visualized class imbalance in `Attrition` using bar charts
- Explored key variables such as:
  - `OverTime`, `MonthlyIncome`, `YearsSinceLastPromotion`, `JobRole`, `MaritalStatus`, etc.
- Identified trends using:
  - Count plots, box plots, line charts, and stacked bar graphs
- Detected outliers and missing values to guide preprocessing
- Used Power BI to build interactive dashboards for deeper insights

### 2. Data Preprocessing
- Handled missing values and inconsistent formats
- Created meaningful categorical bands (e.g., AgeBand, CompanyAgeBand)
- Split data for two models (Logistic Regression, Decision Tree) with tailored encoding:
  - **Logistic Regression**: One-hot for nominal, ordinal for ordered features
  - **Decision Tree**: Ordinal encoding for all categoricals

### 3. Feature Engineering
- Binned continuous features like `YearsSinceLastPromotion` for better interpretability
- Encoded target variable `Attrition` (Yes → 1, No → 0)

### 4. Model Building
- **Logistic Regression** (baseline, interpretable)
- **Decision Tree Classifier** (handles non-linear patterns)
- Both models wrapped in preprocessing pipelines using `ColumnTransformer`

### 5. Evaluation
| Metric        | Logistic Regression | Decision Tree |
|---------------|---------------------|----------------|
| Accuracy      | 87.76%              | 82.31%         |
| Precision     | 84.62%              | 62.96%         |
| Recall        | 24.44%              | 28.81%         |
| F1 Score      | 37.93%              | 39.53%         |

- Confusion matrices and classification reports included in `/outputs`.

### 6. Explainability: SHAP Values
- Used SHAP to explain model predictions and top attrition drivers
- Key features:
  - **OverTime**, **YearsSinceLastPromotion**, **MonthlyIncome**, **TrainingTimesLastYear**
- Insights used to generate data-backed HR policy suggestions

---

## 📈 SHAP Highlights

| Feature                 | Insight                                                            |
|-------------------------|--------------------------------------------------------------------|
| OverTime                | Strongest positive driver of attrition                            |
| YearsSinceLastPromotion | Long gaps lead to increased attrition                             |
| MonthlyIncome           | Lower salaries drive higher resignation                           |
| TrainingTimesLastYear   | Less training = higher attrition risk                             |
| MaritalStatus_Single    | Singles more likely to leave                                      |
| TotalWorkingYears       | Experienced employees are more stable                             |

Visualizations located in `images/`.

---

## 📄 Deliverables

- ✅ Power BI dashboard with interactive filters and department-wise attrition
- ✅ `model_accuracy_report.pdf`: Confusion matrices + model comparison
- ✅ `Attrition_Prevention_Suggestions.pdf`: SHAP-based HR policy report
- ✅ Jupyter Notebooks of EDA and Model Fitting & Evaluation

---

## 🧠 Conclusion

Both models consistently identified OverTime, lack of promotion, and compensation as key attrition drivers. The analysis supports proactive HR measures like performance tracking, fair workload distribution, and personalized retention strategies. 
