# Real Estate Analysis
![Python](https://img.shields.io/badge/Python-3.8-blueviolet)
![SQL](https://img.shields.io/badge/SQL-red)
![FLAML](https://img.shields.io/badge/FLAML-blue)
## Introduction

The purpose of this project is to make an analysis about the real estate market in 10 of the main cities in the USA, for this we have created the dataset extracting data from the website www.trulia.com. 
```
.
└── Real Estate Analysis
    ├── Data Extraction
    ├── Data Cleaning
    ├── Data Analysis
    └── Regression Model
```
## Data Extraction
All data used for this analysis was extracted from www.trulia.com, using the beautifulsoup and requests libraries.

Only the last 1000 records from the following cities were selected:

- Albuquerque
- Colorado
- Indianapolis
- Las Vegas
- Miami
- New York
- Philadelphia
- San Diego
- San Francisco
- Washington, D.C.

Each dataset consists of the following columns:
- Address
- Bedrooms
- Bathrooms
- Area
- Year Built
- Parking
- Pool
- Location
- Price

The 10 datasets are located in the raw data folder, likewise the code to extract the 10 datasets are located in the Data Extraction folder.

## Data Cleaning

For this data processing, transformation and cleaning step use the pandas library.

1) Join each dataset of the 10 cities to form a single dataset with the name "df_combined".

2) Explored the columns of the dataset to see if there are many missing values: 

- The column "Pool" is eliminated because it had more than 2000 missing records. Therefore, the dataset now consists of 9 columns.
- Any row containing a missing value is removed.

3) We proceed to transform each column separately, correcting the data type and eliminating special characters.

4) A new column is created for the dataset "price / sqft".

5) Search for outliers in the data.

Finally the final dataset is saved in a csv file "cleaned_data.csv".

![cleaned_data](https://user-images.githubusercontent.com/58336896/136228123-a2a7b406-6ef3-4434-bc37-c54638c37bbc.png)


## Data Analysis

After creating a clean dataset (cleaned_data.csv) the file was uploaded to posgresql, so that an exploratory analysis of the data can be done, both in python and SQL.
The code for this stage is in the "Data Analysis.ipynb" notebook.

![output sql](https://user-images.githubusercontent.com/58336896/136228453-21e794d2-f2dc-4bd8-b362-b0c1e689c166.png)

In this EDA, we asked several questions of the data to find patterns and possible correlations between the different variables that could explain house prices:

## Regression Model

Once the exploratory data analysis is completed, a machine learning model is created by implementing a regression analysis in order to predict the price value. Use FLAML https://github.com/microsoft/FLAML a library created by Microsoft that builds machine learning models in a fast and easy way.

The best model was built with the Random Forest regressor estimator, using the evaluation metric "r2".

The code for this section can be found in "Regression Model.ipynb".
