Amazon Product Sales Prediction - README

Overview

This project builds machine learning models to predict future sales of Amazon products based on product details and customer reviews.

Two scripts are provided:

predictFutureSales0.py: Basic version without sentiment analysis (faster runtime).

predictFutureSales1.py: Complete version with TextBlob sentiment analysis and fine-tuning (longer runtime).

Goals

Clean and merge product and review datasets.

Engineer new features (e.g., review sentiment scores).

Train Random Forest and XGBoost regressors to predict future sales.

Analyze feature importance to understand key sales drivers.

File Descriptions

predictFutureSales0.py

Loads and merges product and review datasets.

Builds models using basic product statistics.

Faster runtime since no text sentiment analysis is performed.

predictFutureSales1.py

Same as predictFutureSales0.py plus:

Applies TextBlob to calculate sentiment scores from review text.

Adds "Avg_Sentiment_Score" as a predictive feature.

Fine-tunes model parameters.

Note: Runtime is longer due to per-review text processing.

R^2 Performance Metrics (from predictFutureSales1.py)

Random Forest R² on Test Set: 0.6057

XGBoost R² on Test Set: 0.7047

Requirements

Python 3.x

Libraries: pandas, scikit-learn, xgboost, textblob, matplotlib

Install dependencies with:

pip install pandas scikit-learn xgboost textblob matplotlib

If running the TextBlob version, also run:

python -m textblob.download_corpora

Notes

The Avg_Sentiment_Score feature was crucial in improving prediction performance.

Brand categories (one-hot encoded) also played a significant role.

Future improvements could involve using a faster sentiment analyzer (e.g., VADER) for quicker processing.

Developed as part of a machine learning pipeline exploration for Amazon product datasets for the AIM lab at the University of Toronto Scarborough.

