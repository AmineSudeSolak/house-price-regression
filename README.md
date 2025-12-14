House Price Prediction with Multiple Linear Regression
Çoklu Doğrusal Regresyon ile Ev Fiyat Tahmini

🇬🇧 English
Project Objective

This project aims to predict house sale prices using the Ames Housing dataset.
The main goal is to build a solid baseline model with multiple linear regression, evaluate its limitations, and justify each modeling decision through analytical reasoning.

This project is not competition-oriented; instead, it focuses on demonstrating the learning process and a structured approach to regression modeling.

Dataset

Source: Kaggle – House Prices: Advanced Regression Techniques

File used: train.csv

Number of observations: 1460

Number of features: 80+

The dataset contains both numerical and categorical variables.

The provided test.csv file was not used in this project, as it does not include the true target variable (SalePrice) and is intended only for Kaggle competition submissions.

Exploratory Data Analysis (EDA)

Initial analysis of the target variable SalePrice revealed a left-skewed distribution.
Since this violates linear regression assumptions, a log transformation was applied to the target variable.

The purpose of this transformation was to:

Reduce the influence of outliers

Stabilize the variance

Improve model reliability

Missing Value Analysis

Missing values were not treated uniformly across all features.
Each variable was evaluated based on whether the missing value represented actual missing data or the absence of a property characteristic.

For example:

Variables such as Neighborhood are mandatory and should not be interpreted as missing

Variables like FireplaceQu or PoolQC may indicate that the property does not include that feature

This approach ensured that missing values were handled in a context-aware manner.

Modeling Process
Baseline Model

A baseline model was built using numerical features only.
This step was designed to assess how much predictive power numerical variables provide before introducing additional complexity.

Model: Linear Regression

Target variable: log(SalePrice)

Results:

R² Score: 0.876

RMSE (log-scale): 0.152

These results indicate that numerical features alone explain a large portion of the variance in house prices.

Categorical Feature Experiment

In the next step, selected categorical variables were added to the model:

Neighborhood

ExterQual

KitchenQual

These variables were encoded using one-hot encoding.
However, no significant improvement in model performance was observed compared to the baseline model.

This suggests that the numerical features already capture most of the relevant information and that linear regression has limitations in modeling complex categorical effects.

Evaluation

Rather than forcing performance improvements, this project emphasizes understanding why certain changes do or do not impact model results.

The absence of performance improvement after adding categorical features reflects a conscious and analytical modeling approach.

Technologies Used

Python

Pandas

NumPy

Matplotlib

Seaborn

Scikit-learn

🇹🇷 Türkçe
Projenin Amacı

Bu projede Ames Housing veri seti kullanılarak ev satış fiyatlarının tahmin edilmesi amaçlanmıştır.
Çalışmanın temel amacı, çoklu doğrusal regresyon kullanarak sağlam bir baseline model oluşturmak, bu modelin sınırlarını gözlemlemek ve yapılan her adımı gerekçeleriyle değerlendirmektir.

Bu proje bir Kaggle yarışması odaklı değil; öğrenme sürecini ve analitik düşünme yaklaşımını göstermeyi hedeflemektedir.

Kullanılan Veri Seti

Kaynak: Kaggle – House Prices: Advanced Regression Techniques

Kullanılan dosya: train.csv

Gözlem sayısı: 1460

Özellik sayısı: 80+

Veri seti hem sayısal hem de kategorik değişkenler içermektedir.

Kaggle tarafından sağlanan test.csv dosyası, gerçek hedef değişken (SalePrice) içermediği için bu çalışmada kullanılmamıştır. Bu dosya yalnızca yarışma ortamında tahmin üretmek amacıyla tasarlanmıştır.

Keşifsel Veri Analizi (EDA)

Hedef değişken olan SalePrice incelendiğinde dağılımın sola çarpık olduğu görülmüştür.
Bu durum doğrusal regresyon varsayımlarını olumsuz etkileyebileceği için hedef değişkene log dönüşümü uygulanmıştır.

Log dönüşümünün amacı:

Aykırı değerlerin etkisini azaltmak

Hata dağılımını daha dengeli hale getirmek

Modelin daha kararlı sonuçlar üretmesini sağlamak

Eksik Değer Analizi

Veri setindeki eksik değerler tek tip olarak ele alınmamıştır.
Her değişken, eksikliğin anlamı açısından ayrı ayrı değerlendirilmiştir.

Örneğin:

Neighborhood gibi değişkenler her ev için zorunludur ve “yok” olarak kabul edilmemelidir

FireplaceQu, PoolQC gibi değişkenler evde bu özelliğin bulunmamasını temsil edebilir

Bu nedenle eksik değerler kör şekilde doldurulmamış, değişkenlerin gerçek hayattaki karşılıkları dikkate alınmıştır.

Modelleme Süreci
Baseline Model

İlk aşamada yalnızca sayısal değişkenler kullanılarak bir baseline model oluşturulmuştur.
Bu adımın amacı, daha karmaşık işlemler yapılmadan önce sayısal özelliklerin tahmin gücünü gözlemlemektir.

Model: Linear Regression

Hedef değişken: log(SalePrice)

Model sonuçları:

R²: 0.876

RMSE (log-scale): 0.152

Bu sonuçlar, sayısal değişkenlerin ev fiyatlarını açıklamada oldukça güçlü olduğunu göstermektedir.

Kategorik Değişkenlerin Eklenmesi

Bir sonraki adımda, ev fiyatını etkileyebileceği düşünülen bazı kategorik değişkenler modele eklenmiştir:

Neighborhood

ExterQual

KitchenQual

Bu değişkenler one-hot encoding yöntemiyle sayısal hale getirilmiştir.
Ancak model performansı baseline modele kıyasla anlamlı bir iyileşme göstermemiştir.

Bu durum, sayısal değişkenlerin fiyat bilgisinin büyük bir kısmını zaten temsil ettiğini ve doğrusal regresyon modelinin kategorik değişkenlerin karmaşık etkilerini sınırlı şekilde yakalayabildiğini göstermektedir.

Değerlendirme

Bu projede amaç, model skorunu zorla artırmak değil; neden artmadığını analiz edebilmektir.

Kategorik değişkenler eklenmesine rağmen performansın değişmemesi, modelin sınırlarının ve veri setinin yapısının doğru şekilde anlaşıldığını göstermektedir.

Kullanılan Teknolojiler

Python

Pandas

NumPy

Matplotlib

Seaborn

Scikit-learn

Seaborn

Scikit-learn
