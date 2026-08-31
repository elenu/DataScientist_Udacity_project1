# Medical Genetics and Genomics Office Visit Costs Analysis

A comprehensive data science analysis of Medicare pricing patterns for medical genetics and genomics office visits across the United States, leveraging real CMS (Centers for Medicare & Medicaid Services) data.

**Read the full analysis on Medium:** [Medical Genetics and Genomics Office Visit Costs: What Your ZIP Code Really Tells Us](https://medium.com/@elenueyre/medical-genetics-and-genomics-office-visit-costs-what-your-zip-code-really-tells-us-c8c3b149c59f?sharedUserId=elenueyre)

---

## 📊 Project Overview

This project is part of the **Udacity Data Scientist Nanodegree** (Course 1, Project Lesson 6). The analysis answers critical questions about healthcare pricing using real-world Medicare data:

- **What are the actual costs patients face for genetic counseling?**
- **How does geographic location influence pricing?**
- **How predictable are healthcare costs using available data?**
- **What insights reveal the underlying structure of Medicare pricing?**

### Key Findings

✅ **Geographic variation is real** - Costs vary by up to 41% across the country  
✅ **The system is standardized** - Medicare enforces disciplined pricing structures  
✅ **Copays follow a formula** - Patient copays are ~25% of Medicare's allowed amount  
✅ **New patients pay more** - Established patients enjoy significantly lower costs  
✅ **Data dependencies matter** - Simple predictions can mask system structure rather than reveal insight  

---

## 📁 Repository Contents

```
.
├── README.md                                    # This file
├── Medical_Genetics_and_Genomics.csv           # Raw dataset (42,966 ZIP codes)
├── my_EDA_and_MLmodel.ipynb                    # Complete analysis notebook
├── Medium_Post_Draft.md                         # Blog post markdown
├── cost_intensity_map.png                       # State-level cost visualization
├── medicare_cms_logo.png                        # Healthcare branding header
└── .gitignore                                   # Git ignore file
```

---

## 🗂️ Dataset

**File:** `Medical_Genetics_and_Genomics.csv`

**Source:** [Centers for Medicare & Medicaid Services (CMS)](https://data.cms.gov/provider-data/dataset/b599-54c1#data-table)

**Dataset:** Medical Genetics and Genomics Office Visit Cost

**Records:** 42,966 ZIP codes across the United States

**Columns:**
- `zip_code` - ZIP code identifier
- `min_medicare_pricing_for_new_patient` - Minimum Medicare allowed amount (new patients)
- `max_medicare_pricing_for_new_patient` - Maximum Medicare allowed amount (new patients)
- `mode_medicare_pricing_for_new_patient` - Most frequent Medicare price (new patients)
- `min_copay_for_new_patient` - Minimum patient copay (new patients)
- `max_copay_for_new_patient` - Maximum patient copay (new patients)
- `mode_copay_for_new_patient` - Most frequent copay (new patients)
- `most_utilized_procedure_code_for_new_patient` - CPT code (new patients)
- `min_medicare_pricing_for_established_patient` - Minimum Medicare allowed amount (established)
- `max_medicare_pricing_for_established_patient` - Maximum Medicare allowed amount (established)
- `mode_medicare_pricing_for_established_patient` - Most frequent Medicare price (established)
- `min_copay_for_established_patient` - Minimum patient copay (established)
- `max_copay_for_established_patient` - Maximum patient copay (established)
- `mode_copay_for_established_patient` - Most frequent copay (established)
- `most_utilized_procedure_code_for_established_patient` - CPT code (established)

**Data Quality:** No missing values | Well-structured | Ready for analysis

---

## 📓 Analysis Notebook

**File:** `my_EDA_and_MLmodel.ipynb`

### Sections

1. **Data Context & Overview**
   - Dataset description and CMS background
   - Data types and structure exploration

2. **Exploratory Data Analysis (EDA)**
   - Descriptive statistics
   - Distribution analysis (histograms)
   - Correlation analysis with heatmaps
   - Scatter plots and feature relationships
   - Principal Component Analysis (PCA)

3. **Machine Learning Modeling**
   - Linear Regression baseline model
   - Polynomial Regression (degree 2)
   - Model evaluation using RMSE

4. **Predictive Scenarios**
   - Predicting minimum Medicare costs
   - Analysis of data leakage and model redundancy

5. **Geographic Visualization**
   - State-level cost intensity aggregation
   - Interactive and static visualizations

### Key Techniques

- **Data Cleaning:** Handling categorical/numerical data, feature engineering
- **EDA:** Descriptive statistics, correlation analysis, visualization
- **Modeling:** Linear & polynomial regression with scikit-learn
- **Evaluation:** RMSE, correlation analysis
- **Visualization:** Matplotlib, seaborn, plotly

---

## 🚀 Getting Started

### Requirements

- Python 3.9+
- Jupyter Notebook
- pandas
- numpy
- matplotlib
- scikit-learn
- seaborn
- plotly

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/elenu/medical-genetics-cost-analysis.git
   cd medical-genetics-cost-analysis
   ```

2. **Create a virtual environment:**
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # On Windows: .venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook my_EDA_and_MLmodel.ipynb
   ```

---

## 📈 Key Insights from Analysis

### 1. Cost Structure is Standardized
Medicare enforces a rigid fee schedule. Pricing isn't independently determined by providers but follows federal guidelines. This explains the near-perfect correlations between pricing metrics.

### 2. Geographic Variation Has Limits
While costs do vary by location (up to 41% difference), ZIP code alone cannot predict costs effectively. RMSE of ~$26,437 shows the weakness of using location alone as a predictor.

### 3. New Patients Pay Premium Prices
New patients face 3-7x higher minimum costs than established patients for the same service. This pricing structure incentivizes continuity of care.

### 4. Data Redundancy vs. Real Insight
When all pricing variables are mathematically derived from the same source (copay = medicare price ÷ 4), achieving "perfect" model performance is hollow—it's just algebra, not true predictive insight.

### 5. True Prediction Requires Independent Factors
To genuinely predict healthcare costs, you need factors beyond pricing tiers:
- Patient diagnosis complexity
- Provider efficiency metrics
- Regional demand for services
- Insurance negotiation leverage

---

## 📊 Visualizations

### cost_intensity_map.png
State-level cost analysis showing highest and lowest cost states, with key statistics.

### medicare_cms_logo.png
Professional header graphic featuring Medicare branding, CMS data reference, and healthcare financial symbols.

---

## 🔍 Methodology (CRISP-DM Process)

1. **Business Understanding** - What drives medical genetics office visit costs?
2. **Data Understanding** - Explore CMS Medicare pricing dataset
3. **Data Preparation** - Clean, aggregate by state, handle categorical variables
4. **Modeling** - Linear and polynomial regression
5. **Evaluation** - RMSE analysis, correlation insights
6. **Deployment** - Medium blog post + GitHub repository

---

## 📖 Read the Full Analysis

For detailed findings, interpretations, and non-technical summaries of this analysis, read the complete blog post:

**[Medical Genetics and Genomics Office Visit Costs: What Your ZIP Code Really Tells Us](https://medium.com/@elenueyre/medical-genetics-and-genomics-office-visit-costs-what-your-zip-code-really-tells-us-c8c3b149c59f?sharedUserId=elenueyre)** on Medium

---

## 💡 For Readers

- **Patients:** Understand cost variation and why continuity of care matters
- **Healthcare Providers:** Learn about Medicare's standardized pricing structure
- **Data Scientists:** See how data quality and structure influence model performance
- **Researchers:** Explore directions for deeper healthcare cost analysis

---

## 📚 Data Sources

- **Primary:** [CMS Provider Data - Medical Genetics & Genomics Office Visit Cost](https://data.cms.gov/provider-data/dataset/b599-54c1#data-table)
- **Documentation:** [CMS Medicare Physician Fee Schedule](https://www.cms.gov/medicare/physician-fee-schedule/search)
- **CPT Codes Reference:** [Medical Code Definitions](https://www.optimantra.com/medical-code-definitions/)

---

## 🛠️ Project Context

**Program:** Udacity Data Scientist Nanodegree  
**Course:** Course 1 - Introduction to Data Science  
**Project:** Lesson 6 - Write a Data Science Blog Post  
**Completion Date:** August 2024

**Project Requirements Met:**
- ✅ 3-5 business questions answered with data
- ✅ Proper CRISP-DM process followed
- ✅ Categorical and missing values handled appropriately
- ✅ Readable, well-documented code (PEP8 compliant)
- ✅ Jupyter notebook executable and correct
- ✅ Analysis published as blog post
- ✅ GitHub repository with complete materials

---

## 📝 License

This project is provided for educational purposes as part of the Udacity Data Scientist Nanodegree.

---

## 👤 Author

**Elena Eyre**  
Data Science Student | Healthcare Data Analysis  
Medium: [@elenueyre](https://medium.com/@elenueyre)  
GitHub: [elenu](https://github.com/elenu)

---

## 🤝 Contributing

This is an educational project. For questions, suggestions, or discussions about the analysis, feel free to reach out or open an issue.

---

## ❓ Questions?

- **About the analysis:** Read the [Medium post](https://medium.com/@elenueyre/medical-genetics-and-genomics-office-visit-costs-what-your-zip-code-really-tells-us-c8c3b149c59f?sharedUserId=elenueyre)
- **About the dataset:** Visit [CMS Data Portal](https://data.cms.gov/)
- **About the code:** Check the Jupyter notebook comments
- **About CMS:** See [Centers for Medicare & Medicaid Services](https://www.cms.gov/)

---

**Last Updated:** August 31, 2024
