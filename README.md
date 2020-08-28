# Customer-Engagement-Analysis-VMWARE

### Table of contents
* [Introduction](#introduction)
* [Technologies](#technologies)
* [Data](#data)
* [Algorithms](#algorithms)
* [Approach](#approach)

### Introduction
Worked on Harvard case study - "Improving customer engagement through analytics". The objective of this project is to analyze the rich data on customer behavior on VMW website and provide insights on customer engagement. 
[Customer-Engagement-Analysis-VMWARE](https://github.com/sruthi1014/Customer-Engagement-Analysis-VMWARE/blob/master/Customer_Engagement_analysis.Rmd) file has the code for the analysis

### Technologies
Project is created with:
* R Studio

### Data
* VMWARE web analysis data 
available at this [link](https://store.hbr.org/product/improving-customer-engagement-at-vmware-through-analytics/IMB623) for purchase.
The data has around 700 columns.

### Algorithms
* SMOTE
* Random forest
* LASSO
* Ridge Regression
* XGBoost

### Approach:
1. Data Cleaning
   Data consists of 700 columns with few redundant columns and rows. Due to which initial cleaning was done step wise as mentioned below:
   * step 1: collecting column indexes which have same value in all the observations and removal of those columns 
   ![R code for step 1](https://github.com/sruthi1014/Customer-Engagement-Analysis-VMWARE/blob/master/images/step1.PNG)<br>
   * step 2: creating a new level "NotAVailable" for capturing both NAs and Unknown values in each categorical column <br>
              analyzed the columns in the data manually to decide which is categorical variable
   ![R code for step 2](https://github.com/sruthi1014/Customer-Engagement-Analysis-VMWARE/blob/master/images/step2.PNG)<br>
   * step 3: collecting column indexes of the  date columns which have 70% or more data as 9999 from the data set of 576 
   ![R code for step 3](https://github.com/sruthi1014/Customer-Engagement-Analysis-VMWARE/blob/master/images/step3.PNG)<br>
   * step 4: collecting index of  columns that have more than 70% of NAs 
   ![R code for step 4](https://github.com/sruthi1014/Customer-Engagement-Analysis-VMWARE/blob/master/images/step4.PNG)<br>
   * step 5: imputation of missing data for numeric columns
   ![R code for step 5](https://github.com/sruthi1014/Customer-Engagement-Analysis-VMWARE/blob/master/images/step5.PNG)<br>
   * step 6: remove all the collected columns from the original data 
2. Smote to balance data
   There were 7 levels in the target with one single value existing 80% of the data. To handle this imbalance in the data we tried over sampling and undersampling using SMOTE
   ![SMOTE code](https://github.com/sruthi1014/Customer-Engagement-Analysis-VMWARE/blob/master/images/smote.PNG)
3. Feature selection - part 1 (with RF)<br>
   On the imbalanced data applied Random forest model to find the top 150 significant variables which were able to explain the data. 
   ![Feature selection part 1](https://github.com/sruthi1014/Customer-Engagement-Analysis-VMWARE/blob/master/images/featureselectionpart1.PNG)
4. Feature selection - part 2 (with Lasso and Ridge)<br>
   With the 150 significant variables, performed Lasso and Ridge with Cross validation by using the metric recall instead of accuracy as it is an imbalanced data. Chose the        variables with non zero coefficients.
   ![Feature selection part 2] (https://github.com/sruthi1014/Customer-Engagement-Analysis-VMWARE/blob/master/images/featureselectionpart2.PNG)
5. Models   
   After completing the feature selection, built different models to check which performs better with predicting the unseen data. 
   1. RF model
   2. Regularized Lasso/Ridge
   3. XGBoost model
6. Results


