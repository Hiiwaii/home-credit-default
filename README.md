Home Credit Default Risk Prediction

Project Summary and Objective

Business Problem
Many individuals struggle to secure loans due to having an insufficient or nonexistent credit history. Home Credit aims to expand financial inclusion by offering a positive and secure borrowing experience to the unbanked population. Our core business objective is to identify who will default on their home loan, allowing us to ethically extend loans only to those in a good financial situation and who can repay them, thereby mitigating risk and loss for the company.

Project Objective
The primary objective is to develop a robust classification model that accurately predicts the likelihood of an applicant defaulting. This ensures that clients capable of repayment are not rejected and that loans are issued with appropriate terms to maximize their success. We recognize that borrowers tend to exhibit predictable patterns that can be identified through data analysis.

Group Solution & Analytical Approach

Analytical Approach
The project utilized a Predictive Analytics approach based on Classification algorithms. We found that data points such as household demographics, credit history, loan application details, and income were the main predictors.

- Models Evaluated: We ran a baseline model (Logistic Regression on the intercept, AUC 0.5) and compared three advanced models: Logistic Regression (with relevant predictors), Random Forest, and Gradient Boosting Machine (GBM).
- Performance Comparison: All advanced models achieved AUCs around 0.73 to 0.75.
- Final Model Selection: The Gradient Boosting Machine (GBM) was selected as the final model because it yielded the highest AUC.
- Data Strategy & Feature Engineering:
  - Missing values, particularly in the existing source variables (a major predictor), were imputed using the median to maintain them as placeholders and allow us to focus on other variables.
  - We specifically wanted to look beyond existing credit source history, which is the traditional way loans are extended, in order to broaden the scope of people we can approve.

Business Value: Optimizing Profit

The raw AUC value itself is insufficient for business decisions; it must be applied using a threshold10. The primary value of our solution is realized through Profit Curve Analysis.

- Optimal Threshold Determination: The profit table and curve illustrate that choosing the right threshold is crucial. Being too conservative (with a low approval rate) or too aggressive (with a high default rate) results in financial losses.
- Real-World Application: Using a representative loan example (e.g., $600,000 principal, 15% interest, 30 months, 25% recovery rate), the profit curve derived from the real data entries suggests that profitability is maximized by approving as many people as possible, only rejecting the riskiest ~5%(high threshold). This outcome aligns with Home Credit's mission to serve the unbanked population.

Next Steps: Shadow Mode Deployment
To ensure the model is robust and ethically sound before full deployment, we propose a Shadow Mode implementation:

1. Parallel Run: Run the model in the background for six months to a year, where the model scores applicants but the current system makes the final loan decisions (No Interference).

2. Calibration: Compare the model's predictions against actual outcomes. The profit curve will be updated using this real-world data.

3. Full Integration: Use the model for decision-making only after its ROI (Return on Investment) is verified using real-world data gathered.

Individual Contribution and Key Learnings

My Contribution to the Project

Limitations and Next Steps: I focused on identifying model limitations, specifically the issues of imbalanced data and reliance on profit assumptions. I also outlined the clear next step, which is a Shadow Mode Deployment for verification.

What I Learned in the Project

This project provided hands-on experience in solving a complex, real-world business problem:

- Prioritizing Business Metrics: The critical lesson was that the AUC (a technical metric) is secondary to the Profit Curve (a business metric) in determining the optimal decision threshold.
- Ethical Modeling for Financial Inclusion: Learned how modeling objectives can align with ethical goals, specifically by proving that approving more loans (and only rejecting the riskiest) can align with both the business mission (serving the unbanked) and profit maximization.
- Deployment Strategy: Understood the necessity of phased deployment, particularly the Shadow Mode, for high-stakes financial applications before full implementation.
- Data Limitations: Acknowledged and planned for the impact of imbalanced data (only ~8% default rate) and the sensitivity of the outcome to the assumptions used in cost/benefit calculations.
