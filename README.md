#Mutation Impact Prediction Using Random Forest:

## Problem Statement:

Cancer progression and various genetic disorders are significantly influenced by gene mutations. Determining the **impact** of these mutations on gene fitness is critical for understanding disease mechanisms and prioritizing mutations for further study.However, experimental validation of every mutation is time-consuming and resource-intensive. Currently, researchers manually interpret mutation impacts from clinical or genomic data, which slows down the process of discovery and delays potential treatments.Our project proposes a solution to **automatically predict the impact of mutations on gene fitness** using machine learning, enabling faster, scalable, and more consistent results.

---

## Solution
We propose a **regression-based machine learning model** that predicts the impact of a given mutation using genomic features. Specifically, we implemented a **Random Forest Regressor** to predict fitness scores, which represent how a mutation affects the survival or growth of a cell.

This model will:
* Help researchers identify impactful mutations quickly.
* Reduce manual effort in genomic data analysis.
* Improve prioritization in functional experiments.

---
## Dataset Used

We used the publicly available dataset from the **Project SCORE** initiative:

* `Project_score_combined_Sanger_v2_Broad_21Q2_fitness_scores_bayesian_factors_20240111.tsv`

### Dataset Overview:
* Rows: \~16,506 genes
* Features: \~1,107 numerical features
* Target: `Fitness score` — represents the impact of the mutation (lower = more harmful)

---

### 🔹 Preprocessing Steps

1. **Load Dataset**: Loaded the TSV dataset using `pandas`.
2. **Missing Values**: Checked and handled missing data.
3. **Feature/Target Split**: Separated input features (`X`) from target variable (`y` = fitness score).
4. **Train-Test Split**: Used an 80/20 split with `train_test_split`.
5. **Normalization**: Scaled features using `StandardScaler`.

---

## Exploratory Data Analysis (EDA)

* Analyzed distribution of fitness scores.
* Checked for feature variance and correlations.
* Visualized fitness impact using histograms and scatter plots.

---

## Model Used — Random Forest Regressor

Random Forest is an ensemble learning algorithm that combines multiple decision trees to improve accuracy and control overfitting.
* Works well on tabular, high-dimensional data.
* Handles nonlinear relationships.
* Provides **feature importance** scores for interpretation.

### Model Configuration:

```python
RandomForestRegressor(
    n_estimators=100,
    max_depth=None,
    random_state=42
)
```

### Evaluation Metrics:

* **Mean Squared Error (MSE)**: 1.86
* **Mean Absolute Error (MAE)**: 0.94
* **R² Score**: 0.7347 (73.47% of variance explained)

---

## 📊 Model Performance

| Metric | Value  |
| ------ | ------ |
| MSE    | 1.8605 |
| MAE    | 0.9417 |
| R²     | 0.7347 |

The model performs fairly well with a **R² score of 73.47%**, indicating strong predictive power on unseen gene mutations.

---
## Future Improvements

While this project achieved a good baseline, future enhancements could include:

* Use of deep learning (e.g., feedforward networks)
* Integration with external biological annotations (e.g., pathways)
* Application of SHAP for model explainability
* Hyperparameter tuning via RandomizedSearchCV or GridSearchCV

---
## Conclusion

This project demonstrates that machine learning — particularly Random Forest — can be successfully applied to predict the impact of gene mutations. Such tools can drastically accelerate genomic research, support experimental prioritization, and ultimately contribute to faster therapeutic developments.

---

##References

* [Project SCORE Dataset](https://score.depmap.sanger.ac.uk/)
* Scikit-Learn Documentation
* Random Forest Algorithm - Breiman (2001)

Would you like this in `.md` format ready to upload to GitHub? Or should I add images like graphs and performance plots into the README as well?
