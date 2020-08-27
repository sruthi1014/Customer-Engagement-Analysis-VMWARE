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
   step 1: collecting column indexes which have same value in all the observations and removal of those columns 
   ![R code for step 1](/images/step1.png)
2. Smote to balance data
3. Feature selection - part 1 (with RF)
4. Feature selection - part 2 (with Lasso and Ridge)
5. RF model
6. XGBoost model


