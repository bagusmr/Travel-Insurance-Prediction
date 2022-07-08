This is a final project assignment from Rakamin Academy based on Kaggle dataset 2019

# Travel-Insurance-Prediction
This is a final project of data science bootcamp on Rakamin Academy which consist of EDA, preprocessing, and modelling of Travel Insurance Prediction data based on Kaggle dataset on 2019
# Lucky-7
Anggota : 
- Bagus Maulidika Rofi ( Ketua )
- Irfan Divi Zianka
- Tristan Matias
- Muthia Sofi
- Rifki Muhammad
Final Project Batch 21 - Travel Insurance
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
