# 🧠 Mental Health in Tech Industry Analysis

**Student:** Jay Jawalkar  
**Roll No:** DW241  
**Dataset:** Open Sourcing Mental Illness (OSMI) Tech Survey  
**Respondents:** 1,259  
**Features:** 27 attributes

---

## 📋 Project Overview

This project conducts a comprehensive analysis of mental health challenges in the technology industry using real-world survey data. The goal is to understand what demographic and workplace factors influence tech employees' willingness to seek mental health treatment, and to build a predictive model that can identify individuals who may need support.

Mental health remains a critical yet often overlooked aspect of employee wellbeing in tech, an industry known for high pressure, demanding work schedules, and a culture that sometimes stigmatizes vulnerability. This analysis addresses that gap by providing data-driven insights.

---

## 🎯 Research Objectives

The project investigates three primary research questions:

1. **What demographic and workplace factors correlate with seeking treatment?**
   - How do age, gender, and country of residence influence treatment-seeking behavior?
   - Which workplace characteristics (company size, remote work options, benefits) matter most?

2. **How do employer-provided resources affect mental health outcomes?**
   - Do companies offering mental health benefits and wellness programs see higher treatment rates?
   - How important is employer support and anonymity?

3. **Can we accurately predict treatment-seeking behavior?**
   - Build a machine learning model to classify individuals likely to seek help
   - Identify the most influential features driving predictions

---

## 📦 Dataset Description

### Source

The dataset comes from the **Open Sourcing Mental Illness (OSMI)** initiative, a nonprofit organization that regularly surveys tech workers about mental health in the industry.

### Data Characteristics

- **Rows:** 1,259 survey respondents
- **Columns:** 27 features including demographics, workplace factors, and treatment outcomes
- **Missing Values:** Significant missingness in certain columns handled through imputation and removal

### Key Variables

**Target Variable:**

- `treatment` — Whether the respondent sought mental health treatment (Yes/No)

**Demographic Features:**

- `Age` — Respondent's age (numeric)
- `Gender` — Self-identified gender (Male, Female, Other)
- `Country` — Country of residence
- `family_history` — History of mental health issues in family

**Workplace Features:**

- `tech_company` — Whether employed at a tech company
- `no_employees` — Company size categories
- `remote_work` — Whether remote work options are available
- `work_interfere` — How much mental health interferes with work (Never, Rarely, Sometimes, Often)
- `benefits` — Whether employer provides mental health benefits
- `care_options` — Whether employer provides care options
- `wellness_program` — Whether employer has a wellness program
- `leave` — How easy is it to take leave for mental health
- `seek_help` — Employer actively promotes mental health resources
- `anonymity` — Whether benefits are confidential
- `phys_health_consequence` — Negative consequences to physical health due to work
- `mental_health_consequence` — Negative consequences to mental health due to work

**Support & Communication:**

- `coworkers` — Willingness to discuss mental health with coworkers
- `supervisor` — Willingness to discuss mental health with supervisor
- `mental_health_interview` — Fear of being asked about mental health in interviews
- `phys_health_interview` — Fear of being asked about physical health in interviews
- `obs_consequence` — Observed negative consequences of mental health issues at workplace

---

## 🔧 Data Cleaning & Preprocessing

The analysis notebook (`mental_health.ipynb`) performs extensive data cleaning:

### 1. **Outlier Detection & Fixing**

- Age values outside the range 15-75 are treated as missing
- Outliers filled with median age (handles data entry errors)

### 2. **Gender Standardization**

- Raw gender responses contain variations ("M", "male", "Make", "msle", etc.)
- Standardized to three categories: Male, Female, Other
- Logic accounts for common typos and variations

### 3. **Missing Value Imputation**

- Categorical features filled with "Unknown"
- Numeric features imputed with median values
- Low-value columns (`Timestamp`, `comments`, `state`) removed entirely

### 4. **Deduplication**

- Duplicate rows removed to ensure data integrity

### 5. **Feature Engineering**

- Categorical variables encoded using `LabelEncoder` for model compatibility

---

## 📊 Exploratory Data Analysis (EDA)

The primary analysis notebook (`mental_health_analysis.ipynb`) includes comprehensive visualizations:

### Demographic Insights

- **Age Distribution:** Histogram showing respondents are predominantly young to mid-career professionals (mean age typically 30s)
- **Gender Breakdown:** Bar chart displaying male dominance in responses (common in tech surveys)
- **Country Distribution:** Geographic spread of respondents

### Univariate Analysis

- Box plots showing age spread and outliers
- Count plots for categorical distributions
- Descriptive statistics (mean, median, standard deviation, variance)

### Correlation Analysis

- Heatmaps showing relationships between numeric features
- Identification of strong predictors of treatment-seeking

### Workplace Factors Analysis

- How work interference levels affect treatment decisions
- Impact of employer benefits on treatment rates
- Remote work options vs. company size trends
- Correlation between supervisor relationships and treatment outcomes

### Treatment-Seeking Patterns

- Breakdowns by demographic groups
- Comparisons across countries
- Analysis of willingness to discuss mental health with peers vs. supervisors

---

## 🤖 Predictive Modeling

The project implements a **Logistic Regression** classifier to predict whether an employee will seek mental health treatment.

### Model Pipeline

1. **Feature Selection:** All features except the target (`treatment`) are used
2. **Data Splitting:** 80-20 train-test split
3. **Algorithm:** Logistic Regression (max_iter=1000)
4. **Evaluation:** Accuracy score on test set

### Model Rationale

- **Logistic Regression** chosen for interpretability — coefficients show feature importance
- Linear boundary suitable for this binary classification problem
- Fast training and efficient predictions

### Typical Results

- Models achieve **70-80% accuracy** depending on feature engineering
- Most predictive features: work interference, employer benefits, family history, age

---

## 💡 Key Insights & Findings

Based on the analysis, several patterns emerge:

1. **Work-Life Balance is Critical**
   - Employees experiencing high work interference are significantly more likely to seek treatment
   - Remote work options correlate with better mental health outcomes

2. **Employer Support Matters**
   - Companies offering mental health benefits and wellness programs see higher treatment rates
   - Employees who know how to seek help are more likely to do so
   - Manager support and open communication channels reduce stigma

3. **Demographic Patterns**
   - Younger employees slightly more likely to seek treatment
   - Geographic location influences cultural attitudes toward mental health
   - Family history is a strong predictor

4. **Stigma Remains a Barrier**
   - Many employees fear discussing mental health in interviews
   - Anonymity/confidentiality concerns prevent some from using available resources

5. **Gender & Diversity**
   - Male-dominated responses reflect tech industry demographics
   - Female and non-binary respondents show different patterns in treatment-seeking

---

## 📈 Recommendations

Based on findings, recommendations for tech companies include:

1. **Normalize Mental Health Conversations**
   - Implement mental health awareness campaigns
   - Leadership should model vulnerability and share experiences
   - Create safe spaces for peer discussion

2. **Expand Support Services**
   - Offer comprehensive mental health benefits
   - Provide multiple support channels (counseling, therapy, peer support)
   - Ensure accessibility and affordability

3. **Improve Work Culture**
   - Encourage reasonable work hours and time off
   - Promote remote work options where feasible
   - Implement clear leave policies for mental health days

4. **Transparency & Trust**
   - Ensure benefits are confidential and private
   - Clearly communicate available resources
   - Track and report on mental health initiatives

5. **Targeted Interventions**
   - Identify high-risk groups (high work interference, new hires)
   - Provide extra support during crunch periods
   - Mentor programs for younger employees

---

## 🛠️ Technology Stack

- **Python 3.x** — Core programming language
- **Pandas** — Data manipulation and cleaning
- **NumPy** — Numerical computations
- **Matplotlib** — Static visualizations
- **Seaborn** — Statistical data visualization
- **Scikit-learn** — Machine learning (LogisticRegression, preprocessing, train/test split)

---

## 📁 Project Structure

```
mental_health/
├── README.md                      # This file
├── mental_health.csv              # Raw survey data (1,259 rows × 27 columns)
├── mental_health.ipynb            # Initial exploratory analysis notebook
│                                  # (Data loading, cleaning, basic visualizations)
├── mental_health_analysis.ipynb   # Comprehensive analysis & modeling notebook
│                                  # (EDA, correlation analysis, predictive model)
└── .venv/                         # Python virtual environment
```

---

## 🚀 How to Use This Project

### 1. Set Up Environment

```bash
# Navigate to project directory
cd mental_health

# Activate virtual environment (Windows)
.venv\Scripts\Activate.ps1

# Or Linux/Mac
source .venv/bin/activate

# Install/verify dependencies
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### 2. Run the Analysis

```bash
# Start Jupyter
jupyter notebook

# Open and run notebooks in order:
# 1. mental_health.ipynb (data cleaning)
# 2. mental_health_analysis.ipynb (full analysis)
```

### 3. Interpret Results

- Check visualizations for patterns
- Review model coefficients for feature importance
- Reference insights section for key findings

---

## 📚 Learning Outcomes

This project demonstrates:

- **Data Cleaning:** Handling missing values, outliers, standardization
- **EDA:** Exploratory analysis using matplotlib and seaborn
- **Feature Engineering:** Categorical encoding and selection
- **Machine Learning:** Classification modeling with scikit-learn
- **Visualization:** Creating meaningful, styled charts to communicate insights
- **Statistical Analysis:** Correlation, distribution, and predictive relationships
- **Problem-Solving:** From raw data to actionable business insights

---

## 🔍 Limitations & Future Work

### Current Limitations

- **Sample Bias:** Survey respondents self-selected, may not represent all tech workers
- **Timestamp Data:** Survey conducted over time; temporal trends not analyzed
- **Missing Data:** Some respondents did not answer all questions
- **Geographic Bias:** OSMI surveys primarily reach English-speaking regions

### Future Enhancements

- **Time Series Analysis:** Track trends across survey years (2014-2019)
- **Advanced Modeling:** Random Forests, Gradient Boosting, Neural Networks
- **Feature Engineering:** Create interaction terms and domain-specific features
- **Stratified Analysis:** Separate models for different job roles or company sizes
- **Causal Inference:** Determine cause-and-effect relationships vs. correlations
- **Cost-Sensitive Learning:** Weight false negatives higher (missing at-risk individuals)

---

## 📝 Author Notes

This analysis was conducted as an academic project to understand mental health in tech. The insights derived are based on survey data and should not be interpreted as professional mental health advice. If you or someone you know needs mental health support, please reach out to:

- **OSMI** (Open Sourcing Mental Illness): osmihelp.org
- **NAMI** (National Alliance on Mental Illness): nami.org
- **SAMHSA** National Helpline: 1-800-662-4357 (free, confidential, 24/7)

---

**Last Updated:** April 2026  
**Status:** Complete ✅
