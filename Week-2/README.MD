# Data Collection, Cleaning, and Preprocessing for Logistics Analysis

## 📌 Project Overview

This project demonstrates a complete **data collection simulation, data cleaning, and preprocessing pipeline for logistics analysis using Python**.

The objective is to prepare a logistics dataset for reliable downstream analysis by identifying and treating common data-quality problems such as:

* Missing values
* Duplicate records
* Invalid numerical values
* Inconsistent categorical values
* Statistical outliers
* Different numerical feature scales

The project was implemented using **Python in Google Colab** and organized for reproducibility through **GitHub**.

---

## 🎯 Project Objective

The main objective is to simulate a logistics data preprocessing workflow and demonstrate how raw operational data can be transformed into a high-quality analytical dataset.

The project focuses on:

1. Simulating logistics data collection.
2. Inspecting the structure and quality of the dataset.
3. Identifying missing values and invalid observations.
4. Removing duplicate records.
5. Standardizing categorical variables.
6. Detecting and treating numerical outliers.
7. Applying Min-Max normalization.
8. Applying standardization.
9. Validating the final dataset.
10. Exporting the processed datasets for future analysis.

---

## 🗂️ Project Structure

```text
Logistics-Data-Preprocessing/
│
├── data/
│   ├── logistics_raw_issues.csv
│   ├── logistics_cleaned.csv
│   ├── logistics_preprocessed.csv
│   ├── preprocessing_summary.csv
│   └── final_preprocessing_statistics.csv
│
├── figures/
│   ├── missing_values_before_cleaning.png
│   ├── outliers_before_treatment.png
│   └── data_quality_before_after.png
│
├── notebooks/
│   └── Logistics_Data_Preprocessing.ipynb
│
├── reports/
│   └── Logistics_Data_Collection_Cleaning_and_Preprocessing_Report.docx
│
├
└── README.md
```

---

## 📊 Dataset Description

A synthetic logistics dataset was created because the selected public dataset source was not accessible for download.

The baseline dataset contains:

* **1,000 delivery records**
* **16 original columns**

The dataset represents logistics delivery operations and includes information related to:

* Delivery ID
* Delivery date
* Vehicle type
* Origin
* Destination zone
* Distance
* Traffic level
* Weather condition
* Package count
* Vehicle capacity
* Delivery time
* Delivery cost
* Fuel cost
* Load weight
* Customer rating

Controlled data-quality problems were introduced to simulate realistic raw logistics data.

---

## 🔎 Data Quality Issues Identified

The simulated raw dataset contained several quality issues.

| Data Quality Issue            | Observed |
| ----------------------------- | -------: |
| Negative distance values      |        3 |
| Invalid customer ratings      |        3 |
| Non-positive delivery times   |        0 |
| Non-positive delivery costs   |        0 |
| Missing Distance_KM           |       10 |
| Missing Weather_Condition     |       10 |
| Missing Delivery_Time_Minutes |       10 |
| Missing Delivery_Cost_INR     |       10 |
| Missing Customer_Rating       |       10 |
| Duplicate rows                |        4 |

Categorical inconsistencies were also identified.

### Traffic Level

Examples included:

```text
Medium
medium
High
HIGH
Low
low
```

### Weather Condition

Examples included:

```text
Normal
normal
Rain
RAIN
Storm
storm
```

These categories were standardized during preprocessing.

---

## 🧹 Data Cleaning Methodology

### 1. Duplicate Removal

Duplicate rows were identified using pandas and removed from the working dataset.

Four duplicate records were removed.

After treatment:

```text
Remaining duplicates: 0
```

---

### 2. Missing Value Treatment

Missing numerical values were handled using **median imputation**.

The median was selected because it is less affected by extreme values than the mean.

Missing categorical values were handled using the **mode**.

This approach preserved the records while providing reasonable replacement values.

---

### 3. Categorical Standardization

Inconsistent capitalization was standardized using string transformation.

For example:

```text
HIGH → High
medium → Medium
low → Low
RAIN → Rain
normal → Normal
storm → Storm
```

Final traffic categories:

```text
High
Low
Medium
```

Final weather categories:

```text
Normal
Rain
Storm
```

---

### 4. Invalid Value Treatment

Three negative distance values were detected.

Three invalid customer ratings were also detected.

These invalid observations were converted into missing values and subsequently handled through the established imputation process.

Delivery time and delivery cost contained no non-positive values.

---

## 📈 Outlier Detection

The **Interquartile Range (IQR)** method was used to detect statistical outliers.

The calculation was based on:

```text
IQR = Q3 - Q1

Lower Bound = Q1 - 1.5 × IQR

Upper Bound = Q3 + 1.5 × IQR
```

### Detected Outliers

| Variable              | Outlier Count |
| --------------------- | ------------: |
| Distance_KM           |            15 |
| Delivery_Time_Minutes |            10 |
| Delivery_Cost_INR     |             9 |
| Fuel_Cost_INR         |            14 |
| Customer_Rating       |            13 |
| Package_Count         |             0 |
| Load_Weight_KG        |            57 |

---

## 🛠️ Outlier Treatment

The following operational numerical variables were treated using **IQR capping**:

* Distance_KM
* Delivery_Time_Minutes
* Delivery_Cost_INR
* Fuel_Cost_INR
* Load_Weight_KG

Instead of deleting potentially valid logistics observations, extreme values were capped at the calculated IQR boundaries.

Post-treatment validation showed:

```text
Distance_KM: 0 outliers
Delivery_Time_Minutes: 0 outliers
Delivery_Cost_INR: 0 outliers
Fuel_Cost_INR: 0 outliers
Load_Weight_KG: 0 outliers
```

---

## ⚖️ Data Normalization and Standardization

Two numerical transformation techniques were applied.

### Min-Max Scaling

Min-Max scaling transforms numerical values to a common range between 0 and 1.

The following variables were scaled:

```text
Distance_KM
Delivery_Time_Minutes
Delivery_Cost_INR
Fuel_Cost_INR
Load_Weight_KG
```

New columns were created with the suffix:

```text
_MinMax
```

For example:

```text
Distance_KM_MinMax
Delivery_Cost_INR_MinMax
```

---

### Standardization

Standardization converts numerical variables into standardized values based on their mean and standard deviation.

New columns were created with the suffix:

```text
_Standardized
```

For example:

```text
Distance_KM_Standardized
Delivery_Time_Minutes_Standardized
```

The original cleaned variables were preserved to maintain traceability.

---

## ✅ Final Dataset Validation

The final preprocessing validation produced the following results:

| Validation Metric        |        Final Result |
| ------------------------ | ------------------: |
| Final records            |               1,001 |
| Final columns            |                  26 |
| Missing values           |                   0 |
| Duplicate rows           |                   0 |
| Negative distances       |                   0 |
| Invalid customer ratings |                   0 |
| Traffic categories       |   High, Low, Medium |
| Weather categories       | Normal, Rain, Storm |

The final dataset passed the major data-quality checks.

---

## 🔄 Preprocessing Pipeline

The complete workflow can be summarized as:

```text
Data Collection Simulation
          ↓
Initial Data Inspection
          ↓
Data Quality Assessment
          ↓
Duplicate Detection & Removal
          ↓
Missing Value Treatment
          ↓
Categorical Standardization
          ↓
Invalid Value Treatment
          ↓
Outlier Detection using IQR
          ↓
Outlier Treatment using Capping
          ↓
Min-Max Scaling
          ↓
Standardization
          ↓
Final Data Validation
          ↓
CSV Export
```

---

## 📊 Project Visualizations

The project includes visual evidence of the preprocessing process.

### Missing Values Before Cleaning

![Missing Values Before Cleaning](figures/missing_values_before_cleaning.png)

### Outliers Before Treatment

![Outliers Before Treatment](figures/outliers_before_treatment.png)

### Data Quality Before and After Preprocessing

![Data Quality Before and After](figures/data_quality_before_after.png)

---

## 💻 Technologies Used

The project was developed using:

* Python
* Google Colab
* pandas
* NumPy
* Matplotlib
* scikit-learn
* Jupyter Notebook
* Git
* GitHub

---

## 📚 Key Python Techniques

The project demonstrates practical use of:

```python
pandas
```

for:

* Data loading
* Data inspection
* Missing-value handling
* Duplicate detection
* Categorical transformation
* Data validation
* CSV export

It also demonstrates:

```python
sklearn.preprocessing.MinMaxScaler
sklearn.preprocessing.StandardScaler
```

for numerical feature transformation.

---

## 📁 Dataset Files

### `logistics_raw_issues.csv`

Contains the simulated dataset with deliberately introduced data-quality problems.

### `logistics_cleaned.csv`

Contains the dataset after cleaning operations such as missing-value treatment, duplicate removal, categorical standardization, and invalid-value treatment.

### `logistics_preprocessed.csv`

Contains the final processed dataset including normalized and standardized numerical variables.

### `preprocessing_summary.csv`

Contains preprocessing-related summary information.

### `final_preprocessing_statistics.csv`

Contains final dataset validation statistics.

---

## 📄 Report

The detailed academic report is available in:

```text
reports/
└── Logistics_Data_Collection_Cleaning_and_Preprocessing_Report.docx
```

The report explains:

* Dataset collection simulation
* Data-quality problems
* Cleaning methodology
* Missing-value treatment
* Duplicate handling
* Outlier detection
* Outlier treatment
* Normalization
* Standardization
* Validation
* Reflection on data quality
* Python implementation

---

## 🔬 Reflection

Data quality is a critical prerequisite for reliable logistics analytics.

Missing delivery information can affect operational measurements. Duplicate records can artificially increase delivery counts. Inconsistent categorical labels can split the same operational group into multiple categories. Invalid values can create misleading analytical results, while extreme observations can disproportionately influence statistical models.

The preprocessing workflow used in this project provides a systematic approach for reducing these risks before further analytics or machine-learning tasks are performed.

An important consideration is that statistical outliers are not automatically errors. Logistics operations can legitimately contain unusually long distances, large loads, expensive deliveries, or extended delivery times. Therefore, preprocessing decisions should always consider the operational context.

---

## 🚀 Future Improvements

Possible extensions of this project include:

1. Exploratory Data Analysis (EDA).
2. Logistics KPI development.
3. Delivery-time prediction.
4. Delivery-cost prediction.
5. Vehicle utilization analysis.
6. Route optimization.
7. Traffic and weather impact analysis.
8. Feature engineering.
9. Machine-learning model development.
10. Interactive logistics dashboards.

---

## 👨‍💻 Project Workflow

The project was completed through an iterative workflow:

```text
Dataset Simulation
       ↓
Quality Assessment
       ↓
Cleaning
       ↓
Outlier Treatment
       ↓
Normalization
       ↓
Validation
       ↓
Documentation
       ↓
GitHub Submission
```

---

## 📌 Conclusion

This project successfully demonstrates a complete logistics data collection simulation, cleaning, and preprocessing workflow using Python.

The original dataset contained **1,000 records and 16 columns**. After controlled data-quality issues were introduced and subsequently treated, the final validated dataset contained **1,001 records and 26 columns**.

The final validation confirmed:

```text
Missing values       → 0
Duplicate rows       → 0
Negative distances   → 0
Invalid ratings      → 0
```

The resulting dataset provides a structured foundation for future logistics analytics, visualization, predictive modeling, and operational decision-support applications.
