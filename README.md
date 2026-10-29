# Gold Recovery Prediction

Machine learning project focused on predicting gold recovery during mineral processing using regression models, cross-validation, and the sMAPE evaluation metric.

## Project Overview

The objective of this project is to build a machine learning model capable of predicting gold recovery during different stages of the extraction and purification process.

Two target variables are predicted:

- `rougher.output.recovery`
- `final.output.recovery`

The final model is evaluated using a weighted symmetric mean absolute percentage error (sMAPE).

## Dataset

The project uses three datasets:

- `gold_recovery_train.csv` — training data.
- `gold_recovery_test.csv` — test data.
- `gold_recovery_full.csv` — complete dataset containing all available features and targets.

The data contains measurements from different stages of the mineral processing pipeline, including flotation and purification.

## Project Workflow

The analysis follows these main steps:

1. Data loading and inspection.
2. Validation of the recovery calculation.
3. Analysis of features unavailable in the test dataset.
4. Missing value treatment.
5. Analysis of metal concentrations across processing stages.
6. Comparison of feed particle size distributions.
7. Detection of anomalous concentration values.
8. Implementation of the sMAPE evaluation metric.
9. Model comparison using cross-validation.
10. Final model evaluation on the test dataset.

## Exploratory Analysis

The analysis showed that:

- Gold concentration increases significantly through the purification process.
- Silver concentration initially increases during flotation and later decreases.
- Lead concentration increases progressively through the process.
- Train and test particle-size distributions are sufficiently similar for model evaluation.
- Abnormal observations with total concentrations equal to zero were identified during the analysis.

## Models Evaluated

The following regression models were compared:

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- Dummy Regressor as a baseline

Model quality was evaluated using cross-validation and the project-specific weighted sMAPE metric.

## Model Performance

The best cross-validation result was obtained with:

**Random Forest Regressor**

Configuration:

```python
RandomForestRegressor(
    n_estimators=10,
    max_depth=3,
    random_state=12345
)