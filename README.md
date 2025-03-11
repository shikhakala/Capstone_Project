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

#### **Key Findings & Observations**

1.  **General Observations**
-   The dataset contains 23,436 records with 37 columns (19 numeric, 18 categorical).
-   After data cleaning, 23,188 records remained with 33 columns.
-   Major issues like missing values, duplicate records, and extreme outliers were handled before analysis.
2.  **Attrition Insights**
-   The dataset exhibits a class imbalance, with significantly more current employees than those who resigned.
-   Employees who resigned were generally younger, lower in job level, and had lower income.
-   Compensation-related variables, such as MonthlyIncome, JobLevel, and TotalWorkingYears, showed a weak but noticeable correlation with attrition.
-   Attrition was higher among employees who frequently changed jobs in the past.
3.  **Salary & Job Level Impact**
-   Higher-income employees were more likely to stay.
-   Job Level and Monthly Income were highly correlated (\~0.94), meaning that higher job levels translate into higher income and possibly better job stability.
-   Employees at lower job levels left more frequently, likely for better opportunities.
4.  **Work-Life Balance & Job Satisfaction**
-   Work-life balance had little impact on attrition, suggesting employees left for better compensation or career growth rather than dissatisfaction with work-life balance.
-   Job satisfaction was not a strong predictor of attrition, indicating other factors like salary, promotions, and career growth were more influential.
5.  **Impact of Promotions & Career Growth**
-   Employees stuck in the same role for too long were more likely to leave.
-   Years Since Last Promotion had no strong correlation with attrition, meaning employees left for better opportunities rather than waiting for a promotion.
-   Employees with more experience (Total Working Years) were less likely to leave.
6.  **Managerial Influence**
-   Short tenure under a manager was correlated with higher attrition, suggesting that poor managerial relationships or lack of mentorship could drive employees away.
-   Employees who stayed with the same manager for a long time were more likely to remain with the company.
7.  **Other Notable Findings**
-   Longer commutes (DistanceFromHome) showed weak correlation (-0.07) with attrition, indicating it might not be a major factor.
-   Overtime work was linked to higher attrition, possibly due to burnout.
-   Employees hired via referrals had the lowest attrition rates, meaning referral programs could be a strong retention strategy.
-   Frequent travelers had higher attrition, possibly due to work-related stress and dissatisfaction.
-   Sales Executives and Laboratory Technicians had the highest attrition, indicating a need for targeted retention efforts in these roles.

#### **Next steps**

What suggestions do you have for next steps?

**Recommendations**

1.  **Compensation Adjustments**
    -   Improve salaries for lower-level employees to reduce voluntary resignations.
    -   Consider performance-based raises or bonuses to retain high performers.
2.  **Career Growth & Development**
    -   Provide clear career progression paths to encourage long-term employee retention.
    -   Invest in training programs that align with career growth.
3.  **Retention-Focused Hiring**
    -   Strengthen employee referral programs, as referrals have lower attrition rates.
    -   Evaluate hiring sources and prioritize platforms that bring long-term employees.
4.  **Workload & Managerial Improvements**
    -   Optimize workload and reduce excessive overtime to minimize burnout.
    -   Provide leadership training for managers to improve employee-manager relationships.
5.  **Flexible Work Arrangements**
    -   Explore hybrid or remote work options for employees with long commutes.
    -   Review travel policies for frequent travelers to reduce stress-related turnover.

#### **Outline of project**

-   [Link to notebook 1]()
-   [Link to notebook 2]()
-   [Link to notebook 3]()

##### **Contact and Further Information**
