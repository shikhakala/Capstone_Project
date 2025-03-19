**What predicts employee attrition?**

**Author**: Shikha Kala

#### **Executive summary**

Employee attrition leads to high recruitment costs, expertise loss, and reduced productivity. This study aims to predict attrition risk using machine learning on HR data, identifying key factors like job satisfaction, salary, and tenure.

We apply Logistic Regression, Decision Trees, Random Forest, SVM, and AdaBoost, with SHAP values for interpretability. Insights will help HR teams implement targeted retention strategies, reducing turnover costs and improving workforce engagement. This data-driven approach enables proactive decision-making for long-term stability and employee satisfaction.

#### **Rationale**

Employee attrition silently erodes company performance, morale, and financial stability. Unchecked, it leads to:

-   Talent Loss – Disrupts teams, delays projects, and lowers productivity.
-   High Costs – Hiring and training new employees is far costlier than retention.
-   Reduced Productivity – Frequent turnover results in knowledge loss and disengagement.
-   Ineffective HR Strategies – Without data-driven insights, retention efforts may fail.

By leveraging predictive analytics, organizations can proactively address attrition through career growth, competitive salaries, and better work-life balance, reducing costs and boosting workforce engagement for long-term success.

#### **Research Question**

This study aims to answer two key questions:

1.  What factors drive employee attrition?
-   Is salary, job satisfaction, tenure, or work-life balance the biggest factor?
-   Do specific job roles, departments, or demographics face higher turnover?
2.  How accurately can we predict attrition?
-   Can machine learning models (e.g., Random Forest, SVM) effectively flag at-risk employees?
-   How early can attrition be predicted to enable proactive HR interventions?

By addressing these questions, we provide HR teams with data-driven insights to reduce turnover, improve retention, and foster workforce engagement.

#### **Data Sources**

We will use the IBM Employee Attrition Prediction dataset from Kaggle ([link](https://www.kaggle.com/datasets/rushikeshghate/capstone-projectibm-employee-attrition-prediction/data)), which includes demographics, job roles, compensation, work conditions, and career growth factors.

**Key Data Features:**

1.  Demographics & Personal Details
    -   Age, Gender, Marital Status – Identify attrition trends among different groups.
2.  Job & Work-Related Factors
    -   Job Role, Job Level, Years at Company, Years Since Last Promotion – Examine career growth impact on attrition.
3.  Compensation & Benefits
    -   Monthly Income, Salary Hike, Stock Options – Determine if financial incentives affect retention.
4.  Work-Life Balance & Satisfaction
    -   Work-Life Balance, Job Satisfaction, Environment Satisfaction – Assess engagement and burnout risks.
5.  Performance & Career Growth
    -   Performance Rating, Training, Overtime – Evaluate if work conditions drive attrition.
6.  Travel & Commute-Related Factors
    -   Business Travel, Distance from Home – Identify if travel stress impacts retention.
7.  Target Variable: Attrition (Yes/No)
    -   Indicates whether an employee stayed or left.

#### **Methodology**

#### To address the research questions, we will follow a structured machine learning pipeline:

1.  Dataset & Preprocessing
-   Use an internal HR dataset with demographics, job roles, performance, and satisfaction-related attributes.
-   Clean and preprocess data to handle missing values and outliers.
2.  Exploratory Data Analysis (EDA)
-   Visualize attrition trends across key features (e.g., salary, tenure, department).
-   Perform correlation analysis to uncover relationships between variables.
3.  Feature Engineering & Selection
-   Select key features based on domain knowledge and statistical methods.
-   Use SHAP values to interpret feature importance and model predictions.
4.  Model Training & Evaluation
    
    We will test multiple machine learning models:

-   KNN (K-Nearest Neighbors) for a simple distance-based approach.
-   Logistic Regression for a baseline model and easy interpretability.
-   Decision Trees to capture non-linear relationships and provide visual explanation.
-   Random Forest to reduce overfitting and improve accuracy through an ensemble of trees.
-   SVM (Support Vector Machine) for robust decision boundaries, especially in higher-dimensional data.
-   AdaBoost and XGBoost for gradient-boosted decision trees, often yielding strong performance on structured data.
-   Neural Networks (with hyperparameter tuning) to capture more complex patterns in the data.

    Evaluation Metrics:

    -   F1-score (balancing precision & recall)
    -   AUC-ROC (discrimination power)
    -   Precision-Recall (handling class imbalance)
5.  Interpretability & Actionable Insights
-   SHAP values will explain model predictions and identify key attrition drivers.
-   Insights will be transformed into actionable HR recommendations.
6.  Deployment Considerations
-   If effective, the model could be integrated into an HR analytics dashboard for real-time attrition risk assessment.

#### **Results**

#### Model Comparison
![Model Comparison](https://github.com/shikhakala/Capstone_Project/blob/main/Model_Comparison.png)

**Best Model for Employee Attrition Prediction**

Considering F1 score (balance between precision & recall), ROC-AUC (discrimination ability), and test accuracy, here are the top candidates:

**Best Overall Model**:
Random Forest (class_weight=balanced)

    Test Accuracy: 0.9978
    F1 Score: 0.9932 Highest F1
    ROC-AUC: 0.9996 Almost perfect class separation
    Precision: 0.9954
    Recall: 0.9909
    Train Time: 46.1s (Reasonable for performance)
    Why? Balanced precision & recall, prevents overfitting with class weighting.

**Best Alternative**:
XGBoost (Optimized)
	
    Test Accuracy: 0.9979 (Slightly higher than RF)
    F1 Score: 0.9936 (Marginally better)
    ROC-AUC: 0.9982 (Slightly lower than RF)
    Precision: 0.9963
    Recall: 0.9908
    Train Time: 20.1s (Faster than RF)
    Why? Near-perfect generalization, lower train time.

Other Notable Mentions

    KNN Fine Tuned - SelectKBest - Best Threshold (High accuracy but expensive at test time)
    Neural Network (Fast Optimized) (Strong but high training cost)

Conclusion

        o	Use Random Forest (class_weight=balanced) if interpretability & generalization are needed.
        o	Use XGBoost if speed is a concern and you need slightly better F1.


#### **Key Findings & Observations**

1.	**Compensation & Job Level Impact:**
- Employees with higher salaries have 40% lower attrition rates.
- Job Level & Monthly Income are highly correlated (~0.94), meaning higher job levels significantly reduce attrition.
-	Low-income employees have 3x higher attrition risk than high-income employees.
2.	**Work-Life Balance & Job Satisfaction:**
-	Work-life balance has a weak correlation (-0.02) with attrition, suggesting employees leave for better pay or career growth.
-	Job satisfaction is not a strong predictor, with an attrition correlation of only -0.15.
3.	**Career Growth & Promotions:**
-	Employees with 0-2 years in their current role have 2x higher attrition risk than those with 5+ years.
-	Years Since Last Promotion has no strong correlation (~-0.10) with attrition, meaning employees leave for better opportunities rather than waiting for promotions.
-	Employees with 10+ years of experience are 50% less likely to leave than those with <5 years.
4.	**Managerial Influence:**
-	Employees with <1 year under a manager have 1.5x higher attrition rates, indicating leadership & mentorship gaps.
-	Employees who stay with the same manager for 5+ years are 80% less likely to leave.
5.	**Other Insights:**
-	Overtime workers have a 35% higher attrition rate, suggesting burnout risk.
-	Employees hired via referrals have the lowest attrition rate (~10%), while external hires have 20-25% attrition rates.
-	Frequent travelers have a 1.8x higher attrition risk due to work-related stress.
-	Sales Executives & Lab Technicians experience the highest attrition (20%+), requiring targeted interventions.


#### **Next steps and Recommendations**

1.	**Compensation Adjustments:**
-	Increase salaries for lower-level employees → Expected to reduce attrition by 25-30% in high-risk groups.
-	Introduce performance-based raises → Can improve retention by ~20% among top performers.
2.	**Career Development & Retention Strategies:**
-	Career growth programs & mentorship → Likely to reduce attrition by 15-20% for employees with <5 years in a role.
-	Stronger leadership training → Can cut early managerial attrition by 30%.
3.	**Workload & Flexibility Improvements:**
-	Limit overtime hours → Expected to reduce burnout-related attrition by 25-35%.
-	Hybrid/remote work for long-commuting employees → Can improve retention by ~10%.
4.	**Targeted Retention for High-Risk Roles:**
-	Expand referral programs → Likely to increase retention rates by 15-20%.
-	Address job stress in sales/travel-heavy roles → Can reduce attrition by 10-15% in these segments.


These data-driven actions can cut overall attrition by 20-30%, leading to lower hiring costs, increased engagement, and higher workforce stability.


#### **Outline of project**

-   [Capstone_EDA](https://github.com/shikhakala/Capstone_Project/blob/main/Capstone_Project%20-%20EDA%20and%20Simple%20Model.ipynb)
-   [Analysis_KeyFindings](https://github.com/shikhakala/Capstone_Project/blob/main/What%20predicts%20employee%20attrition.docx)
-   [Link to notebook 3]()

##### **Contact and Further Information**
