
# Laptop Price Predictor

## Description
This project uses machine learning to predict laptop prices based on their specifications. The model is trained on a dataset containing various features of laptops and their corresponding prices. The goal is to provide accurate price predictions for laptops based on attributes such as company, type, RAM, weight, and other specifications.

## Technologies Used
- **Python**: The primary programming language used.
- **Jupyter Notebook**: For writing and executing the code.
- **Libraries**:
  - `pandas`: For data manipulation and analysis.
  - `seaborn` and `matplotlib`: For data visualization.
  - `scikit-learn`: For machine learning models, including preprocessing and evaluation.

## Dataset
The dataset includes the following features:
- `Company`: The brand of the laptop.
- `TypeName`: The type of laptop (e.g., Notebook, Ultrabook).
- `Ram`: The amount of RAM in GB.
- `Weight`: The weight of the laptop.
- `Touchscreen`: A binary indicator for touchscreen capability.
- `Ips`: A binary indicator for IPS display.
- `ppi`: Pixels per inch, a measure of screen density.
- `Cpu brand`: The brand of the CPU (e.g., Intel, AMD).
- `HDD`: Hard disk drive storage in GB.
- `SSD`: Solid-state drive storage in GB.
- `Gpu brand`: The brand of the GPU (e.g., Intel, Nvidia, AMD).
- `os`: The operating system (e.g., Windows, macOS).
- `Price`: The target variable (price of the laptop).

The dataset consists of 1302 rows and 13 columns.

## Exploratory Data Analysis (EDA)
The notebook includes exploratory data analysis to visualize relationships between features and the target variable (Price). This helps in understanding which features are most influential in determining laptop prices. For example:
- Scatter plots show the relationship between screen size and price.
- Bar plots illustrate the impact of features like touchscreen, IPS panel, CPU brand, and GPU brand on price.
- Correlation matrices help identify correlations between numerical features.

This EDA guides the feature engineering and model selection process.

## Model
A stacking regression model is used to predict laptop prices. The model combines:
- **Base models**:
  - `RandomForestRegressor` with hyperparameters (350 estimators, random state 3, max samples 0.5, max features 0.75, max depth 15).
  - `GradientBoostingRegressor` with 100 estimators and max features 0.5.
- **Final estimator**: `Ridge` regression with an alpha value of 100.

**Data Preprocessing**:
- Categorical variables (e.g., `Company`, `TypeName`, `Cpu brand`, `Gpu brand`, `os`) are encoded using `OneHotEncoder`.
- Numerical features are passed through unchanged.

The model is implemented using a pipeline that includes both preprocessing and the stacking regressor.

## Performance
The model's performance on the test set is evaluated using the following metrics:
- **R2 Score**: 0.875 (indicating that about 87.5% of the variance in the target variable is explained by the model).
- **Mean Absolute Error (MAE)**: 0.171 (measuring the average absolute difference between predicted and actual values).

## How to Run
To run the project, follow these steps:
1. Ensure you have Python and Jupyter Notebook installed.
2. Open the file `laptop_price_predictor(1).ipynb` in Jupyter Notebook.
3. Run the cells sequentially to see the data preprocessing, exploratory data analysis, model training, and evaluation.

Alternatively:
- The trained model is saved as `pipe.pkl` and can be loaded using `pickle` for making predictions on new data.
- The dataset is saved as `df.pkl` for reference.

## Files
- `laptop_price_predictor(1).ipynb`: The Jupyter Notebook containing the project code, including data preprocessing, EDA, model training, and evaluation.
- `df.pkl`: The pickled dataset used for training and testing.
- `pipe.pkl`: The pickled trained model for making predictions.
