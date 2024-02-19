# Forecasting COVID-19 and Interactive Dashboard

This repository contains a comprehensive project aimed at forecasting COVID-19 metrics and visualizing the data through an interactive dashboard. The project involves data warehousing with Google BigQuery, exploratory data analysis (EDA), feature engineering, model forecasting, and dashboard development with Dash.

## Project Components

- **Data Warehousing with BigQuery**: Utilizes Google BigQuery for storing and querying COVID-19 datasets from various sources, facilitating efficient data handling and scalable analysis.
- **Forecasting COVID-19.ipynb**: A Jupyter Notebook detailing the data preparation, EDA, feature engineering, and modeling process to forecast COVID-19 metrics.
- **Dashboard.ipynb**: A Jupyter Notebook hosting the interactive dashboard built with Dash, highlighting COVID-19 trends and predictions.

## Methodology

The forecasting process involves several key steps:
1. **Data Preprocessing**: Cleaning and preparing the data for analysis, including handling missing values and normalizing data. Additionally, a `latlong_data.json` file was created to fill in missing location data.
2. **EDA**: Visualizing the different relationships between the variables of the data. 
2. **Feature Engineering**: Creating new features from existing data to improve model predictions. This includes rolling averages, lag features, and growth rates.
3. **Model Training and Evaluation**: Training the models on a subset of the data and evaluating their performance using metrics such as Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R-squared (R2).
4. **Model Selection**: Comparing the models based on their performance metrics to select the best performing model for each COVID-19 metric.

## Data Sources and Preparation

- **Original Datasets**:
  - Johns Hopkins University (JHU) COVID-19 Data: [JHU CSSE COVID-19 Dataset](https://github.com/CSSEGISandData/COVID-19)
  - Our World in Data (OWID) COVID-19 Data: [OWID COVID-19 Data](https://github.com/owid/covid-19-data)
  
- **Data Warehousing**: 
  - The original datasets were renamed to `jhu_time_series_data` and `owid_covid_data` and uploaded to Google BigQuery. A `config.json` file specifies the Google Cloud project ID and dataset/table names for structured organization and access within BigQuery.

  - Data from both sources was merged in the notebook, then warehoused back in BigQuery as `merged_covid_data` for future use.
  - The merged dataset was also saved locally as `merged_dataset_01.csv` through `merged_dataset_04.csv`, with `merged_dataset_03.csv` being specifically used for interactive visualizations in the dashboard.

## Visualizations and Models

- **EDA Outputs**: Stored in `/eda_outputs`, including graphics generated during the EDA process.
- **Models**: The `/models` directory contains the best model selected after evaluation, used for forecasting COVID-19 metrics.



## Interactive Dashboard

Utilizing `merged_dataset_03.csv`, the dashboard offers an interactive way to explore data on COVID-19 metrics across various locations and time frames. Developed using Dash, it can be run locally or deployed for wider access.

## Setup and Installation

### Conda Environment (Recommended for Local Development)

To create a Conda environment with all the necessary packages, use the provided `environment.yml` file and run `conda env create -f environment.yml`:

### Requirements.txt (For Colab and Other Environments)
- Alternatively, you can use pip to install dependencies from the provided `requirements.txt` file:

### Running the Notebooks
- Ensure Jupyter Notebook or JupyterLab is installed.
- Start with `Forecasting COVID-19.ipynb` for data analysis and model forecasting.
- Proceed to `Dashboard.ipynb` to view and interact with the visualization dashboard.

### Dashboard Deployment

- Instructions for running the Dash app locally or deploying it are included within `Dashboard.ipynb`.
