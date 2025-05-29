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

Random Forest: Random forest is a supervised learning algorithm. It is a classification algorithm that consists of several decision trees. When constructing, each particular tree in the forest makes a class prescience and the class with the maximum votes becomes the prediction of our model. The count vectors obtained from the sparse matrix are fitted and test scores are calculated by tuning the various parameters to achieve the optimum performance of the model. The average accuracy score for this model is coming out to be 49%. We used the RandomForestClassifier function for the Model. Also, we have used the calibrated classifier that predicts the class probabilities rather than the absolute values along with the sigmoid activation function. Predicting probabilities provides better ways to evaluate the model. We identified the best alpha value and predicted the class using it. We used the Log Loss (Logarithmic Loss) as a performance measurement function. In Log Loss the prediction output is a probability value between 0 and 1.


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

