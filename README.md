# DSC_Phase_3_Project
Syriatel is one of the two dominant mobile network providers in Syria, offering services under its Super Surf brand name. However, it faces growing competition from the recent entry of a third player, Wafa Telecom, which has received an additional telecom license in the country. 

In this intensely competitive market, customer retention is paramount for Syriatel's continued dominance and long-term viability. Losing customers to rival providers directly impacts revenues and profitability. Therefore, Syriatel initiated an advanced analytics project to predict customer churn risk at an individual level and enable targeted retention initiatives.

As the lead data scientist on this project, I developed machine learning models to identify customers likely to churn. The models provide actionable insights to our marketing and customer retention teams on which customers need proactive retention incentives. This approach aligns tightly with Syriatel's strategic imperative of retaining customers in an evolving telecom landscape.

Problem Definition

Syriatel lacked visibility into early warning signs that a customer may be likely to churn. Without a systematic way to predict churn risk, customer losses were often invisible until after the event had occurred.

My project aimed to solve this issue by harnessing customer data to forecast individual churn risk probabilities. The dataset provided by Syriatel contained 3,000 customer records with 20 attributes capturing usage, billing, and demographic details. 

By training advanced machine learning algorithms on this data, I sought to uncover patterns that characterize churn behavior. These predictive insights enable our retention teams to get ahead of potential customer losses.

Data Exploration and Analysis

My first task was thoroughly analyzing this customer dataset to ensure suitability for modeling. I performed extensive exploratory analysis, including:

- Statistical distributions of all variables to identify outliers, skewness, variability 
- Correlation analysis to quantify interconnectivity between attributes
- Segmenting records by churn status for comparative analysis

Key observations included varied account tenure, skewed distribution in international call frequencies, and linkage between service issues and churn. I also found that enrollments in voice mail plans and higher area codes correlated with increased churn likelihood.

These exploratory insights already shed light on potential churn drivers. Furthermore, the analytical phase prepared the data for predictive modeling by handling missing values and redundancies. Removing highly correlated variables guarded against biases during model creation.  

The outcome was a high-quality, churn-specific dataset primed for supervised machine learning algorithms to uncover intricate churn patterns.


Model Development and Evaluation

With a target variable of customer churn status and 19 descriptive attributes, I tested various modeling techniques:

- Dummy baseline classifier 
- Logistic regression
- Decision tree
- Gradient boosting machine (GBM)
- Extreme Gradient Boosting (XGBoost)

I addressed class imbalance using the Synthetic Minority Oversampling Technique (SMOTE). The models were repeatedly cross-validated to minimize selection bias and overfitting. I also performed extensive hyperparameter tuning guided by accuracy and Area Under the ROC Curve (AUC).

The optimized XGBoost model emerged as the top performer by: 

- Achieving 93.5% accuracy on unseen customer data
- Identifying 76% of customers who actually churned
- Maintaining 89% precision to avoid false churn predictions
- Demonstrating robust lift on AUC metric for reliable churn classification  

Additionally, I extracted model insights on the most influential indicators of customer churn, like service calls and area codes.

These comprehensive analytical evaluations solidified the suitability of the XGBoost algorithm for integrating into Syriatel’s customer retention infrastructure.


Strategic Recommendations 
To leverage these machine learning capabilities for business impact, I proposed a strategic roadmap:

- Deploy the XGBoost model for real-time customer churn predictions
- Present insights through an interactive dashboard for retention team
- Proactively offer personalized promotions to likely churners 
- Re-train model periodically with new customer data 
- Initiate small pilot for model-based retention targeting  
- Redirect marketing campaigns from acquisition to retention

As next steps, I recommended rapid test-and-learn iteration cycles to continuously enhance model accuracy, features, and product recommendations over time.

-----

## Installation

```bash
git clone https://github.com/syriatel/churn-prediction.git
cd churn-prediction
pip install -r requirements.txt 
```

## Usage

```python
jupyter notebook churn-modeling.ipynb
```

The notebook covers:

- Data import & exploration
- Feature engineering 
- Model development with cross-validation
- Hyperparameter tuning
- Model evaluation on test set
- Business insights into drivers of churn

## Contents

```
├── data
│   ├── customers.csv - Raw customer data
│   ├── processed.csv - Preprocessed data for modeling 
├── images - Visualizations and model performance charts
├── models - Saved trained models
├── notebooks
│   ├── eda.ipynb - Exploratory data analysis
│   ├── modeling.ipynb - Model training and evaluation
├── src
│   ├── preprocess.py - Script for data preprocessing
│   ├── train.py - Functions to train models
│   ├── evaluate.py - Functions to evaluate models
├── README.md
├── requirements.txt
```

## Contributing

Contributions to improve the analysis are welcome! Please submit issues and pull requests.

## License

This project is licensed under the MIT license. See `LICENSE` for details.

## Authors

- Paul Kamau 

## Acknowledgments

- Syriatel for providing the customer dataset

