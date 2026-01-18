# SC4000-Kaggle-Project-American-Express
American Express Default Prediction: High-Scale Binary Classification
Rank 11 (Top 15%) Reproduction & Pipeline Optimization

## 📌 Project Overview
This project focuses on predicting credit default using a large-scale industrial dataset from American Express. The primary challenge was managing 5.5M+ records (over 50GB raw) while engineering temporal features to capture customer behavior deterioration over time.

This repository serves as a technical reproduction and optimization of state-of-the-art (SOTA) solutions, benchmarking pipeline efficiency and memory management in a resource-constrained environment.

## 🛠️ Technical Highlights
Memory Optimization: Implemented chunk-based processing and float16 downcasting, reducing memory footprint by ~70% to allow for local training on consumer-grade hardware.

Temporal Feature Engineering: Engineered complex features across multiple time windows, including lagged means, first/last ratios, and aggregated deterioration metrics.

Ensemble Architecture: Built a two-layer stacked ensemble utilizing LightGBM, CatBoost, and DART models, optimized via a Logistic Regression meta-learner.

Validation Strategy: Utilized GroupKFold cross-validation to ensure model robustness and prevent leakage across customer IDs, resulting in a significant climb from public to private leaderboard rankings.

## 🏗️ Model Architecture
The final model utilizes a stacking approach to blend the strengths of different gradient-boosting frameworks:

Level 0 (Base Models):

LightGBM: Fast training and excellent handling of categorical features.

CatBoost: Robust handling of noisy features and high-cardinality data.

DART: Dropouts meet Multiple Additive Regression Trees to prevent over-reliance on specific features.

Level 1 (Meta-Learner):

Logistic Regression: A simple, linear meta-learner to blend predictions and maximize the Amex-specific competition metric.

## 📊 Results
Private Leaderboard Score: 0.798 (Equivalent to Rank 11 / Top 15%)

Performance: Achieved high stability across timefolds, moving up 200+ spots from public to private rankings through robust feature selection.

## 🧪 Reproducibility & Acknowledgements
This project was developed as a benchmark for the SC4000 Machine Learning module at NTU.

To maintain intellectual honesty and technical transparency:

The architecture was inspired by top-performing community strategies from the original 2022 competition.

The primary objective of this repository was the independent implementation of these strategies, specifically focusing on the software engineering challenges of scaling the pipeline to handle 5.5M records.
