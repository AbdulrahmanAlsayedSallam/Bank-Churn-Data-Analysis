# Bank Churners Data Analysis

This project analyzes customer churn in a bank dataset. The goal is to understand customer behavior, clean the dataset, and perform exploratory data analysis (EDA) to identify patterns and factors influencing customer attrition.

---

## 📂 Project Structure
- `bank_data_analysis.py` → Main analysis script  
- `BankChurners.csv` → Dataset   
- `README.md` → Project documentation  

---

## 🔍 1. Data Understanding
- **Loaded dataset** using Pandas (`pd.read_csv`).  
- **Checked dataset shape**: number of rows and columns.  
- **Inspected columns**:
  - `df.info()` → datatypes  
  - `df.describe()` → summary statistics  
  - Separated categorical vs numerical features  
- **Examples**:
  - Categorical: `Gender`, `Marital_Status`, `Income_Category`, `Education_Level`, etc.  
  - Numerical: `Customer_Age`, `Dependent_count`, `Months_on_book`, `Total_Trans_Ct`, `Avg_Utilization_Ratio`, etc.  

---

## 🧹 2. Data Cleaning
- **Missing values check** → no true `NaN` values.  
- **"Unknown" values** found in categorical columns:
  - Replaced with the **mode** of each column.  
- **Duplicates check** → none found.  
- **Range validation** → `Customer_Age` and `Avg_Utilization_Ratio` values within expected ranges.  

---

## 📊 3. Exploratory Data Analysis (EDA)

### Univariate Analysis
- **Histograms**:
  - Customer Age → most churners around ages 40–50.  
  - Months on Book → peak around 35 months.  
- **Bar Charts**:
  - Income Category → most customers earn `<$40K`.  
  - Marital Status → majority married.  
  - Dependent Count → most customers have 2–3 dependents.  
  - Card Category → majority hold **Blue** cards.  
- **Pie Charts**:
  - Gender → slightly more females.  
  - Churn Distribution → ~84% existing, ~16% attrited.  

### Bivariate Analysis
- **Churn by Gender** → nearly equal, attrition slightly higher among females.  
- **Churn by Education Level** → similar rates across categories.  
- **Transactions vs Churn** → fewer transactions = higher attrition.  
- **Churn by Age Group** → attrition rises with age (except drop at 60+).  
- **Inactivity vs Churn** → more inactive months = higher attrition.  
- **Dependents vs Churn** → minimal effect.  
- **Income vs Churn** → `<40K` and `120K+` have slightly higher attrition.  
- **Utilization Ratio vs Churn** → attrited customers show **much lower utilization**.  

---

## ✅ Key Insights
- **Low transaction activity** and **low utilization ratio** strongly correlate with churn.  
- **Demographics** (gender, dependents, marital status, education) have minimal effect.  
- **Older customers** are more likely to leave, except for the **60+ group** where attrition stabilizes.  

---

## 🚀 How to Run
1. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn
   ```
2. Place `BankChurners.csv` in the same directory.  
3. Run the script:
   ```bash
   python bank_data_analysis.py
   ```

---

## 📌 Next Steps
- Build predictive models (e.g., Logistic Regression, Random Forest, XGBoost) to **predict churn**.  
- Perform **feature importance analysis** to identify strongest churn drivers.  
- Explore **customer segmentation** for targeted retention strategies.  
