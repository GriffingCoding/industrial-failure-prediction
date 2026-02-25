# Predictive Maintenance System (AI4I Dataset)

## Overview
This project uses the AI4I 2020 Predictive Maintenance dataset to explore how machine failure can be predicted using structured data and machine learning. The goal is to build a small end-to-end workflow that mirrors how predictive maintenance could work in a real industrial setting — from raw data to database storage to model evaluation.

Rather than just training a model in a single notebook, this project focuses on organizing the data pipeline clearly and evaluating results in a way that reflects real operational tradeoffs.

## Business Context
Unplanned downtime is expensive in manufacturing environments. Identifying machines at higher risk of failure allows maintenance to be scheduled proactively instead of reactively.

In this dataset, failures are relatively rare (~3–4%), which makes this an imbalanced classification problem. Because missed failures are typically more costly than unnecessary inspections, recall and F1-score are emphasized over raw accuracy.

## Dataset
This project uses the AI4I 2020 Predictive Maintenance Dataset from Kaggle.

The dataset contains simulated industrial sensor data including:
- Air temperature
- Process temperature
- Rotational speed
- Torque
- Tool wear
- Machine failure label

The raw CSV file is not included due to licensing.

To run this project:
1. Download the dataset from Kaggle
2. Place the file at:
data/ai4i2020.csv

## Tech Stack
- Python 3.10.x
- PostgreSQL
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn
- psycopg2

## Project Structure
This project includes:
- Exploratory data analysis
- PostgreSQL schema design
- SQL-based querying and validation
- Feature engineering
- Classification modeling
- Model evaluation with operational metrics

The goal is to simulate a small production-style workflow rather than a one-off notebook experiment.

## Environment Setup (Windows)
Create virtual environment:
py -3.10 -m venv venv
venv\Scripts\activate

Install dependencies:
pip install -r requirements.txt

Launch Jupyter:
jupyter notebook

## Database Setup
Create the database:
CREATE DATABASE predictive_maintenance;

Run schema file:
psql -d predictive_maintenance -f sql/schema.sql

Then import the CSV into PostgreSQL.

## Evaluation Approach
Model performance is evaluated using:
- Confusion Matrix
- Precision
- Recall
- F1-score
- ROC-AUC
- Threshold tuning

The focus is on reducing missed failures while keeping false positives at a reasonable level.

## Current Status
- Environment configured
- Dataset inspection in progress
- Database schema design underway