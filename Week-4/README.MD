# Predictive Modeling and Optimization in Logistics Systems

## Project Overview

This project applies machine learning techniques to predict delivery durations and demonstrate dispatch-time optimization in logistics systems. It uses a synthetic logistics dataset to analyze how factors such as distance, package count, shipment weight, traffic, weather, and dispatch time influence delivery duration.

The project compares multiple regression models, evaluates their predictive performance, and implements a simple optimization simulation to identify dispatch times associated with lower predicted delivery durations.

## Objectives

- Generate and analyze a logistics dataset.
- Perform data inspection and preprocessing.
- Predict delivery duration using regression models.
- Compare model performance using standard evaluation metrics.
- Apply cross-validation and hyperparameter tuning.
- Simulate dispatch-time optimization using model predictions.
- Visualize results and export performance tables for reporting.

## Dataset Description

The project uses a **synthetic dataset containing 1,500 records and 12 columns**, including 11 input features and one target variable.

| Feature | Description |
|---|---|
| `Distance_KM` | Delivery distance in kilometers |
| `Package_Count` | Number of packages in the shipment |
| `Load_Weight_KG` | Total shipment weight |
| `Shipment_Volume` | Shipment volume |
| `Vehicle_Type` | Type of delivery vehicle |
| `Traffic_Level` | Traffic conditions |
| `Weather_Condition` | Weather during delivery |
| `Destination_Zone` | Destination area or zone |
| `Dispatch_Hour` | Hour of dispatch |
| `Day_of_Week` | Day of the week |
| `Rush_Hour` | Indicator for rush-hour conditions |
| `Delivery_Time_Minutes` | Target variable: delivery duration in minutes |

**Note:** Because the dataset is synthetic, its patterns and results should not be interpreted as verified real-world logistics performance.

## Technologies Used

- Python
- Google Colab
- Pandas
- NumPy
- Scikit-learn

## Machine Learning Workflow

1. **Data generation and inspection**  
   Create the synthetic dataset and inspect its structure, summary statistics, missing values, and duplicate records.

2. **Data preprocessing**  
   Separate input features from the target variable. Standardize numerical features and one-hot encode categorical features using a `ColumnTransformer` and `Pipeline`.

3. **Train-test split**  
   Split the data into training and testing sets using an 80:20 ratio and `random_state=42`.

4. **Model training and comparison**  
   Evaluate Linear Regression, Random Forest Regression, and a mean-prediction baseline.

5. **Cross-validation**  
   Compare regression models using five-fold cross-validation.

6. **Hyperparameter tuning**  
   Use `GridSearchCV` to tune Ridge Regression's regularization parameter (`alpha`).

7. **Model evaluation**  
   Evaluate the selected model using Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and the coefficient of determination (R²).

8. **Dispatch-time optimization**  
   Evaluate candidate dispatch hours from 06:00 to 22:00 for 20 test deliveries and compare predicted delivery durations.

9. **Visualization and export**  
   Generate charts and export model-comparison, cross-validation, and dispatch-optimization results as CSV files.

## Model Performance

The final test-set results are summarized below.

| Model | MAE (minutes) | RMSE (minutes) | R² |
|---|---:|---:|---:|
| Ridge Regression | 5.796 | 7.493 | 0.9549 |
| Linear Regression | 5.798 | 7.496 | 0.9548 |
| Random Forest Regression | 8.89 | 11.29 | 0.8976 |
| Mean Baseline | 28.87 | 35.53 | -0.0148 |

The tuned Ridge Regression model achieved the best final test performance, although its improvement over Linear Regression was negligible.

**Interpretation:** The Ridge model's test-set predictions had an MAE of approximately 5.80 minutes. The R² value of approximately 0.955 indicates that the model explained about 95.5% of the target variance in this synthetic test dataset.

## Dispatch-Time Optimization

The optimization simulation evaluates alternative dispatch hours and selects the hour associated with the lowest predicted delivery duration for each selected delivery.

### Simulation Results

- Deliveries evaluated: 20
- Candidate dispatch hours: 06:00–22:00
- Selected dispatch hour in the reported run: 06:00 for all 20 deliveries
- Average predicted time saving: approximately 4.45 minutes per delivery
- Deliveries with a positive predicted improvement: 20 out of 20

These results demonstrate how predictive models can support scheduling decisions under defined assumptions.

**Important limitation:** The dataset is synthetic, and the simulation changes dispatch time without fully modeling operational constraints such as vehicle availability, delivery time windows, driver schedules, depot operating hours, route dependencies, or vehicle capacity. Therefore, the results are illustrative and do not establish that 06:00 is universally the optimal dispatch time.

## Visualizations

The project generates the following charts:

1. **Model Performance Comparison** — compares regression models using evaluation metrics.
2. **Actual vs. Predicted Delivery Time** — illustrates the relationship between actual and predicted delivery durations.
3. **Dispatch Optimization Savings** — shows estimated delivery-time improvements from the dispatch-time simulation.

## Output Files

The notebook exports the following CSV files:

| File | Description |
|---|---|
| `initial_model_comparison.csv` | Initial model evaluation results |
| `cross_validation_results.csv` | Cross-validation performance |
| `final_test_model_comparison.csv` | Final test-set model metrics |
| `dispatch_optimization_results.csv` | Dispatch-time optimization results |

Save the generated chart images in a project folder such as `images/` before adding them to the GitHub repository.

## How to Run the Project

### Option 1: Google Colab

1. Open the project notebook in Google Colab.
2. Run the notebook cells in order.
3. Allow the dataset generation, preprocessing, training, evaluation, and optimization steps to finish.
4. Review the printed metrics and visualizations.
5. Download the generated CSV files and chart images.
6. Upload the notebook and required outputs to your GitHub repository.

## Suggested Repository Structure

```text
predictive-modeling-logistics/
├── README.md
├── logistics_prediction.ipynb
├── images/
│   ├── model_performance_comparison.png
│   ├── actual_vs_predicted.png
│   └── dispatch_optimization_savings.png
└── results/
    ├── initial_model_comparison.csv
    ├── cross_validation_results.csv
    ├── final_test_model_comparison.csv
    └── dispatch_optimization_results.csv
```

Adjust filenames and folders to match the files you actually upload.

## Limitations

- The dataset is synthetically generated rather than collected from a real logistics operation.
- Model performance may be influenced by patterns deliberately incorporated into the data-generation process.
- Dispatch optimization is based on predicted delivery duration and does not account for all real operational constraints.
- The reported metrics are specific to the generated dataset and the stated train-test split.
- Further validation using real delivery records is necessary before practical deployment.


## Conclusion

This project demonstrates an end-to-end machine learning workflow for delivery-time prediction and a basic dispatch-time optimization simulation. Ridge Regression achieved strong predictive performance on the synthetic test dataset, while the optimization experiment illustrated how predictions can inform scheduling decisions.

The project provides a foundation for exploring data-driven logistics planning, with real-world deployment requiring actual operational data and more comprehensive optimization constraints.

## Author

**Your Name**  
[GitHub Profile](https://github.com/your-username)
