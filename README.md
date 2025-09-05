## Overview

This project aims to build a machine learning model to predict used car prices based on various features. The workflow includes data exploration, cleaning, transformation, feature engineering, and model training using a linear regression pipeline. The dataset is sourced from train.csv and the analysis is performed in a Jupyter notebook (Car_Price_Pred.ipynb).

## Data

- **Source:** train.csv
- **Features:**  
  - `brand`: Car manufacturer  
  - `model`: Car model  
  - `model_year`: Year of manufacture  
  - `milage`: Mileage of the car  
  - `fuel_type`: Type of fuel (Gasoline, Diesel, Electric, Hybrid, etc.)  
  - `engine`: Engine details  
  - `transmission`: Transmission type  
  - `ext_col`: Exterior color  
  - `int_col`: Interior color  
  - `accident`: Accident history  
  - `clean_title`: Title status  
  - `price`: Target variable (car price)

## Workflow

### 1. Import Dependencies

Libraries used include pandas, numpy, matplotlib, seaborn, scikit-learn, and missingno for data visualization and modeling.

### 2. Data Exploration (EDA)

- Displayed basic statistics and info about the dataset.
- Visualized missing values and feature distributions.
- Checked for outliers and multi-collinearity.

### 3. Data Cleaning & Transformation

- Handled missing values:
  - Set Tesla fuel types to "Electric".
  - Filled missing `fuel_type` with the mode.
  - Corrected inconsistencies between `accident` and `clean_title`.
  - Imputed missing values in `accident` and `clean_title` based on logical rules.
- Outlier handling using IQR clipping.
- Log transformation applied to the `price` column to reduce skewness.

### 4. Feature Engineering

- Selected relevant features for modeling:  
  `brand`, `model_year`, `milage`, `fuel_type`, `accident`, `clean_title`
- Target variable: log-transformed price (`price_log`).

### 5. Model Building

- Split data into training and test sets.
- Built a scikit-learn pipeline:
  - **Preprocessing:** One-hot encoding for categorical features, standard scaling for numerical features.
  - **Model:** Linear Regression.
- Trained the model and made predictions.

### 6. Evaluation

- Calculated Mean Squared Error (MSE) and R² score on the test set.
- Inverted log transformation for interpretability of predictions.

## Results

- The model provides a baseline for car price prediction.
- Evaluation metrics (MSE, R²) are printed at the end of the notebook.

**Files:**  
- Car_Price_Pred.ipynb – Main notebook  
- train.csv – Dataset
