
# NYC_SCHOOLS

## Introduction
This project is a based on a collaboration between Manoranjan Kumar (me) /Gary Sepulveda as
part of a final project in the University of Texas @ San Antonio Master of Science Data Analytics
program. We chose a current (as of 8/7/18) Kaggle challenge (PASSNYC) as our topic. This basically is a
challenge in the NYC school district to ultimately help underserved student achieve academic success by
taking and being accepted into some the best specialized High School in the city.

## Problem Description -
Black & Latino Students are significantly underrepresented in NYC Specialized High Schools. 
We took the PASSNYC dataset from Kaggle and attempted to build a model predicting Average Proficiency of maths and english.
Our aim is to predict and rank the schools based on multiple feature engineered columns using open data.

## Data Sources
- PASSNYC KAGGLE
    https://www.kaggle.com/samextensibleenergy/2016-school-explorer-new
    
- Feature Engineering (New data points)
1 Mile Radius from Each School
    Libraries - https://data.cityofnewyork.us/Business/Library/p4pf-fyc4
    After School Programs - https://data.cityofnewyork.us/Social-Services/After-School-Programs/6ej9-7qyi
    Low and Extremely Subsidized Housing - https://data.cityofnewyork.us/Housing-Development/Affordable-Housing/x9h2-i4fk/data

Census Tract Data (geoID) - Uses tidycensus and censusr package
    Median HH Income
    Ratio of Income to Poverty
    Child Poverty (under 18 Yrs old)
    Num of HH with Food stamps
    Num of HH with Health Coverage

## Data Cleaning and Preprocessing
    Reduced 55 missing response variable rows. (Final number of observations –  1,217)
    Imputed with KNN for missing NA’s (394 of 1,272) or 31%
    Box-Cox transformation applied.
    No degenerate variables found (near zero var)
    PCA 90% variance explained by 10 of 19 components
    Checked & removed highly correlated predictor variables (cutoff 0.8)
    Evaluated and reduced predictors using Variable Clustering as a second approach using lowest rsq ratio.

## Model Tuning
    Achieved a 85 training/15 test split on main dataset. 
    Used repeated 10-fold cross validation to tune multiple models.
    Best results were from ranfom forest but it was overfitting.
    We selected best model as lm and pls due to simplicity and interpretability.
    Selected PLS Model - Prediction performance good @ 79.0% R² / 0.188 RMSE
    
## Conclusion
Feature Engineered variables  impacted model prediction (good insight such as number of subsidized housing)
Simple linear models did well compared to unsupervised ones.
Further research and refinement needed:
     Consider predictor variables that impact the total educational pipeline
     Portable model  -  Can be applied to other school districts/geographies
     Assess impact of controllable variables impacting educational success
