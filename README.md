ESG Analytics Project – ESG Decoupling in Chinese Firms

This project investigates ESG Decoupling—the divergence between Bloomberg ESG scores, independent third-party ESG ratings, and news sentiment. We analyzed this phenomenon using a structured and scalable analytics pipeline.

📌 Project Objectives
Quantify ESG decoupling between different rating systems

Analyze regional and sectoral patterns of ESG inconsistencies

Assess media sentiment alignment with formal ESG scores

Forecast ESG performance using time-series models

📂 Data Sources
BloombergESG.xlsx – Company-level Bloomberg ESG data (2009–2023)

ESGperformance.xlsx – Independent ESG ratings with E/S/G component breakdowns

news.xlsx – Annual news sentiment counts (positive/neutral/negative)

🧱 Database Design
Developed a relational schema in SQLite, visualized through an ERD

Tables:

COMPANIES – Company metadata

BLOOMBERG_ESG – Bloomberg scores (E/S/G + Total)

ESG_PERFORMANCE – Independent ratings

NEWS_SENTIMENT – Sentiment analysis results

Foreign key relationships established on Company_ID and Year

⚙️ Data Pipeline
Column translation from Spanish to English using Google Sheets

Schema mapping and data cleaning in Python

Automated data loading into SQLite

Missing value handling and consistency checks

📈 Modeling and Analysis
ESG Decoupling Score = 70% weight to Bloomberg vs Independent difference + 30% to Bloomberg vs News Sentiment difference

Models Used:

Linear Regression

Random Forest

XGBoost (Best performance: R² = 0.59, RMSE = 6.46)

Key Features: Year, Region (East/Mid/West), Polluting & High-Tech flags, Industry dummies

📊 Key Insights
Average decoupling: 60.72% with notable firm-specific outliers (e.g., Jishi Media = 87.03%)

Environmental & Social components showed the highest discrepancies

Weak sentiment alignment (Pearson correlation: ~0.10–0.17)

Minimal regional variation, suggesting firm and industry effects dominate

📉 Time-Series Forecasting
Used ARIMA to forecast ESG scores for Shenzhen Energy

Predicted ESG scores:

2025: 54.71

2026: 56.61

Evaluation metrics:

RMSE = 3.178

MAE = 2.349

MAPE = 7.968

🔮 Future Work
Integrate Isolation Forest and LOF for anomaly detection

Explore LSTM models for ESG trajectory prediction

Extend analysis to cross-country comparisons
