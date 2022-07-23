# Travel Insurance Prediction
Travel insurance is a type of insurance that covers the costs and losses associated with traveling. It is useful protection for those traveling domestically or abroad. (Investopedia)
# Business Understanding
- Problem: According to demographical statistics captured by jerseyislandholidays website, there are 41% americans who did not buy travel insurance with various reasons such as it was too expensive, they were traveled for a short vacation, forgot to buy, did not think it was necessary, and waste of money. This reasons have led to almost 50% of americans had to bear the concequences of cost loss during their vacation. The same reasons also happen on british, where 21% of them did not buy travel insurance, 37% felt it was unnecessary, and 28% said that cost losses on vacation was risk they can bear with. In Indonesia, this is also a common think to happen. Most of indonesian who took flight services did not think travel insurance is a useful feature, and these kind of perceptions may lead to revenue drop, hence not good for travel insurance company. On the other hand, corona virus travel regulations in Indonesia had been loosened up, leading to the increased number of people who took flight services since February 2022.
- Goal: Increasing the sales amount of travel insurance product.
- Objectives: Conducting analytical approach to identify potential features that may influence customer and suggesting business recomendations which will affect customers to buy travel insurance.
-Business Metric : Sales Amount
Stage 1
- Kami melakukan EDA yaitu univariate analysis, bivariate analysis, dan multivariate analysis untuk menganalisa secara menyeluruh  insight pada setiap feature dan  
  hubungannya dengan target.
- Terdapat 10 kolom dengan 9 feature dan 1 target feature. 6 feature numerik dimana 2 diantaranya merupakan binary(Boolean) dan 4 fitur kategorikal
- Dari EDA, kami mengetahui bahwa feature ‘AnnualIncome’ dan ‘EverTravelledAbroad’ memiliki korelasi yang lumayan tinggi dengan target feature yaitu ‘TravelInsurance’. 
- Ada banyak insights yang kami temukan yang nantinya bisa menjadi acuan untuk rekomendasi bisnis.
Stage 2
- Kami melakukan preprocessing agar dataset siap untuk dilakukan modelling
- Terdapat 1987 entries, tidak ada missing value dan duplicated value
- Kami menemukan bahwa feature ‘Unamed: 0’ tidak punya korelasi karena hanya berupa index sehingga kami drop
- Kami melakukan label encoding pada 4 feature kategorikal
Stage 3
- Kami melakukan assignment dimana X adalah variable feature dan y adalah variable target
- Feature transformation berupa normalizing diterapkan pada X
- Kami melakukan splitting train-test data sebagai input modelling
- Kami menerapkan beberapa modelling diantaranya Decision Tree Classifier, Random Forest Classifier, dan SVM
- Kami concern terhadap kondisi false negative sehingga evaluation metric yang kami gunakan adalah Recall
- Sejauh ini, model Decision Tree Classifier dengan balancing menggunakan undersampling dan dikenakan hyperparameter tuning memiliki nilai recall tertinggi, dengan  
  kenaikan sebesar 4% dari recall pada kondisi baseline (tanpa handling imbalance dan hyperparameter)

Stage 4 
- Membuat rekomendasi bisnis berdasarkan feature importance
