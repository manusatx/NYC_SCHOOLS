# NYC_SCHOOLS
## Problem Description -
Black & Latino Students are significantly underrepresented in NYC Specialized High Schools. 
We took the PASSNYC dataset from Kaggle and attempted to build a model predicting Average Proficiency.
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
    # of HH with Food stamps
    # of  HH with Health Coverage

## Data Cleaning and Preprocessing

    Reduced 55 missing response variable rows. (Final number of observations –  1,217)
    Imputed with KNN for missing NA’s (394 of 1,272) or 31%
    Box-Cox transformation applied.
    No degenerate variables  found (near zero var)
    PCA 90% variance explained by 10 of 19 components
    Checked & removed highly correlated predictor variables
    Evaluated and reduced predictors using Variable Clustering as a second approach
    
 
