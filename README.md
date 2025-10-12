# Economics of Emissions: Prediction Analysis of the Contribution of Emissions to the GDP of the states in the United States of America using a Cluster-Spatio-Temporal Approach

## Project Summary

The project will explore the economics of emissions under the title “Economics of Emissions: Prediction Analysis of the Contribution of Emissions to the GDP of the states in the United States of America using a Cluster-Spatio-Temporal Approach”. 
A dataset collected from the Federal Reserve Bank of St. Louis (FRED) and four datasets from the Emissions Database for Global Atmospheric Research (EDGAR) will be utilized for the project. 
As a preliminary step, the project will first aim at grouping the states depending on the extent of emissions, cumulatively and at different time periods; this will serve to paint a picture of the history of emissions in each of the states. 
Machine learning algorithms for prediction analysis for the GDP of the states will then be developed, with the extent of emissions and the type of emissions as predictors in a time series framework. 
Through the algorithms, the economic dependence of the states on emission will be investigated for the present and future cases. 


## Week 2

Data collection from FRED was completed through the following link: https://fredaccount.stlouisfed.org/public/datalist/5498/download. 
The resultant data contained 53 columns and 74 rows. The first column of the data was the observation data that contained the beginning dates for each quarter from the first quarter of the year 2005 through to the first quarter of the year 2023. 
The remaining 52 columns contained the GDP for 52 states and territories in the United States. 
Data collection from EDGAR was completed for the four datasets through the following link: https://edgar.jrc.ec.europa.eu/dataset_ghg2024_nuts2. 
The four resultant datasets were on the Fossil CO2, CH4, N2O and F-Gases emissions. The datasets were identical in structure with 40 columns and 3853 rows. 
The datasets contained the following initial columns: Substance, ISO, Country, Subnational Code, Subnational Desc and Sector giving information on the type of emission, country, subnational level (for regions and states) and the sector. 
The remaining columns provide the corresponding emission levels for each year between 1990 and 2023. 


## Week 3

The following progress was made for the week:

•	Principal Component Analysis: The emissions for the years 1990 to 2023 were reduced in dimension in the PCA to optimal components for combined emissions, Fossil CO2 emissions, CH4 emissions, N2O emissions and F-Gases emissions.
•	Cluster Analyses: The K-Means clusters were computed from the optimal components for combined emissions, Fossil CO2 emissions, CH4 emissions, N2O emissions and F-Gases emissions.
•	Data Fusion: The clusters resulting from the respective cluster analyses were combined to the initial dataset to make the final dataset.

The descriptive analysis is presented in the dashboard below:

![Descriptive Analysis](https://github.com/Rohan7386/Cluster-Spatio-Temporal-Approach-to-Prediction-Analysis-of-the-Contribution-of-Emissions-to-the-GDP-/blob/main/Descriptive%20Statistics.png)

Determination of the number of components for the PCA model was particularly a challenge. In comparison, K-Means clustering through the within cluster sum of squares allows for the determination of the optimal number of clusters to be predicted from the K-Means. The PCA model requires the number of components parameter without a way of determining a starting number of components. Although the scree plot is applied later on to get the optimal number of components, the number of components to begin with is the challenge. 








