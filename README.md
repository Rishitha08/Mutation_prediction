# Mutation Impact Prediction using Random Forest

This project applies machine learning techniques to predict how genetic mutations affect gene functionality, measured through fitness scores. Using data from the Project SCORE initiative, we train and evaluate a Random Forest model to regress gene mutation impact.

## Project Overview
Genetic mutations can influence the fitness of genes, affecting processes like cancer progression and cell survival. This project leverages regression models to predict those effects using curated mutation profiles.

## Dataset Description

- **Source:** Project SCORE: Sanger v2 + Broad 21Q2
- **Format:** TSV (tab-separated values)
- **Size:** 16,506 genes × 1,107 features
- **Target variable:** Bayesian Fitness Score

> Preview of Raw Data  
> ![image](https://github.com/user-attachments/assets/e41d0e85-ecd7-45f4-ab3d-51bb03c6ac45)
 

## Machine Learning Workflow:

### 1. Data Preprocessing
- Handled missing values
- Selected relevant columns
- Split into training (80%) and testing (20%) sets

### 2. Model Training
- Used `RandomForestRegressor` from `scikit-learn`

### 3. Evaluation Metrics
- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- R² Score


## Model Results:

| Metric | Value |
|--------|-------|
| MAE    | ~0.94 |
| MSE    | ~1.86 |
| R²     | ~0.73 |

Graphs:
![Untitled](https://github.com/user-attachments/assets/67223346-9ea7-4ed4-8cbc-aab373a8a522)

![Untitled-1](https://github.com/user-attachments/assets/7b30f1a5-b4e2-4633-b6ad-812c7874bc82)

## Tools Used
- Python
- Pandas, NumPy
- scikit-learn
- Matplotlib, Seaborn
- Jupyter Notebook / Google Colab

