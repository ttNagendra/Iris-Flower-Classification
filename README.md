# Iris Flower Species Classification

[![Python](https://img.shields.io/badge/Python-3.7%2B-blue)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-Latest-orange)](https://scikit-learn.org/)

This project implements a machine learning model to classify Iris flowers into three species based on their measurements. The model achieves >90% accuracy using a Random Forest Classifier with optimized hyperparameters.

## Project Objectives

1. Build a classification model to identify Iris flower species using sepal and petal measurements
2. Perform comprehensive data analysis and visualization
3. Identify the most significant features influencing flower species classification
4. Achieve classification accuracy of >90%
5. Provide clear documentation and reproducible results

## Dataset

The project uses the classic Iris dataset (`IRIS.csv`) which includes:
- Sepal length
- Sepal width
- Petal length
- Petal width
- Species (target variable)

## Project Structure

```
iris/
│   README.md
│   IRIS.csv
│   iris_classification.ipynb
│   iris_model.joblib (generated after running)
│   scaler.joblib (generated after running)
```

## Requirements

- Python 3.7+
- Required packages:
  - pandas
  - numpy
  - matplotlib
  - seaborn
  - scikit-learn
  - joblib

## Setup and Installation

1. Clone this repository or download the files
2. Install required packages:
   ```powershell
   pip install pandas numpy matplotlib seaborn scikit-learn joblib
   ```

## Running the Project

1. Open the project in VS Code with Jupyter Notebook extension installed
2. Open `iris_classification.ipynb`
3. Run all cells in sequence (Shift+Enter)

The notebook will:
- Load and analyze the dataset
- Perform data preprocessing
- Train a Random Forest model with optimized parameters
- Evaluate model performance
- Generate visualizations
- Save the trained model

## Key Features

1. **Data Analysis & Visualization**
   - Correlation analysis
   - Feature distribution plots
   - Pair plots for feature relationships

2. **Model Development**
   - Data preprocessing with StandardScaler
   - Hyperparameter optimization using GridSearchCV
   - Feature importance analysis

3. **Model Evaluation**
   - Accuracy metrics
   - Classification report
   - Confusion matrix

## Results

The model achieves high accuracy (>90%) in classifying Iris flowers using the Random Forest algorithm. Feature importance analysis reveals the most significant measurements for species identification.

## Usage Examples

```python
# Load the saved model and scaler
import joblib
model = joblib.load('iris_model.joblib')
scaler = joblib.load('scaler.joblib')

# Example prediction
sample_data = [[5.1, 3.5, 1.4, 0.2]]  # Example measurements
scaled_data = scaler.transform(sample_data)
prediction = model.predict(scaled_data)
print(f"Predicted species: {prediction[0]}")
```

### Making Predictions
To use the trained model for predictions:
1. Ensure both `iris_model.joblib` and `scaler.joblib` are in your working directory
2. Measure the following features of your Iris flower:
   - Sepal length (cm)
   - Sepal width (cm)
   - Petal length (cm)
   - Petal width (cm)
3. Use the code example above to make predictions

## Model Details

The Random Forest Classifier is trained with the following specifications:
- Training/Test split: 80/20
- Cross-validation: 5-fold
- Hyperparameter optimization using GridSearchCV
- Feature scaling using StandardScaler
