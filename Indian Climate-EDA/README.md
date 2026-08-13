# Exploratory Data Analysis (EDA): Indian Climate 2025

## Project Overview

This project performs an **Exploratory Data Analysis (EDA)** on the `Indianclimate.csv` dataset sourced from Kaggle. The objective is to understand climate variations across major Indian cities and identify patterns and relationships between **temperature, humidity, rainfall, wind speed, pressure, cloud cover, and Air Quality Index (AQI)**.

The project follows an end-to-end data analysis workflow, including data inspection, missing value handling, duplicate removal, outlier detection, descriptive statistics, data transformation, visualization, probability analysis, K-Means clustering, and interactive dashboard development.

---

## Objectives

* Understand and explore the Indian climate dataset.
* Inspect dataset structure and data types.
* Handle missing values and duplicate records.
* Detect and handle outliers using the IQR method.
* Calculate descriptive statistics.
* Transform numerical features using normalization and standardization.
* Analyze relationships between climate variables.
* Visualize climate and AQI patterns.
* Perform probability analysis.
* Apply K-Means clustering to identify climate patterns.
* Develop an interactive dashboard for city-wise climate analysis.

---

## Technologies Used

* Python 3.x
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Dash
* Plotly
* Jupyter Notebook

---

## Dataset

**Dataset Name:** `Indianclimate.csv`

**Source:** Kaggle

### Dataset Description

The dataset contains climate and air quality information collected from different cities across India.

### Dataset Variables

#### Numerical Features

* Temperature_Max (°C)
* Temperature_Min (°C)
* Temperature_Avg (°C)
* Humidity (%)
* Rainfall (mm)
* Wind_Speed (km/h)
* AQI
* Pressure (hPa)
* Cloud_Cover (%)

#### Categorical Features

* City
* State
* AQI_Category

#### Temporal Feature

* Date

---

## Project Workflow

### 1. Understand the Problem and Data

The main objective is to analyze climate variations across major Indian cities and understand relationships between weather conditions and air quality.

The analysis focuses on:

* Temperature
* Humidity
* Rainfall
* Wind Speed
* AQI
* Pressure
* Cloud Cover

---

## 2. Import and Inspect the Data

**File:** `import_data.py`

The dataset is loaded into a Pandas DataFrame using `read_csv()`.

The dataset is inspected using:

* `head()` – Displays the first five records.
* `info()` – Displays column names, data types, and non-null values.
* Dataset shape – Identifies the number of rows and columns.

This step helps understand the structure and quality of the dataset before preprocessing.

---

## 3. Handling Missing Values and Outliers

**File:** `handling_missing_value.py`

### 3.1 Missing Value Detection

Missing values were identified using:

```python
isnull().sum()
```

The analysis identified:

* `Temperature_Max (°C)` – 2 missing values
* `Temperature_Min (°C)` – 3 missing values

Other major climate variables did not contain missing values.

### 3.2 Mean Imputation

The missing numerical values were replaced using the **mean** of their respective columns.

This maintains the original dataset size while providing reasonable values for the missing observations.

### 3.3 Duplicate Removal

Duplicate records were checked using:

```python
drop_duplicates()
```

No duplicate records were identified during the analysis.

### 3.4 Outlier Handling

Outliers were identified using the **Interquartile Range (IQR)** method.

The IQR method uses:

```text
IQR = Q3 - Q1

Lower Bound = Q1 - 1.5 × IQR
Upper Bound = Q3 + 1.5 × IQR
```

`Rainfall (mm)` contained a significant number of extreme values. These outliers were removed for the analysis to reduce the influence of extreme rainfall events.

The cleaned dataset was saved as:

```text
cleaned_dataset.csv
```

---

## 4. Explore Data Characteristics

**File:** `descriptive_stats.py`

Descriptive statistics were calculated for the numerical features.

The analysis includes:

* Mean
* Median
* Mode
* Standard Deviation
* Minimum
* Maximum

### Key Statistics

| Variable        |        Mean |
| --------------- | ----------: |
| Temperature_Max |     35.01°C |
| Temperature_Min |     25.08°C |
| Temperature_Avg |     30.05°C |
| Humidity        |      62.69% |
| Rainfall        |     1.71 mm |
| Wind Speed      |  13.54 km/h |
| AQI             |      193.97 |
| Pressure        | 1007.36 hPa |
| Cloud Cover     |      52.66% |

The statistics provide an overview of the typical climate conditions and variability across the dataset.

---

## 5. Data Transformation

**File:** `data_transformation.py`

Data transformation was performed to bring numerical features to comparable scales, especially for distance-based algorithms such as K-Means.

### 5.1 Min-Max Normalization

`MinMaxScaler` transforms numerical values into the range **0 to 1**.

```python
from sklearn.preprocessing import MinMaxScaler
```

### 5.2 Z-Score Standardization

`StandardScaler` transforms numerical features so that they have approximately:

```text
Mean = 0
Standard Deviation = 1
```

```python
from sklearn.preprocessing import StandardScaler
```

Standardization was used before applying K-Means clustering.

---

## 6. Data Visualization

**Files:**

* `basic_visualizations.py`
* `advanced_visualizations.py`

Visualization was performed to understand distributions, trends, relationships, and patterns in the climate data.

### 6.1 Univariate Analysis

Univariate analysis examines one variable at a time.

Visualizations include:

* **Histogram** – Shows the distribution of AQI and temperature values.
* **Line Plot** – Shows trends in climate variables.
* **Bar Chart** – Compares values across selected observations.

### 6.2 Multivariate Analysis

Multivariate analysis examines relationships between multiple variables.

Visualizations include:

* **Pair Plot** – Shows relationships among numerical features.
* **Correlation Heatmap** – Displays the strength and direction of relationships.
* **Covariance Heatmap** – Shows how numerical variables vary together.

---

## 7. Probability Analysis

**File:** `probability_analysis.py`

Probability analysis was performed to understand the distribution and variability of important climate variables.

The analysis includes:

* Range calculation
* Variance calculation
* Histograms
* KDE curves
* Probability distribution analysis

This helps understand the spread and distribution of climate and AQI values.

---

## 8. K-Means Clustering

**File:** `kmeans_modeling.py`

K-Means clustering was applied to the standardized numerical dataset to identify groups with similar climate characteristics.

### Model

**Algorithm:** K-Means Clustering

**Type:** Unsupervised Learning

**Number of Clusters:** 3

```python
from sklearn.cluster import KMeans

model = KMeans(n_clusters=3)
```

The clustering process groups climate records based on similarities in their numerical characteristics.

### Cluster Visualization

The clusters were visualized using:

* Scatter plots
* Pair plots

These visualizations help identify differences between the generated climate groups.

### Cluster Interpretation

Cluster-wise mean values were calculated to understand the environmental characteristics of each cluster.

This helps identify different climate patterns or environmental behavior within the dataset.

---

## 9. Interactive Dashboard

**File:** `dashboard.py`

An interactive **Dash-based web dashboard** was developed to make the climate analysis easier to explore.

### Dashboard Features

#### City Dropdown

Users can select a specific city to filter the climate records.

#### Trend Analysis

Interactive line charts display the trends of:

* Temperature
* Rainfall
* AQI

over time for the selected city.

The dashboard provides an easy way to explore city-wise climate and air quality patterns.

---

## Features

* Complete EDA workflow.
* Missing value detection and imputation.
* Duplicate detection.
* Outlier detection using IQR.
* Descriptive statistical analysis.
* Min-Max normalization.
* Z-score standardization.
* Univariate and multivariate visualization.
* Correlation and covariance analysis.
* Probability distribution analysis.
* K-Means clustering.
* Cluster visualization and interpretation.
* Interactive city-wise climate dashboard.

---

## Output

The project produces:

* Cleaned climate dataset.
* Descriptive statistics.
* Climate distribution plots.
* Correlation heatmaps.
* Covariance heatmaps.
* Pair plots.
* Probability distribution plots.
* K-Means cluster visualizations.
* Cluster-wise analysis.
* Interactive climate dashboard.

---

## Project Structure

```text
Indian Climate 2025 - EDA/
│
├── Indianclimate.csv
├── cleaned_dataset.csv
│
├── import_data.py
├── handling_missing_value.py
├── descriptive_stats.py
├── data_transformation.py
├── basic_visualizations.py
├── advanced_visualizations.py
├── probability_analysis.py
├── kmeans_modeling.py
├── dashboard.py
│
└── README.md
```

---

## How to Run

### 1. Download or Clone the Project

Download or clone the project repository to your computer.

### 2. Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn dash plotly
```

### 3. Run the Python Files

Run the scripts sequentially according to the analysis workflow.

For example:

```bash
python import_data.py
```

```bash
python handling_missing_value.py
```

```bash
python descriptive_stats.py
```

```bash
python data_transformation.py
```

```bash
python basic_visualizations.py
```

```bash
python advanced_visualizations.py
```

```bash
python probability_analysis.py
```

```bash
python kmeans_modeling.py
```

### 4. Run the Dashboard

```bash
python dashboard.py
```

Open the displayed local Dash application in a web browser to interact with the climate dashboard.

---

## Conclusion

This project successfully performs an end-to-end **Exploratory Data Analysis of the Indian Climate 2025 dataset**. The dataset was cleaned by handling missing values, removing duplicate records, and identifying outliers. Descriptive statistics and visualizations were used to understand temperature, humidity, rainfall, wind speed, and AQI patterns.

Data transformation techniques were applied to prepare the numerical features for analysis and clustering. **K-Means clustering** identified distinct groups of climate records with different environmental characteristics, while the interactive dashboard enabled city-wise exploration of climate and AQI trends.

Overall, the project demonstrates how **EDA, data visualization, statistical analysis, data transformation, clustering, and interactive dashboards** can be combined to derive meaningful insights from climate data.
