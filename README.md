<div align="center">

# Poverty Level Prediction in Indonesia

**End-to-End Regression Modeling utilizing XGBoost to map socioeconomic determinants across 514 districts.**

</div>

---

### Project Overview
This project aims to identify the key macroeconomic and developmental drivers of poverty to extract data-driven, actionable insights that can support precision-targeted public policy formulation. Due to the highly complex and non-linear interactions within regional socioeconomic data, an optimized **Extreme Gradient Boosting (XGBoost Regressor)** model was developed.

---

### Analytical Workflow & Pipeline

**1. Data Ingestion & Integration**
* Sourced cross-sectional regional data from **Badan Pusat Statistik (BPS)** covering 514 districts/cities.
* Consolidated 12 core variables spanning Human Development, Economic Drivers, Labor Market, and Infrastructure.

**2. Data Engineering & Preprocessing**
* **Imputation:** Handled structural missing values via Robust Median Imputation to prevent outlier distortion.
* **Feature Scaling:** Applied `StandardScaler` to continuous predictors to stabilize mathematical convergence.
* **Feature Engineering:** Developed spatial interaction metrics and handled dummy variable traps (`drop_first=True`) for categorical geospatial data.

**3. Modeling & Hyperparameter Optimization**
* Implemented **XGBoost Regressor** to capture non-linear socioeconomic relationships.
* Conducted rigorous hyperparameter tuning utilizing `GridSearchCV` with 3-fold cross-validation.
* **Tuned Parameters:** `n_estimators`, `max_depth`, `learning_rate`, and `subsample`.

**4. Evaluation & Interpretability**
* Benchmarked the optimized model against baseline Linear Regression and Random Forest architectures.
* Extracted **Feature Importance** to translate black-box model decisions into actionable policy insights.

---

### Core Findings & Performance

The optimized XGBoost model demonstrated highly efficient parameter usage without signs of overfitting:

| Metric | Score | Interpretation |
| :--- | :---: | :--- |
| **R² (Coefficient of Determination)** | **0.77** | Explains 77% of the total variance in regional poverty. |
| **RMSE** | **4.00** | Predictions deviate by only 4.00 percentage points on average. |
| **Dominant Feature** | **IPM** | Indeks Pembangunan Manusia emerged as the single most critical determinant, solidifying the Human Development Theory in poverty reduction. |

### Conclusion & Key Takeaways
The tuned **XGBoost Regressor** achieved a robust **77% predictive accuracy**, proving that complex machine learning architectures can effectively translate messy socioeconomic datasets into clear, actionable policy-targeting tools.

* **Human Capital is Key:** The analysis confirms that the *Indeks Pembangunan Manusia (IPM)* is the single most powerful predictor of poverty. Any poverty reduction strategy that ignores education and health quality will likely be ineffective.
* **Policy Implication:** Given the model's findings, resource allocation should prioritize human capital development over mere infrastructure expansion. This analytical framework now serves as the foundation for my current research into public policy interventions, such as the *Makanan Bergizi Gratis (MBG)* program, where nutritional impact is evaluated as a critical component of regional human development.

---

### 📂 Repository Structure

```text
├── data/
│   └── bps_socioeconomic_data.csv       # Raw dataset
├── notebooks/
│   └── poverty_prediction_xgboost.ipynb # Main analysis and modeling notebook
├── README.md                            # Executive summary and documentation
