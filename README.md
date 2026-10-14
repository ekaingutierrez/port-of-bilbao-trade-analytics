# Port of Bilbao: International Trade Analytics & Macroeconomic Modeling

## Project Overview

This repository contains a comprehensive Data Engineering and Machine Learning pipeline designed to analyze international trade flows (imports and exports) between Spain/Euskadi and the Netherlands, focusing specifically on the Port of Bilbao.

By integrating customs records (DataComex), port activity data, and World Bank macroeconomic indicators, this project maps hierarchical trade dependencies and applies predictive modeling to understand how global economic shifts impact localized port traffic across key TARIC chapters (Minerals, Chemicals, and Steel).

A key business finding of this analysis is the empirical demonstration of the Hinterland Effect, proving the port's logistical absorption of the industrial output from neighboring autonomous communities, which justifies its regional volume exceeding the local Basque Country export capacity.

## Data Confidentiality Notice

The datasets used in this project are not included in this repository. 
Due to the sensitive nature of the customs records and port activity logs, all raw data files (.csv, .xlsx) have been strictly excluded via .gitignore to comply with data privacy standards. 
Note: To execute the pipeline locally, users must provide their own structured dataset and place it within a local /data directory.

## Tech Stack & Libraries

* Language: Python 3.10+, SQL
* Data Processing: Pandas, NumPy
* Machine Learning: Scikit-Learn (Linear Regression, Support Vector Classification - SVC, GridSearchCV, RobustScaler)
* Visualization: Matplotlib, Seaborn
* Database Architecture: Relational SQL schema design (DDL/DML)

## Methodology & Technical Pipeline

### 1. Data Engineering & SQL Architecture (/sql & /data)
* Extracted and consolidated raw trade data from diverse sources (CSV, Excel) tracking goods by ISO country codes and TARIC commodity chapters.
* Designed a normalized relational database schema mapping COUNTRIES, PORTS, EXPORTS, and IMPORTS to ensure data integrity and facilitate business intelligence querying.

### 2. Exploratory Data Analysis & Trade Profiling (01_ to 07_ notebooks)
* Performed comparative volume analysis filtering by specific high-impact TARIC codes (25, 27, 29, 72).
* Mapped hierarchical trade dependencies to evaluate the strategic importance of the Port of Bilbao within both the regional (Euskadi) and national (Spain) logistics frameworks, identifying its vast Hinterland capacity.

### 3. Macroeconomic Correlation (08_macro_correlation_analysis.ipynb)
* Merged historic trade tonnage with World Bank datasets containing +20 global indicators.
* Generated correlation matrices (heatmaps) to identify which specific macroeconomic variables (e.g., Population Growth, High-tech exports, Commercial service exports) strictly influence physical maritime freight weight.

### 4. Predictive Modeling (09_ to 11_ notebooks)
* Regression: Trained and evaluated Linear Regression models to forecast import/export volumes utilizing RobustScaler to prevent distortion from structural macroeconomic outliers.
* Classification: Formulated a target variable to determine year-over-year activity growth. Implemented a Support Vector Classifier (SVC), optimizing the C hyperparameter via GridSearchCV (5-fold cross-validation) to maximize predictive recall and classify commercial expansion periods.

## How to Run the Project

1. Clone the repository:
   git clone https://github.com/ekaingutierrez/port-of-bilbao-trade-analytics.git

2. Install dependencies:
   pip install -r requirements.txt

3. Run the analytical notebooks sequentially from 01 to 11 located in the /notebooks folder.
