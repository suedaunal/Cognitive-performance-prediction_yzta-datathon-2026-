#  Cognitive Performance Prediction | GOOGLE Aİ& TECHNOLOGY ACADEMY 2026 Datathon


##  Project Overview
This project was developed as part of the **Google AI & Technology Academy (YZTA) 2026 Datathon**. The core objective was to predict individuals’ cognitive performance scores by leveraging sleep, stress, behavioral, and physiological data.

Instead of just fitting baseline models, this project focuses on building a robust **ensemble machine learning pipeline** driven by rigorous residual analysis, subgroup error diagnostics, and iterative feature engineering.

---

## Tech Stack & Tools
* **Data Manipulation:** `pandas`, `numpy`
* **Modeling & Frameworks:** `scikit-learn`, `LightGBM`, `CatBoost`, `XGBoost`
* **Hyperparameter Tuning:** `Optuna`

---

##  The Approach

### 1. Validation Strategy
To prevent data leakage and ensure robust generalization, we implemented:
* **Stratified K-Fold Cross-Validation**
* Out-of-fold (OOF) prediction tracking
* Ensemble correlation analysis to maintain model diversity
* **Primary Metric:** Root Mean Squared Error (RMSE)

### 2. Feature Engineering (Quality over Quantity)
Rather than flooding the model with raw interactions, we engineered domain-specific features focusing on biological and environmental variances:
* **Sleep Dynamics:** Sleep Quality Index, Sleep Disruption Score
* **Stress & Recovery:** Workload vs. Recovery Balance, Stress–Sleep Interaction metrics
* **Environmental Context:** Room Temperature Risk, Environmental Deviation Effects

### 3. Ensemble Pipeline
We developed a weighted blending pipeline using gradient boosting giants:
* **CatBoost** (Served as the backbone due to strong categorical handling)
* **LightGBM** (Optimized for speed and efficiency)
* **XGBoost** (Integrated selectively based on correlation analysis)

---

##  Key Findings & Results

>  **Best CV RMSE:** `~1.2147`

* **The Diversity Bottleneck:** Later stages of optimization revealed that model diversity became a larger limitation than raw single-model performance. XGBoost's contribution was limited due to its high prediction correlation with LightGBM.
* **Granular Error Analysis:** Residual diagnostics showed that **weekday samples (`gun_tipi=0`)** and specific **occupation–mental health combinations** exhibited significantly higher variance and were harder to predict.
* **Feature Impact:** Deviation-based features contributed much more effectively to variance reduction than excessive brute-force interaction features.

---

##  Key Takeaways
This datathon reinforced critical real-world machine learning principles:
1. **Diagnostics Matter:** Subgroup-level error analysis (residual analysis) is key to understanding *where* the model fails.
2. **Feature Representation > Feature Quantity:** Meaningful domain features beat brute-force combinations every time.
3. **Ensemble Strategy:** Maximizing model diversity is just as important as hyperparameter tuning.

---
