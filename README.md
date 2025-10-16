# Project Title

Economics of Emissions: Prediction Analysis of the Contribution of Emissions to the GDP of the states in the United States of America using a Cluster-Spatio-Temporal Approach


# Project Overview

The project will explore the economics of emissions under the title “Economics of Emissions: Prediction Analysis of the Contribution of Emissions to the GDP of the states in the United States of America using a Cluster-Spatio-Temporal Approach”. 
A dataset collected from the Federal Reserve Bank of St. Louis (FRED) and four datasets from the Emissions Database for Global Atmospheric Research (EDGAR) will be utilized for the project. 
As a preliminary step, the project will first aim at grouping the states depending on the extent of emissions, cumulatively and at different time periods; this will serve to paint a picture of the history of emissions in each of the states. 
Machine learning algorithms for prediction analysis for the GDP of the states will then be developed, with the extent of emissions and the type of emissions as predictors in a time series framework. 
Through the algorithms, the economic dependence of the states on emission will be investigated for the present and future cases. 


# Workflow Summary

The chart below summarizes the workflow for the project.

![Descriptive Analysis](https://github.com/Rohan7386/Cluster-Spatio-Temporal-Approach-to-Prediction-Analysis-of-the-Contribution-of-Emissions-to-the-GDP-/blob/main/Economics%20of%20Emission-2025-10-12-144904.png)


# Methods

The following methods were employed:
- Principal Component Analysis
- KMeans Clustering
- Predictive Modelling using Time Series Analysis (Random Forest Model, XGBoost Model and Light GBM Model


# Results Summary 

Although all the models had very high R2 scores for the training set, the Random Forest model with default parameters had the highest R2 for the training set at 0.9766 indicating that the model explained up to 97.66% of the variation in the GDP. The model also has the lowest MAE at 37460.08 for the test set.
Although all the models had very high R2 scores for the test set, the tuned XGBoost model had the highest R2 for the testing set at 0.9178 indicating that the model explained up to 91.78% of the variation in the GDP. In addition, the model had the lowest RMSE of 64195.24 for the test set.
For the model with the highest R2 for the testing set, Tuned XGBoost, the two features with the highest importance were the dummy variables for the F-Gases AR5 clusters. 

# Technology Used 

- Languages Used: Python
- Additional Softwares: Tableau, Mermaid
- Data Sources: EDGAR (European Commission, 2024) and FRED (Federal Reserve Bank of St. Louis, 2024)

# References

European Commission. (2024). Emissions Database for Global Atmospheric Research (EDGAR). European Commission, Joint Research Centre.
Federal Reserve Bank of St. Louis. (2024). Federal Reserve Economic Data (FRED). https://fred.stlouisfed.org/


# Project Blog
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


## Week 4

The following progress was made for the week:

•	Data Merging: Merging of the emissions and GDP data using Year and State was completed. This reduced the timeframe of the data to cover the period between 2005 to 2023 since the GDP data had a time frame of between 2005 and 2023 while the emissions data covered the period between 1990 and 2023.

•	Geospatial Analysis: Geospatial analysis of the GDP, and the clusters for the Combined Emissions, Fossil CO2 emissions, CH4 emissions, N2O emissions and F-Gases emissions completed in Tableau.

•	Contextual Interpretation: Interpretation of the geospatial analysis of the emissions relative to the interpretation of the geospatial analysis of the GDP. 

The Geospatial Analysis is presented in the dashboard below:

![Geospatial Analysis](https://github.com/Rohan7386/Cluster-Spatio-Temporal-Approach-to-Prediction-Analysis-of-the-Contribution-of-Emissions-to-the-GDP-/blob/main/Geospatial%20Analysis.png)

The bulkiness of the geospatial analyses represent an area of discussion. Geospatial analysis was completed for the GDP, and the clusters for the Combined Emission, Fossil CO2 emissions, CH4 emissions, N2O emissions and F-Gases emissions. However, the mapping involved for each of the years between 2005 and 2023 so as to be able to observe how the evolution took place overtime. The slider in Tableau however allowed for the same map for each of the analyses to be used for observation over time. Pairs of mappings were utilized for the analyses, resulting in the five plotting sheets in Tableau. These pairs were: the GDP - Combined Emission, GDP - Fossil CO2 emissions, GDP - CH4 emissions, GDP - N2O emissions and GDP - F Gases emissions. By having the GDP and emissions mapping side by side, it becomes easier to have contextualized interpretation with the evolution of the GDP observed along with the evolution of each of the emissions.


## Week 5

The following progress was made for the week:

•	Data Preparation for Modelling: Three cluster variables created from cluster analysis stage required conversion to dummy variables for use in the training of the models. Using the One-hot Encoding approach, the three cluster variables were converted into dummy variables with each of the constituent clusters converted into variables. Following the encoding of the cluster variables, the data then required feature engineering for the lag feature. Across all the features, forming the predictor variables, the lags were generated. Following the creation of the lags, the data then required partitioning into training and testing sets. The merged, encoded and lagged dataset was split into training and testing sets such that the former had 75% of the data with the latter having 25% of the data. Additionally, the data partitioning was such that the data for the features and the target were split so that in both the training and testing partitions we had corresponding target and features subsets. 

•	Random Forest Model: The random forest model was initialized and trained using the training data with the parameters set as default. The model performance was evaluated for both the training set and the testing set. Based on the model performances and using them as the baseline, the random forest model was tuned with hyperparameters adjusted into order to improve on the model performances. 

•	XGBoost Model: The XGBoost model was initialized and trained using the training data using the default parameters. The model performance was evaluated for both the training set and the testing set. Based on the model performances and using them as the baseline, the random forest model was tuned with hyperparameters adjusted into order to improve on the model performances. 

Hyperparameter tuning specifically represented a challenge for both the Random Forest Model and the XGBoost Model. In both instances multiple changes were required for each of the hyperparameters to ensure that the best combination of the hyperparameters is obtained for yielding the best model performance. 


## Week 6

The following progress was made for the week:

•	Light GBM Model: The LightGBM was initialized and trained using the training data with the parameters set as default. The model performance was evaluated for both the training set and the testing set. Based on the model performances and using them as the baseline, the random forest model was tuned with hyperparameters adjusted in order to improve on the model performances. 

•	Performance Comparison: The performance of the Random Forest, XGBoost and LightGBM models were compared based on the performance metrics for the testing set. The following four performance metrics were compared for the three models; R2, Root Mean Square Error (RMSE), Mean Absolute Error (MAE) and Mean Absolute Percentage Error (MAPE).

•	Performance Evaluation Visualization: 

o	For each of the three models, the four performance metrics were plotted for the default parameters model and the tuned hyperparameters model. Additionally, for each of the default parameters model and the tuned hyperparameters model pairs, both the performance metrics for the training set and the test set were plotted. The bar charts were used for the plotting of the performance metrics.

o	The performance metrics for the each of the three models for the testing set were then plotted for comparison for the four performance metrics. The bar chart was used for visualization of the comparison between the testing set performance metrics across the three models.

o	Tabular visualization was also generated together with the bar charts above with information that corresponds with the information on the bar charts, to allow for comparison of the values of the performance metrics. 


The dashboard below compares the performance for the three models.

![Predictive Modelling](https://github.com/Rohan7386/Cluster-Spatio-Temporal-Approach-to-Prediction-Analysis-of-the-Contribution-of-Emissions-to-the-GDP-/blob/main/Predictive%20Modelling.png)






