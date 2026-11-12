# Custom Transformer: Delivery Time Prediction

## Project Overview

This project demonstrates how to build a custom transformer and integrate it into a scikit-learn pipeline to predict product delivery time.

The dataset contains product packaging dimensions, product weight, seller state, and customer state. The objective is to predict the number of days between an order and its delivery.

## Objectives

- Create a custom transformer to calculate product volume from its dimensions.
- Preserve the original product dimension features.
- Scale numerical features.
- Encode categorical features.
- Combine preprocessing steps using `ColumnTransformer` and `Pipeline`.
- Train a Ridge Regression model.
- Evaluate model performance using cross-validation.
- Predict delivery time for a new order.

## Dataset

The dataset contains 1,000 observations and 7 columns.

| Feature | Description |
|---|---|
| `customer_state` | Customer's state |
| `seller_state` | Seller's state |
| `product_weight_g` | Product weight in grams |
| `product_length_cm` | Product length in centimeters |
| `product_height_cm` | Product height in centimeters |
| `product_width_cm` | Product width in centimeters |
| `days_until_delivery` | Target variable: delivery time in days |

## Methodology

The preprocessing pipeline consists of:

1. **Custom Feature Engineering:** Calculate product volume using length, height, and width.
2. **Numerical Preprocessing:** Apply `StandardScaler` to numerical features.
3. **Categorical Preprocessing:** Apply `OneHotEncoder` to categorical features.
4. **Modeling:** Use `Ridge` Regression as the estimator.

The complete workflow is implemented using scikit-learn's `Pipeline` and `ColumnTransformer`.

## Evaluation and Results

- Cross-validation: 5-fold
- Evaluation metric: R²
- Mean cross-validation R²: **0.1251**
- Predicted delivery time for the new order: **20.67 days**

The relatively low R² score is expected for this challenge.

## Technologies

- Python
- Pandas
- NumPy
- Scikit-learn
- Seaborn
- Jupyter Notebook

## Project Structure

```text
.
├── 02-Custom-Transformer.ipynb
├── tests/
│   ├── test_pipe.py
│   ├── test_prediction.py
│   ├── pipe.pickle
│   └── prediction.pickle
├── Makefile
└── README.md
```

## Key Learning Outcomes

- Building custom transformers with `FunctionTransformer`
- Creating reusable preprocessing pipelines
- Combining numerical and categorical transformations
- Performing feature engineering
- Evaluating regression models with cross-validation

## Project Purpose

This project was completed as part of the Workintech Data Science and AI training program to practice custom feature engineering and scikit-learn pipeline development.
