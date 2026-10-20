
# Advanced Logistics Data Analysis and Visualization

## Project Overview

This project focuses on Exploratory Data Analysis (EDA) and visualization of a hypothetical logistics dataset containing 1,000 delivery records. The objective is to analyze logistics performance, identify cost drivers, investigate delivery delays, and generate actionable insights using Python.

The project uses a synthetic dataset to demonstrate how data analytics can support logistics and supply chain decision-making.

## Objectives

- Analyze delivery data using descriptive statistics.
- Examine distributions, central tendency, and variability.
- Investigate delivery time and delivery cost patterns.
- Compare performance across vehicle types, traffic levels, and weather conditions.
- Identify relationships between numerical variables using correlation analysis.
- Evaluate on-time delivery performance and customer ratings.
- Develop data-driven recommendations for logistics improvement.

## Dataset Description

The dataset contains 1,000 synthetic delivery records and 18 original columns.

Key variables include:

- `Delivery_ID`: Unique delivery identifier.
- `Delivery_Date`: Date of delivery.
- `Vehicle_Type`: Bike, Van, or Truck.
- `Origin`: Delivery origin.
- `Destination_Zone`: Destination area category.
- `Distance_KM`: Delivery distance in kilometers.
- `Shipment_Volume`: Shipment volume.
- `Package_Count`: Number of packages.
- `Load_Weight_KG`: Shipment weight in kilograms.
- `Traffic_Level`: Low, Medium, or High.
- `Weather_Condition`: Normal, Rain, or Storm.
- `Delivery_Time_Minutes`: Delivery duration.
- `Delivery_Cost_INR`: Total delivery cost in Indian Rupees.
- `Fuel_Cost_INR`: Fuel cost.
- `Vehicle_Utilization_Percent`: Vehicle utilization percentage.
- `Customer_Rating`: Customer rating.
- `On_Time`: Whether the delivery was on time.
- `Delivery_Status`: Completed or Cancelled.

An additional derived column, `On_Time_Flag`, converts the on-time status into a numeric value for calculating delivery rates.

**Note:** The dataset is synthetic and is intended for educational and analytical purposes only.

## Tools and Technologies

- Python
- Google Colab
- pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook
- GitHub

## Analysis Performed

### 1. Data Quality Assessment
- Checked dataset dimensions and data types.
- Examined missing values and duplicate records.
- Reviewed categorical variable distributions.

### 2. Exploratory Data Analysis
- Calculated mean, median, standard deviation, minimum, and maximum.
- Examined delivery time, delivery cost, and shipment characteristics.
- Compared logistics performance across categories.

### 3. Data Visualization
- Delivery time distribution.
- Delivery cost distribution.
- Average delivery time by vehicle type.
- Delivery time by traffic level.
- Delivery time by weather condition.
- Correlation heatmap.
- On-time delivery rates by vehicle type and weather.

### 4. Correlation Analysis
Investigated relationships among distance, shipment volume, package count, load weight, delivery time, delivery cost, fuel cost, vehicle utilization, and customer rating.

### 5. On-Time Delivery Analysis
Calculated overall on-time performance and compared rates across vehicle types, traffic levels, and weather conditions.

## Key Findings

Based on the reported analysis of the synthetic dataset:

- **Dataset size:** 1,000 records and 18 original columns.
- **Data quality:** Zero missing values and zero duplicate rows were reported.
- **Average delivery time:** 122.23 minutes.
- **Average delivery cost:** INR 363.87.
- **Traffic impact:** Average delivery time was 137.52 minutes under high traffic, compared with 107.57 minutes under low traffic.
- **Weather impact:** Average delivery time was 138.28 minutes during storms, compared with 120.36 minutes in normal weather.
- **Cost relationship:** Fuel cost and delivery cost had a strong positive correlation of 0.97.
- **Distance relationship:** Distance and delivery time had a positive correlation of 0.80.
- **Customer experience:** Delivery time and customer rating had a negative correlation of -0.41.
- **On-time delivery rate:** 12.8% of records were marked on time.
- **Delivery status:** 959 deliveries were completed and 41 were cancelled.

These findings describe patterns in generated data. Correlation does not prove causation, and the results should not be generalized to real logistics operations without validation.

## Recommendations

1. Investigate traffic-aware route planning and dispatch schedules.
2. Include weather-related delivery buffers while prioritizing safety.
3. Monitor fuel costs and delivery costs together.
4. Compare vehicle performance across similar routes and shipment loads.
5. Improve on-time delivery tracking using clearly defined delivery deadlines.
6. Monitor customer ratings alongside delivery time and service reliability.
7. Validate these findings using real operational data before making business decisions.

## Project Structure

```text
Advanced-Logistics-Data-Analysis/
│
├── README.md
├── data
├── notebooks
├── reports
│
└── figures/
    ├── delivery_time_distribution.png
    ├── delivery_cost_distribution.png
    ├── delivery_time_by_vehicle.png
    ├── delivery_time_by_traffic.png
    ├── delivery_time_by_weather.png
    ├── logistics_correlation_heatmap.png
    ├── on_time_rate_by_vehicle.png
    └── on_time_rate_by_weather.png
```


## How to Run the Project

1. Download or clone this repository.
2. Open `Advanced_Logistics_Data_Analysis_and_Visualization.ipynb` in Google Colab or Jupyter Notebook.
3. Upload `advanced_logistics_dataset.csv` if the notebook requires a local CSV file.
4. Run the notebook cells in order.
5. Review the statistical outputs, visualizations, and findings.

Required libraries:

```python
pip install pandas numpy matplotlib seaborn
```

## Deliverables

- Python analysis notebook.
- Synthetic logistics dataset in CSV format.
- Visualizations of logistics performance.
- Word report with findings, recommendations, and code snippets.
- Project documentation.

## Conclusion

This project demonstrates how exploratory data analysis, statistical summaries, data visualization, and correlation analysis can be applied to logistics performance evaluation. It highlights potential areas for further investigation, including delivery delays, fuel costs, route efficiency, vehicle utilization, and customer satisfaction.

The project provides a foundation for future work involving real logistics data, predictive delivery-time models, cost optimization, and operational performance monitoring.

## Author

Created as a data analytics project for educational purposes.