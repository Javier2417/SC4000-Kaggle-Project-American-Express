# AMEX Default Prediction: Collaborative High-Scale Classification
### Rank 11 (Top 15%) | SC4000 Team Project (NTU)

## 📌 Project Overview
This project was developed as a collaborative effort for the SC4000 Machine Learning module at NTU. The goal was to predict credit default for American Express using an industrial-scale dataset of 5.5M+ records. Our team achieved a Top 15% placement by implementing a robust, memory-efficient pipeline and a diverse stacked ensemble.

## 🛠️ Individual Technical Focus (Javier Tin)
While this was a team effort, my primary responsibilities focused on the end-to-end pipeline infrastructure and memory management:

Pipeline Optimization: Engineered a high-performance training pipeline using chunk-based processing and float16 downcasting to manage 50GB+ of raw data on limited hardware.

Temporal Feature Engineering: Developed lagged behavior features and deterioration metrics to capture shifting customer credit profiles.

Model Contribution: Personally implemented and tuned the LightGBM and DART base models and architected the final Logistic Regression meta-learner for model blending.

## 🤝 Team Ensemble Strategy
Our high ranking was the result of a diverse Stacked Ensemble, combining multiple architectures to minimize variance and capture non-linear relationships:

Base Models: Included a mix of Gradient Boosted Decision Trees (LGBM, CatBoost, and XGBoost) and deep learning approaches contributed by team members (Yu Teng and others).

Diversity Gain: By combining models with different inductive biases, the team was able to achieve a significant boost in the competition metric that no single model could reach alone.

Stacking: Predictions from all team members were aggregated into a Level-1 meta-learner to maximize generalization on the private leaderboard.

## 📊 Results & Reproducibility
Private Leaderboard Score: 0.798 (Rank 11 / Top 15%).

Honesty & Transparency: This repository serves as a technical record of my specific contributions to the group project. It acknowledges the use of community-vetted strategies as a benchmark for independent implementation and optimization.
