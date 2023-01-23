# Churn Analysis

  This analysis used data of employees of a bank to predict whether a employee will stay in the company or not.
  
  The dataset can be found on [Kaggle](https://www.kaggle.com/datasets/shubh0799/churn-modelling).
  
## Data Dictionary

  The dataset provides details of the customers in the company
  
  * Customer ID.
  * Surname.
  * Age.
  * Gender.
  * Tenure - Time of bond with the company.
  * Balance in the bank.
  * Number of products they own.
  * Which country they belong to.
  * Their Credit Score.
  * If they have a credit card.
  * If they were active or not with the bank before the moment where they left the company.
  * Their estimated salary.
  * If they left the company or not.
  
## Data Visualization
  
  Now that we know our variables, let's check how they relate to our response variable - if the customer left the company or not.

* ### Churn numbers

  In this dataset we have 10000 custumers, of which 7963 are still in the company and 2037 have left.
  
![churn numbers](https://user-images.githubusercontent.com/121902546/213935392-b978c7d7-5403-4fdc-ab97-f15ceffd0e2c.png)


* ### Churn by age range

  We can see most of the loyal custumers in the range of 30-40 years, in the meantime the highest churn rate is found in the range of 40-50 years.

![age x churn](https://user-images.githubusercontent.com/121902546/213935452-01138f0a-9f1d-469b-b032-f110f18d6437.png)

* ### Churn by country

 France and Germany have the biggest number of members that left.

![country x churn](https://user-images.githubusercontent.com/121902546/213935460-28122c8d-be24-464b-9cd0-56a9d9b6eac9.png)

* ### Churn by gender
  
  Females have a higher tendency to leave the company.

![gender x churn](https://user-images.githubusercontent.com/121902546/213935542-d6c46c46-be72-4a20-87bb-52405de9fda7.png)

* ### Churn by activity

  Inactive customers have higher tendency to leave the company.

![status of activity relevance](https://user-images.githubusercontent.com/121902546/213944598-b6b58487-a917-4105-a80c-8ca59098ec62.png)

* ### Churn by number of products

  The highest churn rate is found between customers that own only one product, however we should highlight the fact that custumers with more than two products have a extremely high chance to leave the company as well.
    
![products x churn](https://user-images.githubusercontent.com/121902546/213935566-3853e3ec-5ec2-43b6-94c8-1e9580d54de9.png)

* ### Salary influence

    We cannot see any impact of estimated salary into the churn rates.

![salary x churn](https://user-images.githubusercontent.com/121902546/213935567-85955d24-a77b-461b-b782-293c8ba81eae.png)

* ### Churn by Tenure
  
  We have very similar churn rates when considering time spent in the company. Customers that spent less than one year or over nine years are the ones with the lowest churn rate.
   

![tenure x churn](https://user-images.githubusercontent.com/121902546/213935568-9cd497d7-2580-4442-8b92-a142dec1e62d.png)

* ### Churn by Balance

  The highest churn rate is found between members with no balance.

![balance x churn](https://user-images.githubusercontent.com/121902546/213935570-31721e2f-69e5-42a7-8b58-bf6219c360b4.png)

* ### Credit Card relevance to Churn

  Members with credit card have the highest churn rate.

![credcard churn](https://user-images.githubusercontent.com/121902546/213935571-89e0ca3c-b6f8-4c66-8cf3-3b915cc0eda3.png)

* ### Credit Score relevance to Churn

  Customers with credit score in the range 600-700 are the ones with the highest churn rate.

![credscore x churn](https://user-images.githubusercontent.com/121902546/213935572-00f51439-cc5c-4b5e-8f05-efc0565066a1.png)

* ### Correlation
  
  For this step we used the dummy versions of our categorical variables - Geography and Gender - to check the correlation of all our variables with the response variable.
  
  We can see that although all the correlations are weak, the most meaningful ones are: age, balance, both genders, activity and geography (France and Germany).

![Correlation with dummies](https://user-images.githubusercontent.com/121902546/213945348-02aa2fd0-b11e-41d6-8c73-b08ecd27b88a.png)

* ### Machine Learning
  
  In this project was tested the following models of classification - Logistical Regression, Gradient Boosting, Bagging Classifier and Random Forest.
  
  Variables that wouldn't provide any meaningul information for this specific analysis, as surname and customer ID were dropped. Some of the variables with very low correlation were also dropped, such as the presence of credit card, credit score, estimated salary and geography (spain).
  
  The response variable - Exited - was imbalanced, so we used the Imbalanced-learn library to provide the necessary tools to handle the issue.
  
  Train-Test splitting was done with 80% train, 20% test.
  
  The model with the best accuracy to predict the churn rate was the Bagging Classifier with 88.98% accuracy. The same model also presented the best percentage for all the other metrics analysed. Including a F1-Score of 89.34% and ROC AUC Score of 89.12%.
  
  The second best was the Gradient Boosting Classifier with an accuracy of 86.41% while the worst model trained was the Logistical Regression with only 77.34%.
  
  Below we can see the confusion matrix generated for the Bagging model.
  
![cm-bagging](https://user-images.githubusercontent.com/121902546/214082553-badf662f-1729-4933-91c1-00b8edafee02.png)

  We can also check a comparison between the ROC Curves for the models in this analysis.
  
![roc curves comparison](https://user-images.githubusercontent.com/121902546/214082558-4bf65b93-bafc-42c6-8e62-310f62dc9e5a.png)

  
