# Travel Insurance Prediction
Travel insurance is a type of insurance that covers the costs and losses associated with traveling. It is useful protection for those traveling domestically or abroad. (Investopedia)
# Business Understanding
- Problem: According to demographical statistics captured by jerseyislandholidays website, there are 41% americans who did not buy travel insurance with various reasons such as it was too expensive, they were travelled for a short vacation, forgot to buy, did not think it was necessary, and waste of money. This reasons have led to almost 50% of americans had to bear the concequences of cost losses during their vacation. The same reasons also happen on british, where 21% of them did not buy travel insurance, 37% felt it was unnecessary, and 28% said that cost losses on vacation is risk they can bear with. In Indonesia, this is also a common think to happen. Most of indonesian who took flight services did not think travel insurance is a useful feature, and these kind of perceptions may lead to revenue drop, hence not good for travel insurance company. On the other hand, corona virus travel regulations in Indonesia had been loosened up, leading to the increased number of people who took flight services since February 2022.
- Goal: Increasing the sales amount of travel insurance product.
- Objectives: Conducting analytical approach to identify potential features that may influence customer and suggesting business recomendations which will affect customers to buy travel insurance.
- Business Metric : Sales Amount.
# Data Understanding
The dataset contains a list of 1987 customers who bought travel insurance in 2019 with various features which are:
- Age: Age of the customer.
- Employment Type: The sector in which the customer is employed.
- Graduate or Not: Wether the customer is college graduate or not.
- Annual Income: The yearly income of of customer in indian rupees (INR).
- Family Members: Number of member in customer's family.
- Chronic Disease: Wether the customer suffers from any major diseases. 
- Frequent Flyer: Derived data based on customer's history of booking air tickets at least 4 different instances in the last 2 years (2017-2019).
- Ever Travelled Abroad: Wether the customer did or did not have travelled to a foreign country.
- Travel Insurance: Wether the customer bought the travel insurance or not in 2019.
On this dataset, the total customer who bought travel insurance is 710 customers which means around 35% of the total recorded passengers.
For details of the dataset, please visit https://www.kaggle.com/datasets/tejashvi14/travel-insurance-prediction-data
# Data Insights
- Passengers with high annual income have tendency to buy travel insurance. This could also mean that the travel insurance price is too expensive
- Passengers with age from 30 above have tendency to buy travel insurance. This might be corelated with their annual income since increased of age most of the time represents their dedications and expanding experiences in a company, hence upscalling their salary.
- Passengers with family members from 5 above have tendency to buy travel insurance. This probably because of the risks of cost losses will be bigger when they travel together with their families.
- Passengers who work at goverment sector have tendency to not buy travel insurance. This probably corelated with age and annual income factor, since in Indonesia, freshgraduates who just started their career on goverment sector usually have low to mid salary amount.
- Passengers who graduated have tendency to buy travel insurance. This probably because they have more knowledge and informations regarding the risks and benefits of using or not using travel insurance. But at the same time, passengers who graduated and not buy travel insurance is also bigger. This probably because of the same reasons which ended up making them willing to take the risks.
- Passengers who have chronic disease slightly tends to buy travel insurance.
- Passengers who frequently use flight services tend to buy travel insurance. This probably due to their experiences using air transportations.
- Passengers who have travelled abroad tend to buy travel insurance. This probably due to higher risks of travelling abroad.
# Data Preparation
There are some steps that were conducted to ensure the dataset are proper for EDA and modelling. 
- This dataset did not have missing values, duplicated data, and outliers. 
- Drop a feature called 'Unnamed: 0' which did not represents anything other than number.
- There are 4 features that were converted into numerical type using label encoding.
- Annual income were converted into indonesian rupiahs (IDR) to match the problem statement.
- The data on numerical features were relatively normal, there were no skew. 
# Modelling
- The dataset were normalized and undergo various combination of data imbalance handling to find the best model.
- The algorithm used to generate best fit model were Decicion Tree Classifier, Random Forest Classifier, XGBoost, AdaBoost, and CatBoost.
- In order to treat potential customers, the model should be able to capture True Positive and True Negative as much as possible. Therefore, balanced accuracy (average recall) was used as evaluation metric.
# Model Insights
- According to the modelling results, the best fit model with 79% balanced accuracy was using Decision Tree Classifier with undersample handling for imbalance data and hyperparameter tuning.
- Annual Income was the most influence feature on passenger's tendency to buy travel insurance, followed by Age and Family Members. Ever travelled abroad is the least important feature that affected on passenger's insterest. This probably due to not everyone were financially capable and have the interest to travel abroad for vacation.
# Business Recomendation
There is a probability that the price of travel insurance is too expensive, that is why only passengers with high annual income could buy travel insurance. One of the solution to this problem is by grading the price of travel insurance in 3 type of packages which are Bronze, Silver, and Gold to meet customer's interest related to their financial capabilities. Therefore, a mathematical simulation is performed to look for gained sales volume which will affect sales amount.
We knew that existing passengers who bought travel insurance were 710 people. Assuming insurance price around 433k IDR which based on common insurance price of international flight from Indonesia to Singapore, we can calculate these and have a result of sales amount around 307.42 million IDR.
From the modelling, we captured 270 True Negatives, meaning there are 1138 passengers who really did not have interest buy travel insurance and will be given the grading packages treatment. Assuming 433k IDR is the highest price which will be labeled as Gold package, we can calculate the Silver and Bronze package price by using this method:
- Gold Price - (Annual income mean relative difference precentage between classes * Gold Price)
The mean relative difference precentage was measured by clustering passengers based on all annual income unique data into 3 classes equally, find mean of the 3 classes, and calculate using this method :
- ((Gold Income Mean - Silver Income Mean)/Gold Income Mean) * 100 ; For mean relative difference between Gold and Silver Annual Income
- ((Gold Income Mean - Bronze Income Mean)/Gold Income Mean) * 100 ; For mean relative difference between Gold and Bronze Annual Income
From there, we know that :
- Mean relative difference for Silver Income is 26.4% from Gold Income ; The price for Silver package is 320k IDR.
- Mean relative difference for Bronze Income is 61.6% from Gold Income ; The price for Bronze package is 166k IDR.
Since the Gold price were already given to the 710 passengers, if we assume we can capture at least 10% of new customers from the predicted 1138 by giving them the Silver and Bronze packages, we will have at least:
- 114 new customers who buy Bronze package
- 102 new customers who buy Silver package
Therefore, we will gain additional sales amount :
- Bronze package = 18.92 million IDR
- Silver package = 32.64 million IDR
Thus, we will gain 51.56 milion IDR in total, which means a 16% to be added up from existing sales amount.
