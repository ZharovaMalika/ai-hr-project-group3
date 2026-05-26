# ai-hr-project-group3
An AI-powered HR Intelligence System built with Python and Power BI to solve critical workforce challenges: automated candidate screening, ethical bias auditing, employee attrition prediction (SMOTE), K-Means performance clustering, and predictive workforce planning.

## 🏢 Project Overview & Business Case
Every year, corporate organizations face severe financial and operational losses due to subjective, biased, or reactive human resource decisions—such as hiring mismatches, undetected employee burnout, and unpredicted voluntary turnover. Replacing a mid-level professional costs an enterprise between 50% and 150% of their annual salary. 

This project delivers a comprehensive, production-grade AI-Powered HR Intelligence System designed to transform traditional HR workflows into data-driven, predictive operations. Utilizing the real-world HRDataset_v14 (consisting of 311 active and terminated employee profiles with 36 structural variables), our system successfully automates candidate screening, flags flight-risk personnel before resignation letters arrive, clusters workforce performance tiers, forecasts future headcount requirements, and systematically audits the underlying AI frameworks to ensure strict legal compliance and demographic fairness.

---

## 👥 Group Information
* Course: AI for HR Management (Final Exam Project)
* Specialty: AI in Business (School of Creative Industries)
* Group ID: ai-hr-project-group3
* Team Members:
  1. Tokanaeva Aisana (Student ID: `242676`) — Power BI Strategic Dashboard Architecture, DAX Measure Engineering & UI/UX Design.
  2. Zharova Malika (Student ID: `241767`) — Data Engineering, Core Machine Learning Pipeline (SMOTE, Class Weighting, Logistic Regression, KMeans) & Fairness Auditing.

---

## 📊 Dataset Description
* Project Dataset: Human Resources Data Set (HRDataset_v14)
* Source: [Kaggle Human Resources Data Set](https://www.kaggle.com/datasets/rhuebner/human-resources-data-set)
* Scope: 311 records capturing comprehensive historical metrics, including employee salary, position, state, age, gender, race, date of hire, date of termination, manager indicators, recruitment sources, performance scores, engagement survey indices, satisfaction levels, special project counts, and absenteeism data.

---

## 🛠️ Tools and Libraries Used
* Programming Language: Python 3 (Jupyter Notebook Ecosystem)
* Data Manipulation & Processing: pandas, numpy for data extraction, missing value median imputation, text standardization, and category casting.
* Data Visualization: matplotlib, seaborn for exploratory data analysis and bias distribution plotting.
* Machine Learning Frameworks: scikit-learn (Logistic Regression for binary classification, KMeans Clustering for talent segmentation, StandardScaler, and `train_test_split`).
* Imbalance Handling: imbalanced-learn (SMOTE - Synthetic Minority Over-sampling Technique to balance skewed attrition target labels).
* Business Intelligence Engine: Microsoft Power BI Desktop (utilizing complex DAX measures, scenario-planning parameters, and advanced analytical AI visual elements).

---

## 📁 Repository Folder Structure
The repository is professionally organized according to the mandatory academic evaluation criteria:
```text
ai-hr-project-group3/
├── data/
│   ├── HRDataset_v14.csv                    # Raw workforce dataset
│   └── clean_hr_dataset.csv                 # Preprocessed dataset with engineered features
├── notebook/
│   └── Final_AIforHRManagement (1).ipynb   # Executable production Jupyter Notebook with full ML pipeline
├── report/
│   └── HR_Intelligence_System_Report.pdf    # Comprehensive written business analysis report
├── dashboard/
│   ├── Page 1 — Executive Dashboard.jpg     # Executive HR Command Center Capture
│   ├── Page 2 — Recruitment Intelligence.jpg # Pipeline, skill match, and diversity metrics
│   ├── Page 3 — Attrition Risk Center.jpg    # Probability heatmaps & replacement cost calculator
│   ├── Page 4 — Performance Intelligence.jpg # K-Means talent clusters and training ROI map
│   ├── Page 5 — Engagement Monitor.jpg      # Wellbeing Index, manager satisfaction, and absences
│   ├── Page 6 — AI Insights Dashboard.jpg   # Workforce planning, forecasting, and scenario parameters
│   ├── Page 7 — Risk & Compliance.jpg       # Bias audit table, GDPR compliance scorecard, and risk register
│   └── Page 8 — Strategic Recommendations.jpg # 90-day implementation roadmap and cost-benefit analysis
└── presentation/
    └── Blue Minimalist Geometric Project Presentation.pdf # Oral defense slide deck (PDF format)
---

pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn
from imblearn.over_sampling import SMOTE
from sklearn.model_selection import train_test_split

X = df_clean.drop(columns=['Termd', 'EmploymentStatus', 'DateofTermination', 'TermReason'])
y = df_clean['Termd']

X_train, X_test, y_train, y_test = train_test_split(X, y, test_split=0.2, random_state=42, stratify=y)
smote = SMOTE(random_state=42)
X_train_bal, y_train_bal = smote.fit_resample(X_train, y_train)
