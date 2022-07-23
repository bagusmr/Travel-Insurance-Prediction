# Travel Insurance Prediction
Travel insurance is a type of insurance that covers the costs and losses associated with travelling. It is useful protection for those travelling domestically or abroad. (Investopedia)
# Business Understanding
- Problem: According to demographical statistics captured by jerseyislandholidays website, 41% of Americans did not buy travel insurance for various reasons such as it was too expensive, they were travelled for a short vacation, forgot to buy, did not think it was necessary, and waste of money. These reasons have led to almost 50% of Americans having to bear the consequences of cost losses during their vacation. The same reasons also happen in British, where 21% of them did not buy travel insurance, 37% felt it was unnecessary, and 28% said that cost loss on vacation is a risk they can bear with. In Indonesia, this is also a common thing to happen. Most Indonesian who took flight services did not think travel insurance is a useful feature, and this kind of perception may lead to a revenue drop, hence not good for the travel insurance company. On the other hand, coronavirus travel regulations in Indonesia had been loosened up, leading to the increased number of people who took flight services since February 2022.
- Goal: Increasing the sales amount of travel insurance products.
- Objectives: Conducting an analytical approach to identify potential features that may influence customers and suggest business recommendations which will affect customers to buy travel insurance.
- Business Metric: Sales Amount.
# Data Understanding
The dataset contains a list of 1987 recorded passengers, some of them have bought travel insurance in 2019 with various features which are:
- Age: Age of the passenger.
- Employment Type: The sector in which the passenger is employed.
- Graduate or Not: Whether the passenger is a college graduate or not.
- Annual Income: The yearly income of the passenger in Indian rupees (INR).
- Family Members: Number of members in the passenger's family.
- Chronic Disease: Whether the passenger suffers from any major diseases.
- Frequent Flyer: Derived data based on the passenger's history of booking air tickets at least 4 different instances in the last 2 years (2017-2019).
- Ever Travelled Abroad: Whether the passenger did or did not have travelled to a foreign country.
- Travel Insurance: Whether the passenger bought the travel insurance or not in 2019. 
On this dataset, the total passenger who bought travel insurance is 710 passengers which is around 35% of the total recorded. For details of the dataset, please visit https://www.kaggle.com/datasets/tejashvi14/travel-insurance-prediction-data
# Data Insights
- Passengers with high annual incomes tend to buy travel insurance. This could also mean that the travel insurance price is too expensive.
- Passengers with age 30 and above tend to buy travel insurance. This might be correlated with their annual income since increased age most of the time represents their dedication and expanding experiences in a company, hence upscaling their salary.
- Passengers with family members from 5 and above tend to buy travel insurance. This is probably because the risks of cost losses will be bigger when they travel together with their families.
- Passengers who work in the government sector do not have the interest to buy travel insurance. This is probably correlated with age and annual income since, in Indonesia, fresh graduates who just started their career in the government sector usually have low to mid-salary amounts.
- Passengers who graduated tend to buy travel insurance. This is probably because they have more knowledge and information regarding the risks and benefits of using or not using travel insurance. But at the same time, passengers who graduated and did not buy travel insurance are also bigger. This is probably because of the same reasons which ended up making them willing to take the risks.
- Passengers who have chronic disease slightly tends to buy travel insurance.
- Passengers who frequently use flight services tend to buy travel insurance. This is probably due to their experiences using air transportation.
- Passengers who have travelled abroad tend to buy travel insurance. This is probably due to the higher risks of travelling abroad.
# Data Preparation
There are some steps that were conducted to ensure the dataset is proper modelling.
- This dataset did not have missing values, duplicated data, and outliers.
- Drop a feature called 'Unnamed: 0' which did not represent anything other than a list of numbers.
- There are 4 features that were converted into numerical type using label encoding.
- Annual income was converted into Indonesian rupiahs (IDR) to match the problem statement.
- The data on numerical features were relatively normal, there was no skew.
# Modelling
- The dataset was normalized and undergo various combinations of data imbalance handling to find the best model.
- The algorithm used to generate the best-fit model were Decision Tree Classifier, Random Forest Classifier, XGBoost, AdaBoost, and CatBoost.
- To treat potential customers, the model should be able to capture True Positive and True Negative as much as possible. Therefore, balanced accuracy (average recall) was used as the evaluation metric.
# Model Insights
- According to the modelling results, the best fit model with 79% balanced accuracy was using Decision Tree Classifier with undersample handling for imbalance data and hyperparameter tuning.
- Annual Income was the most influential feature on passenger's tendency to buy travel insurance, followed by Age and Family Members. Ever travelled abroad is the least important feature that affected on passenger's interest. This is probably due to not everyone being financially capable and having the interest to travel abroad for vacation.
# Business Recommendation
There is a probability that the price of travel insurance is too expensive, which is why only passengers with high annual incomes could buy travel insurance. One of the solutions to this problem is by grading the price of travel insurance into 3 types of packages which are Bronze, Silver, and Gold to meet customer's interest related to their financial capabilities. Therefore, a mathematical simulation is performed to look for gained sales volume which will affect sales amount. 
We knew that existing passengers who bought travel insurance were 710 people. Assuming the insurance price is around 433k IDR which is based on common insurance price of an international flight from Indonesia to Singapore, we can calculate these and have a result of sales amount of around 307.42 million IDR. 
From the modelling, we captured 270 True Negatives, meaning there are 1138 passengers who did not have interest to buy travel insurance and will be given the grading packages treatment. Assuming 433k IDR is the highest price which will be labelled as Gold package, we can calculate the Silver and Bronze package price by using this method:
- Gold Price - (Annual income mean relative difference percentage between classes * Gold Price) 
The mean relative difference percentage was measured by clustering passengers based on all annual income unique data into 3 classes equally, finding mean of the 3 classes, and calculating using this method :
- ((Gold Income Mean - Silver Income Mean)/Gold Income Mean) * 100 for mean relative difference between Gold and Silver Annual Income
- ((Gold Income Mean - Bronze Income Mean)/Gold Income Mean) * 100  for mean relative difference between Gold and Bronze Annual Income 
From there, we know that :
- Mean relative difference for Silver Income is 26.4% from Gold Income, hence the price for Silver package is 320k IDR.
- Mean relative difference for Bronze Income is 61.6% from Gold Income, hence the price for Bronze package is 166k IDR. 
Since the Gold price was already given to the 710 passengers, if we assume we can capture at least 10% of new customers from the predicted 1138 by giving them the Silver and Bronze packages, we will have at least:
- 114 new customers who buy Bronze package
- 102 new customers who buy Silver package 
Therefore, we will gain additional sales amount :
- Bronze package = 18.92 million IDR
- Silver package = 32.64 million IDR 
- Thus, we will gain 51.56 million IDR in total, which means 16% to be added up from the existing sales amount.
