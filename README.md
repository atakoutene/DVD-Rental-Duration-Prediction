# DVD Rental Duration Prediction

This project utilizes regression models to predict the number of days a customer rents DVDs. The analysis includes data preprocessing, feature engineering, model training, and evaluation. The goal is to recommend a regression model with a mean squared error (MSE) of less than 3 on the test set.

## Table of Contents

- [Introduction](#introduction)
- [Dataset](#dataset)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Code Explanation](#code-explanation)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## Introduction

This project aims to predict DVD rental duration using various regression models. The steps include data preprocessing, feature engineering, model selection, and evaluation to find the best predictive model with the lowest MSE.

## Dataset

The dataset used is `rental_info.csv`, which includes:
- `rental_date`: The date the DVD was rented
- `return_date`: The date the DVD was returned
- `special_features`: Special features of the DVD, such as "Deleted Scenes" and "Behind the Scenes"

## Requirements

The required libraries for this project are:
- `pandas`
- `numpy`
- `scikit-learn`

## Installation

To install the required libraries, run:
```bash
pip install pandas numpy scikit-learn
```

## Usage

1. Clone the repository:
```bash
git clone https://github.com/atakoutene/DVD-Rental-Duration-Prediction.git
cd dvd-rental-duration-prediction
```

2. Ensure the dataset `rental_info.csv` is in the project directory.

3. Run the script:
```bash
python dvd-rental-duration-prediction.py
```

## Code Explanation

- **Data Loading and Preprocessing**: Load the dataset and create a new column `rental_length_days` by calculating the difference between `return_date` and `rental_date`.
- **Feature Engineering**: Create dummy variables for `special_features`, specifically `deleted_scenes` and `behind_the_scenes`.
- **Train-Test Split**: Split the data into training and testing sets with a 20% test size and a random state of 9 for reproducibility.
- **Model Training and Evaluation**:
  - **Lasso Regression**: Perform feature selection using Lasso regression and train a linear regression model on the selected features.
  - **Random Forest Regressor**: Use RandomizedSearchCV to find the best hyperparameters for the random forest model and evaluate its performance.
- **Model Selection**: Compare the MSE of the models and select the best-performing model.

## Results

The random forest model with the best hyperparameters provided the lowest mean squared error (MSE). The recommended model is saved as `best_model`, and its MSE is saved as `best_mse`.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request or open an issue for any bugs or feature requests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
