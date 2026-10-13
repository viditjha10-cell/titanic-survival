# Titanic Survival Prediction & Exploratory Data Analysis (EDA)

This project features a comprehensive Exploratory Data Analysis (EDA), data cleaning, and feature engineering workflow on the classic Kaggle [Titanic Dataset](https://www.kaggle.com/c/titanic). The primary goal is to uncover key demographic and socio-economic factors that influenced passenger survival rates aboard the RMS Titanic.

---

##  Project Overview

- **Dataset Source:** `Titanic-Dataset.csv` (891 passenger records, 12 initial features)
- **Overall Survival Rate:** ~38.38%
- **Key Focus Areas:** 
  - Missing value imputation strategies
  - Feature engineering (extracting titles, family sizes, deck levels, and binning continuous variables)
  - Multivariate survival analysis (class, gender, and family dynamics)

---

##  Data Preprocessing & Feature Engineering

1. **Missing Value Treatment:**
   - **`Embarked`**: Imputed missing values using the mode (`S`).
   - **`Age`**: Imputed using the median age grouped by passenger class (`Pclass`) and `Sex`.
   - **`Cabin`**: Extracted high-level features since over 75% of values were missing:
     - `Has_Cabin`: Binary flag indicating cabin availability.
     - `Deck`: Extracted the deck level from the cabin string.

2. **New Features Created:**
   - **`FamilySize`**: Combined `SibSp` (siblings/spouses) and `Parch` (parents/children) plus the individual (`+ 1`).
   - **`IsAlone`**: Binary flag to categorize solo travelers versus those with family.
   - **`Title`**: Extracted professional and social titles from passenger names and grouped rare titles.
   - **`AgeGroup` & `FareBin`**: Categorized continuous age and fare variables into discrete segments.

---

##  Key Insights & Findings

- **Gender Disparity:** Females had a significantly higher survival rate (**~74.2%**) compared to males (**~18.9%**).
- **Passenger Class Impact:** First-class passengers experienced a **~63%** survival rate, dropping down to **~24.2%** for third-class passengers.
- **Class & Gender Interaction:** First-class females had the highest survival rate at **96.8%**, whereas third-class males faced the lowest at **13.5%**.
- **Family Dynamics:** Passengers traveling with small-to-moderate family sizes (2–4 members) achieved higher survival odds than solo travelers or large families (5+ members).

---


Make sure you have Python installed along with the core data science libraries:
```bash
pip install pandas numpy matplotlib seaborn
