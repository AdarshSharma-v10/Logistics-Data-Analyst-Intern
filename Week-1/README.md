# Strategic Planning and Data Exploration in Logistics

## Project Overview

This project presents a strategic planning and exploratory data analysis approach for a last-mile logistics operation.

The scenario represents a regional delivery network serving urban, suburban, semi-urban, and rural destinations. The project investigates delivery reliability, delivery time, delivery cost, and vehicle utilization using Python-based data analysis.

The project is designed to demonstrate how logistics data can support operational planning, performance monitoring, and resource allocation.

## Project Objectives

- Define a realistic logistics scenario.
- Identify relevant logistics KPIs.
- Explore delivery performance using a synthetic dataset.
- Compare performance across vehicle types and destination zones.
- Examine the relationship between traffic, weather, delivery time, cost, and customer rating.
- Demonstrate how data science methods could support future logistics planning.
- Develop a strategic roadmap for predictive and optimization-based analysis.

## Dataset

The project uses a synthetic dataset containing 1,000 delivery records and 15 variables.

The dataset includes information such as:

- Delivery date
- Origin
- Destination zone
- Distance
- Traffic level
- Weather condition
- Vehicle type
- Load weight
- Vehicle capacity
- Delivery time
- Delivery cost
- Fuel cost
- Customer rating
- On-time delivery status

The dataset was created for educational and analytical demonstration purposes and does not represent real company data.

## Key Performance Indicators

| KPI | Result |
|---|---:|
| On-Time Delivery Rate | 82.60% |
| Average Delivery Time | 99.56 minutes |
| Average Delivery Cost | ₹196.43 |
| Average Vehicle Utilization | 58.90% |

## Exploratory Analysis

The project examines:

1. Overall logistics KPIs
2. Vehicle performance
3. Destination-zone performance
4. Traffic conditions
5. Weather conditions
6. Distance and delivery cost relationship

### Key Findings

- The overall on-time delivery rate is 82.60%.
- Rural deliveries have the highest average delivery time and cost.
- Rural deliveries average 32.68 km, 135.05 minutes, and ₹251.23.
- High-traffic deliveries average 112.02 minutes compared with 91.56 minutes under low traffic.
- Storm deliveries have the highest average delivery time at 126.46 minutes.
- The correlation between delivery distance and delivery cost is 0.442.
- Truck deliveries have the highest average delivery cost and the lowest average utilization among the three vehicle types.

These findings are exploratory associations and should not be interpreted as proof of causation.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Google Colab
- Jupyter Notebook
- Git
- GitHub

## Project Structure

```text
logistics-strategic-planning/
│
├── data/
│   └── logistics_delivery_data.csv
│
├── figures/
│   └── Project.png
│
├── notebooks/
│   └── Logistics_Strategic_Planning.ipynb
│
├── reports/
│   └── Strategic_Planning_and_Data_Exploration_in_Logistics_Report.docx
│
├── .gitignore
├── README.md
└── requirements.txt