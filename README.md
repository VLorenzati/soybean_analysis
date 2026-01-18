# Soybean Production Stability Analysis in Argentina

## Project Overview

This project analyzes the historical soybean production in Argentina with the goal of identifying regional production stability profiles, going beyond traditional average yield metrics.

The analysis combines advanced data cleaning, relational database modeling, risk-oriented feature engineering, and unsupervised machine learning, with the final results integrated into interactive Tableau dashboards.

## Objective
To identify regions with different productive risk profiles, considering not only how much they produce, but how stable and predictable that production has been over time.

This approach provides a more realistic view of agricultural performance, especially for decision-making contexts such as planning, investment, or risk assessment.

## Methodology

The project follows an end-to-end data analysis pipeline:



### **1. Data Cleaning & Agronomic Validation**

• Detection and removal of logical inconsistencies (harvested area greater than planted area)

• Filtering of biologically implausible yields (greater than 20 tons per hectare)

• Standardization of variables across the full historical series


### **2. Data Persistence & Modeling**

• Transition from a flat CSV file to a relational database (SQLite)

• Normalized schema including:
  -  Dimension tables: provinces, departments
  -  Fact table: production

• This step ensures data integrity and scalability for analytical queries

### **3. Risk-Oriented Feature Engineering**

Instead of relying only on average yield, multiple stability and risk metrics were computed:

• Average yield

• Coefficient of Variation (CV)

• Interannual yield volatility

• Frequency of production failures

These features aim to capture production reliability, not just performance.

### **4. Unsupervised Clustering**

• Algorithm: K-Means

• Optimal number of clusters (k = 3) selected based on:
  - Elbow Method
  - Silhouette Score

The clustering process groups regions according to their productive stability patterns.


### **5. Visualization & Storytelling**

• Analytical results were integrated into Tableau dashboards

• Visual exploration includes temporal trends, geographic patterns, and comparative risk profiles

 
 
### *A detailed explanation of each stage is available in the whitepaper.*

## Key Insights

• A very high correlation (0.9816) was found between harvested area and total production, indicating that production volume is primarily driven by scale rather than yield efficiency.

• Three distinct production profiles were identified:
  1. High Stability / High Yield
  2. Medium Stability / Structurally Low Yield
  3. Low Stability / High Productive Risk

These profiles reveal structural differences that are not visible when using average yield alone.

### *Full interpretation and decision implications are discussed in the whitepaper*

## Dashboards

The Tableau dashboards allow users to:
  - Explore long-term production trends
  - Compare stability and risk across regions
  - Analyze the relationship between yield, volatility, and production scale

## Limitations

• The analysis does not include climate, soil, or technological variables.

• Results describe historical patterns and should not be interpreted as causal predictions.

• Future work could integrate climatic data to enhance explanatory power.

## Whitepaper
This project includes a technical whitepaper that provides an in-depth explanation of the methodology, analytical decisions, and strategic interpretation of results.

**File:** `whitepaper/Soybean_Production_Stability_Argentina_Whitepaper.pdf`

## Project Structure

| Folder / File      | Description                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| `data/`            | Raw and cleaned soybean production datasets                                  |
| `notebooks/`       | Jupyter notebooks following the logical analysis workflow                     |
| `database/`        | SQLite database with normalized relational schema                             |
| `visualizations/`  | Tableau packaged workbook (`.twbx`), dashboard previews, and PDF outputs     |
| `outputs/`         | Final datasets used for clustering results and Tableau integration            |
| `whitepaper/`      | Detailed methodological and strategic analysis                                |
| `README.md`        | Project documentation and methodological overview                             |

*Author: Valentino Lorenzati*
