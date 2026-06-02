# CitiBike Big Data Analysis 🚲

A large-scale Big Data engineering and machine learning project that processes 
NYC Citi Bike trip data using Apache Spark to analyze rider behavior, trip 
patterns, and predict rider gender.

## 🎓 Academic Information

- **Institution:** German International University (GIU)
- **Course:** Big Data & NoSQL Databases, Spring 2026
- **Instructor:** Dr. Nada Sharaf

## 📋 Project Overview

This project simulates the role of a lead big data engineer for a city planning 
agency in New York. Using historical Citi Bike trip data, the pipeline cleans, 
engineers, analyzes, and builds predictive models to understand who is using 
the system and provide recommendations for station expansions.

## ⚙️ Data Engineering

- Spark session setup and large-scale CSV ingestion
- Data cleaning: NULL handling, implicit missing values, noise flagging
- Feature engineering using Spark UDFs:
  - Rider Age (derived from Year of Birth)
  - Trip Duration (seconds)
  - Trip Distance (Haversine formula)
  - Trip Speed (km/h)
  - Period of Day (Morning / Afternoon / Evening / Night)
  - Start Month
  - Season (Winter / Spring / Summer / Autumn)
  - Age Group (Young / Adult / Senior)

### Noise Flagging Rules
- Trip duration < 60 seconds
- Trip speed > 40 km/h (system glitch)
- Rider age > 100 or < 12 years
- Missing Start Station, End Station, or Bike ID

## 📊 Analytical Queries

| # | Query |
|---|-------|
| a | Round trip percentage per user type |
| b | Most popular start stations by usage rank |
| c | Rush hour demand analysis |
| d | Trip duration variation across age groups |
| e | Seasonal bike usage and trip behavior trends |
| f | Over-utilized bikes needing maintenance |
| g | Subscriber vs customer geographic mobility patterns |
| h | Top station pairs by trip demand |
| i | Gender-based riding behavior (speed & duration) |
| j | Weekday vs weekend trip comparison |

## 🤖 Machine Learning (SparkML)

**Task:** Predict rider gender using trip features

**Features used:**
- Numeric: Trip_Duration_Seconds, Trip_Distance_KM, Trip_Speed_KMH, Age, Start_Month
- Categorical: Period_of_Day, user_type, Season

**Model Results:**

| Model | Accuracy | F1 Score | Precision | Recall |
|-------|----------|----------|-----------|--------|
| Logistic Regression | 0.5951 | 0.6188 | 0.6780 | 0.5951 |
| Decision Tree | 0.5830 | 0.6081 | 0.6852 | 0.5830 |
| Random Forest | 0.5841 | 0.6092 | 0.6883 | 0.5841 |

**Best model:** Logistic Regression (F1 = 0.6188)

**Most influential feature:** Trip Speed (importance = 0.5277)

## 🛠️ Tech Stack

- Python
- Apache Spark (PySpark)
- SparkML
- Pandas

## 📁 Dataset

NYC Citi Bike trip data — loaded directly from shared drive.

**Key columns:**
- bike_id, starttime, stoptime
- start/end station name, ID, lat, longitude
- gender (0=Unknown, 1=Male, 2=Female)
- user_type (Subscriber / Customer)

## 🚀 Getting Started

```bash
# Install dependencies
pip install pyspark pandas

# Open the notebook
jupyter notebook notebook8a07de7b3e.ipynb
```

## 👥 Team Members

- Ahmed Rashed
- (add teammates here)
