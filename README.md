# Real Estate Analysis
![Python](https://img.shields.io/badge/Python-3.8-blueviolet)
![SQL](https://img.shields.io/badge/SQL-red)
## Introduction

The purpose of this project is to make an analysis about the real estate market in 10 of the main cities in the USA, for this we have created the dataset extracting data from the website www.trulia.com. 
```
.
└── Real Estate Analysis
    ├── Data Extraction
    ├── Data Cleaning
    └── Data Analysis
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

Each dataset consists of the following attributes:
- Address
- Bedrooms
- Bathrooms
- Area
- Year Built
- Parking
- Pool
- Location
- Price
