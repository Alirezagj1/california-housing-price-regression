A neural network regression project built with PyTorch to predict median house values using the California Housing dataset.

## Project Overview

This project implements a fully connected neural network to predict median house values based on geographical and demographic features.

The project covers the main stages of a machine learning workflow, including data exploration, preprocessing, feature scaling, model development, training, and evaluation.

## Dataset

The California Housing dataset is loaded using Scikit-learn.

- **Dataset:** California Housing
- **Samples:** 20,640
- **Features:** 8 numerical features
- **Target:** Median house value
- **Task:** Supervised Regression

The target variable is measured in units of $100,000.

## Technologies & Libraries

- Python
- PyTorch
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter

## Methodology

### 1. Data Loading & Exploration

- Loading the California Housing dataset.
- Separating input features and target values.
- Checking data types and dimensions.
- Checking for missing, infinite, and invalid values.

### 2. Data Preprocessing

The dataset is divided into three subsets:

| Dataset    | Percentage |
|------------|------------|
| Training   | 60%        |
| Validation | 20%        |
| Testing    | 20%        |

Min-Max normalization is applied to both input features and target values.

To prevent data leakage, the scalers are fitted only on the training data. The same transformations are then applied to validation and test data.

The processed data is converted into PyTorch tensors for model training.

### 3. Model Architecture

A fully connected neural network is implemented using PyTorch's `nn.Sequential`.

| Layer          | Neurons | Activation |
|----------------|---------|------------|
| Input          | 8       | -          |
| Hidden Layer 1 | 24      | ReLU       |
| Hidden Layer 2 | 12      | ReLU       |
| Hidden Layer 3 | 6       | ReLU       |
| Output         | 1       | Linear     |

### 4. Model Training

The model is trained using the following configuration:

| Parameter      | Value |
|----------------|-------|
| Optimizer      | Adam  |
| Loss Function  | MSE   |
| Learning Rate  | 0.001 |
| Epochs         | 100   |
| Batch Size     | 32    |

Training and validation losses are monitored throughout the training process.

The model weights with the lowest validation loss are saved and restored for final evaluation.

### 5. Model Evaluation

The final model is evaluated on the unseen test dataset.

The predictions are converted back to the original target scale before calculating evaluation metrics.

The following metrics are used:

- **MAE:** Mean Absolute Error
- **MSE:** Mean Squared Error
- **RMSE:** Root Mean Squared Error
- **R²:** Coefficient of Determination

## Results

### Test Set Performance

- **MAE:** 0.4218
- **MSE:** 0.4021
- **RMSE:** 0.6341
- **R² Score:** 0.7067

The model achieves an R² score of approximately 0.71, explaining around 70.67% of the variance in the test target values.

Since the target is measured in units of $100,000:

- MAE corresponds to approximately $42,180.
- RMSE corresponds to approximately $63,410.

## Visualizations

The notebook includes the following visualizations:

- Training and validation loss curves.
- Actual vs. predicted house values.

## Installation & Usage

### 1. Clone the Repository

```bash
git clone https://github.com/Alirezagj1/california-housing-price-regression.git
cd california-housing-price-regression
pip install -r requirements.txt
```
## Author

**Name:** Alireza Gorji

M.Sc. Student in E-commerce | Machine Learning Enthusiast

- **Project Type:** Machine Learning / Regression
- **Framework:** PyTorch