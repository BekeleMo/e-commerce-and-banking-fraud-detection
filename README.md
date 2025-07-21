## 📊 Datasets Used

### 1. Fraud_Data.csv
- **Description**: A comprehensive dataset containing e-commerce transaction logs with fields such as `user_id`, `device_id`, `ip_address`, `purchase_time`, `purchase_value`, `signup_time`, `source`, `browser`, and `age`. This dataset is designed to identify fraudulent activities based on user behavior and transaction patterns.
- **Target Variable**: `class` (1 = Fraudulent transaction, 0 = Legitimate transaction).
- **Size**: [Add approximate rows/columns if known, e.g., 1M rows, 10 columns].
- **Source**: [Specify source if applicable, e.g., synthetic data or public dataset].

### 2. creditcard.csv
- **Description**: A dataset of credit card transactions with PCA-anonymized features (e.g., `V1`, `V2`, ..., `V28`) to protect sensitive information, along with `Time`, `Amount`, and `Class`. Ideal for machine learning models to detect credit card fraud.
- **Target Variable**: `Class` (1 = Fraudulent transaction, 0 = Legitimate transaction).
- **Size**: [e.g., 284,807 rows, 31 columns].
- **Source**: [e.g., Kaggle or internal data].

### 3. IpAddress_to_Country.csv
- **Description**: A lookup table mapping IP address ranges to countries, enabling geolocation-based feature engineering. Includes columns like `lower_bound_ip`, `upper_bound_ip`, and `country`.
- **Size**: [e.g., 100,000+ rows].
- **Source**: [e.g., public IP geolocation database].

---

## 📌 Project Overview: E-commerce and Banking Fraud Detection

This repository contains the initial deliverables for the **Interim-1 submission** as part of a fraud detection project, focusing on **Task 1**: Data Preparation, Exploratory Data Analysis (EDA), and Feature Engineering. The goal is to build a robust foundation for detecting fraudulent transactions in e-commerce and banking systems using machine learning techniques. The project leverages multiple datasets and includes automated testing via GitHub Actions.

---

### 🧼 Task 1.1: Data Cleaning and Preprocessing

- **Duplicate Removal**: Identified and removed duplicate rows using pandas `drop_duplicates()` to ensure data uniqueness.
- **Timestamp Conversion**: Parsed `signup_time` and `purchase_time` into datetime objects with:
  ```python
  df['signup_time'] = pd.to_datetime(df['signup_time'])
  df['purchase_time'] = pd.to_datetime(df['purchase_time'])