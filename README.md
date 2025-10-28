# provider-contract-analytics
Data analytics project simulating provider contract performance and cost-of-care modeling. Uses Python and SQL-style workflows to identify cost drivers, forecast provider expenses, and evaluate potential savings from value-based care initiatives.
Provider Contract Analytics

Data Analytics for Cost of Care Optimization and Value-Based Contracting

Research Question

How can healthcare claims and quality data be analyzed to identify cost drivers, improve provider performance transparency, and support value-based contract negotiations?

Overview

This project applies cost-of-care analytics to simulate the process used by health plan analysts and provider contracting teams. Using synthetic claim-level data, the analysis identifies the primary drivers of healthcare cost variation, visualizes quality–cost relationships, and quantifies provider-level performance differentials.

The workflow mirrors real-world analytics performed in payer organizations such as Elevance Health to guide contracting decisions, improve network efficiency, and support value-based care models.

Objectives

Explore cost distributions across specialties and states to identify high-cost outliers.

Model cost drivers using regression and feature-importance techniques.

Detect anomalies in claim patterns that indicate potential inefficiencies or unusual billing behavior.

Provide actionable insights to support provider negotiations and contracting strategies.

Methodology

The project follows the scientific method framework:

Step	Action
1. Ask a Question	What factors most strongly influence total claim cost?
2. Conduct Background Research	Review payer-side cost of care analytics and value-based frameworks.
3. Form a Hypothesis	Higher chronic condition counts, readmission rates, and low quality scores will correlate with higher claim costs.
4. Test the Hypothesis	Apply regression modeling and outlier detection to synthetic healthcare data.
5. Analyze the Data	Visualize cost distributions, quality vs. cost trends, and identify top cost predictors.
6. Draw Conclusions	Summarize key cost drivers and recommend follow-up analytic improvements.
Technical Approach

1. Data Preparation

Synthetic dataset simulating provider, member, and claim-level attributes.

Cleaning and normalization of numeric and categorical features.

2. Exploratory Data Analysis

Visualized cost distribution histograms, boxplots by specialty, and quality/cost scatterplots.

Aggregated provider-level summaries to identify outliers.

3. Modeling

Linear regression model to evaluate feature importance in predicting claim cost.

Extracted top predictors including readmission rate, chronic condition count, and member utilization.

4. Evaluation

MAE ≈ 2,086; RMSE ≈ 3,160; R² ≈ 0.004 (indicating non-linearity in real-world cost behavior).

Recommended tree-based models (e.g., Random Forest, Gradient Boosting) for future accuracy improvement.

5. Anomaly Detection

Isolation Forest used to identify ~5% of records as potential outliers for further review.

Results Summary
Category	Key Insight
Descriptive Analysis	Cost highly skewed; top 1% of members ≈ 10–15× median spend
Predictive Modeling	Readmission rate, chronic conditions, and state effects most predictive
Performance	R² ≈ 0.0 indicates high variance typical of healthcare cost data
Next Steps	Explore nonlinear models and time-series segmentation
Artifacts

📊 figures/ — visualizations (cost distribution, feature importance, etc.)

📁 data/processed/ — provider summary and feature importance outputs

📄 notebooks/provider_contract_analytics.ipynb — main analysis notebook

# 1. Clone repository
git clone https://github.com/mspmohle/provider-contract-analytics.git
cd provider-contract-analytics

# 2. Create and activate environment
conda create -n elevance python=3.11 -y
conda activate elevance

# 3. Install dependencies
pip install -r requirements.txt

# 4. Launch Jupyter Lab
jupyter lab


Results & Discussion

The analysis confirmed that healthcare claim costs are highly variable and non-linear, driven by a small subset of members and providers who account for a disproportionate share of total spending. In the synthetic dataset—representing patterns typical of real payer data—the top 1% of members incurred costs approximately 10–15 times higher than the median. This skewed cost distribution highlights why payers focus heavily on identifying outliers and understanding specialty-driven variation.

Regression analysis showed that traditional linear models explain little of this variance (R² ≈ 0.0–0.1), reflecting the complex, multi-factor nature of healthcare utilization. However, the model successfully identified readmission rate, chronic condition count, and visit frequency as consistent cost-increasing factors. These predictors align with real-world expectations: higher readmission rates suggest inefficiencies or poor care coordination, while frequent visits and multiple chronic conditions are hallmarks of high-risk members.

From an operational standpoint, this kind of modeling provides a data-driven foundation for provider negotiations and value-based contracting. By quantifying how specific attributes correlate with higher cost or lower quality, analysts can target performance-improvement initiatives and tailor reimbursement structures. For instance, providers with high readmission-adjusted costs could be prioritized for care management programs or alternative payment models.

Future iterations of this analysis should explore nonlinear models such as Gradient Boosting or Random Forest regressors, which can capture complex interactions between utilization, quality, and geography. Incorporating additional contextual variables—such as social determinants, pharmacy adherence, or facility type—would further enhance predictive accuracy and insight.

Overall, this project demonstrates a scalable analytic workflow for cost transparency, performance benchmarking, and contracting optimization—core functions of modern healthcare analytics teams.

License
MIT License.
