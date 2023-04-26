# Churn Prediction

This repository contains code and analysis for churn prediction using usage data from an Indian telecom firm. The goal is to identify characteristics of customers likely to churn, which can then be used to formulate effective retention strategies to reduce churn and improve overall retention rates.


## Steps Followed

The churn prediction process involved the following steps:
1. Exploratory Data Analysis (EDA): In this phase, each variable in the dataset was thoroughly investigated. Missing values were imputed using the median or removed entirely. During this exploratory phase, several preliminary insights were gained, such as the primary use of the service by most users (social media).
2. Feature Engineering: Feature engineering was performed to create new variables that could potentially improve the prediction accuracy. Specific features that relate to growth in recharges/refills from the observation phase (months of June and July) to the action phase (month of August). Some variables were also created by bucketing other variables ('aon') where appropriate.
3. Modeling: To build the churn prediction model, several steps were taken. First, class rebalancing was performed to increase the number of churn records and facilitate better learning. Next, we built two separate models: logistic regression and decision tree. For logistic regression, recursive feature elimination was performed to identify the most important variables. Variables with a Variance Inflation Factor (VIF) greater than 5 were eliminated. For decision trees, no significant treatment was done apart from scaling and outlier treatment.
4. Model Evaluation: Model evaluation was conducted using various metrics. A confusion matrix was used to assess accuracy, but due to the class imbalance, additional analysis was performed using the Receiver Operating Characteristic (ROC) curve and Area Under the Curve (AUC). The best cutoff point was determined by examining sensitivity, specificity, and accuracy across different cutoff points, selecting the point where all metrics were sufficiently high.


## Results/Insights:

- Decision tree was a better fit for the data, based on the ROC curve and other metrics (accuracy, sensitivity, specificity).
- Higher the refill made during the action phase, the less likely the customer is to churn. Thus, continued and consistent prepaid recharges/refills are a good predictor of likelihood to churn of the customer, and actions must be taken to encourage consistent refills - discounts, loyalty programs, etc
- As number of outgoing calls have increased from the observation to action phase, the likelihood of the customer churning also increases. This could potentially point to pricing problems (competitors offering better rates for the increased volume of calls) or network quality problems (call qualities worsening with increasing calls) causing customers to switch to other networks. 


