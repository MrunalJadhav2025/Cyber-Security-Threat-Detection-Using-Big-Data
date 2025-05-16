Cyber Security Threat Detection Using Big Data

This project was developed for the course DATA 603: Platforms for Big Data Processing. It focuses on detecting cybersecurity threats in IoT environments using scalable big data tools and machine learning models.


Project Description

With the rapid growth of IoT devices, cybersecurity threats have become more sophisticated and frequent. This project uses a large-scale, real-time network traffic dataset (CICIoT2023) to build a multi-class threat detection system. The goal is to classify network traffic as normal or as one of several attack types using big data tools.


Dataset

Name: CICIoT2023

Dataset Link: "https://www.unb.ca/cic/datasets/iotdataset-2023.html"

Size: Approximately 712,000 rows and 40 features

Description: Collected from an IoT topology with 105 devices under both normal and attack scenarios

Attack Types: 33 attacks categorized into 7 groups (DDoS, DoS, Recon, Web-based, Brute Force, Spoofing, Mirai)


Preprocessing

All data preprocessing was performed in Python. The steps included:

Dropping missing and infinite values

Label encoding for categorical variables

Standardizing numerical features

Removing outliers using Z-score

Removing duplicate records

Filtering out extremely rare classes (less than 6 samples)

Balancing the dataset using SMOTE

Saving the final processed dataset as a Parquet file for efficient use in Spark


Feature Engineering

VarianceThreshold to remove low-variance features

Manual removal of redundant features based on domain knowledge

Feature importance analysis using RandomForestClassifier

Final feature set includes 21 selected features


Modeling

Model training and evaluation were performed using both PySpark and Python:

Logistic Regression (PySpark): Accuracy = 53.5 percent

Random Forest (PySpark): Accuracy = 75.2 percent

XGBoost (Python): Accuracy = 86.8 percent

All models were trained on the SMOTE-balanced dataset. XGBoost was trained on a 10 percent sample due to memory constraints.


Technologies Used

Python (Pandas, Scikit-learn, Seaborn, Matplotlib, Imbalanced-learn)

Apache Spark (PySpark)

XGBoost

Google Colaboratory

Parquet file format for optimized data storage


How to Run

Clone this repository

Run the preprocessing notebook to clean and prepare the dataset

Save the final data to a .parquet file

Load the .parquet file into the modeling notebook and run the model training cells

Evaluate and compare model performance
