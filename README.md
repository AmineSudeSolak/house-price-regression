#  House Price Prediction with Multiple Linear Regression

## Çoklu Doğrusal Regresyon ile Ev Fiyat Tahmini

---

## 🇬🇧 English

### Project Overview

This project focuses on predicting house sale prices using the **Ames Housing dataset**. Rather than aiming for leaderboard performance, the goal is to demonstrate a **clear modeling workflow**, starting from exploratory analysis and ending with a well-justified baseline regression model.

The emphasis is on *why* certain modeling decisions are made, not only *how* they are implemented.

---

### Dataset

* **Source:** Kaggle – *House Prices: Advanced Regression Techniques*
* **File used:** `train.csv`
* **Observations:** 1460
* **Features:** 80+

The dataset includes both numerical and categorical variables describing residential properties.

The provided `test.csv` file was **not used** in this project, as it does not contain the target variable (`SalePrice`) and is intended solely for Kaggle competition submissions.

Dataset link:
[https://www.kaggle.com/datasets/rishitaverma02/house-prices-advanced-regression-techniques](https://www.kaggle.com/datasets/rishitaverma02/house-prices-advanced-regression-techniques)

Due to licensing and distribution restrictions, the raw dataset files are not included in this repository.

---

### Exploratory Data Analysis (EDA)

Initial inspection of the target variable (`SalePrice`) revealed a **left-skewed distribution**. Since linear regression assumes normally distributed errors, a **log transformation** was applied to the target variable.

This transformation was applied to:

* Reduce the influence of extreme values
* Stabilize variance
* Improve the robustness and interpretability of the model

---

### Missing Value Analysis

Missing values were handled based on **feature semantics**, not with a single blanket strategy.

Examples:

* Variables such as `Neighborhood` are mandatory attributes and should not be interpreted as missing information.
* Variables like `FireplaceQu` or `PoolQC` often indicate the *absence* of that feature rather than missing data.

This approach ensures that data cleaning decisions remain consistent with real-world meaning.

---

### Modeling Process

#### Baseline Model

A baseline model was constructed using **numerical features only**. The purpose of this step was to measure the predictive strength of numeric variables before introducing additional complexity.

* **Model:** Linear Regression
* **Target variable:** `log(SalePrice)`

**Results:**

* R² Score: **0.876**
* RMSE (log-scale): **0.152**

These results indicate that numerical features alone explain a substantial portion of the variance in house prices.


#### Categorical Feature Experiment

In a subsequent step, selected categorical variables believed to influence house prices were added to the model:

* `Neighborhood`
* `ExterQual`
* `KitchenQual`

These variables were encoded using **one-hot encoding**. However, the inclusion of these features did **not** lead to a meaningful improvement in model performance.

This outcome suggests that:

* Numerical features already capture most of the price-related information
* Linear regression has limited capacity to model complex categorical interactions

---

### Evaluation and Takeaways

Instead of forcing performance improvements, this project prioritizes **understanding model behavior**.

The lack of improvement after adding categorical features highlights the importance of:

* Establishing strong baselines
* Interpreting results critically
* Recognizing model limitations

---

### Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

---

## 🇹🇷 Türkçe

### Proje Özeti

Bu proje, **Ames Housing veri seti** kullanılarak ev satış fiyatlarının tahmin edilmesini amaçlamaktadır. Çalışma bir Kaggle yarışmasına odaklanmak yerine, **doğru ve gerekçeli bir modelleme sürecini** göstermeyi hedefler.

Amaç, yalnızca bir model kurmak değil; yapılan her adımın *neden* gerekli olduğunu açıklayabilmektir.

---

### Veri Seti

* **Kaynak:** Kaggle – *House Prices: Advanced Regression Techniques*
* **Kullanılan dosya:** `train.csv`
* **Gözlem sayısı:** 1460
* **Özellik sayısı:** 80+

Veri seti, konutlara ait hem sayısal hem de kategorik değişkenler içermektedir.

Kaggle tarafından sağlanan `test.csv` dosyası, hedef değişken (`SalePrice`) içermediği için bu projede **kullanılmamıştır**. Bu dosya yalnızca yarışma ortamında tahmin üretmek amacıyla tasarlanmıştır.

Veri seti bağlantısı:
[https://www.kaggle.com/datasets/rishitaverma02/house-prices-advanced-regression-techniques](https://www.kaggle.com/datasets/rishitaverma02/house-prices-advanced-regression-techniques)

Lisans ve paylaşım kısıtları nedeniyle veri dosyaları bu repoya eklenmemiştir.

---

### Keşifsel Veri Analizi (EDA)

Hedef değişken olan `SalePrice` incelendiğinde dağılımın **sola çarpık** olduğu gözlemlenmiştir. Bu durum doğrusal regresyon varsayımlarını olumsuz etkileyebileceği için hedef değişkene **log dönüşümü** uygulanmıştır.

Bu dönüşümün amacı:

* Aykırı değerlerin etkisini azaltmak
* Varyansı dengelemek
* Model çıktılarının daha kararlı olmasını sağlamak

---

### Eksik Değer Analizi

Eksik değerler tüm değişkenler için aynı şekilde ele alınmamıştır. Her değişken, gerçek hayattaki anlamı dikkate alınarak değerlendirilmiştir.

Örnekler:

* `Neighborhood` gibi değişkenler her ev için zorunludur ve eksik olarak yorumlanmamalıdır.
* `FireplaceQu` veya `PoolQC` gibi değişkenlerdeki eksiklikler, evde bu özelliğin bulunmadığını gösterebilir.

Bu yaklaşım, veri temizleme sürecinin daha anlamlı ve tutarlı olmasını sağlamıştır.

---

### Modelleme Süreci

#### Baseline Model

İlk aşamada yalnızca **sayısal değişkenler** kullanılarak bir baseline model oluşturulmuştur. Amaç, daha karmaşık yöntemlere geçmeden önce sayısal değişkenlerin tahmin gücünü ölçmektir.

* **Model:** Linear Regression
* **Hedef değişken:** `log(SalePrice)`

**Model sonuçları:**

* R²: **0.876**
* RMSE (log-scale): **0.152**

Bu sonuçlar, sayısal değişkenlerin ev fiyatlarını açıklamada oldukça güçlü olduğunu göstermektedir.


#### Kategorik Değişken Denemesi

Bir sonraki adımda, ev fiyatını etkileyebileceği düşünülen bazı kategorik değişkenler modele eklenmiştir:

* `Neighborhood`
* `ExterQual`
* `KitchenQual`

Bu değişkenler one-hot encoding yöntemiyle sayısal hale getirilmiştir. Ancak baseline modele kıyasla anlamlı bir performans artışı gözlemlenmemiştir.

Bu durum, sayısal değişkenlerin fiyat bilgisinin büyük bir bölümünü zaten temsil ettiğini ve doğrusal regresyonun kategorik karmaşıklıkları sınırlı şekilde yakalayabildiğini göstermektedir.

---

### Değerlendirme ve Çıkarımlar

Bu projede amaç, model skorunu zorla artırmak değil; **neden artmadığını anlayabilmektir**.

Kategorik değişkenlerin eklenmesine rağmen performansın değişmemesi, modelin sınırlarının ve veri setinin yapısının doğru şekilde yorumlandığını göstermektedir.

---

### Kullanılan Teknolojiler

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
