Projenin Amacı
Veri setindeki çeşitli özelliklere (konut yaşı, oda sayısı, konum vb.) dayanarak bir evin piyasa değerini doğru bir şekilde tahmin etmek ve en yüksek performansı gösteren regresyon modelini belirlemektir.

Metodoloji
Proje, standart bir veri bilimi iş akışını takip etmektedir:

Veri Hazırlığı ve Ön İşleme:

Eksik değerler (total_bedrooms) medyan ile dolduruldu.

median_house_value sütunundaki aykırı değerler temizlendi.

Kategorik ocean_proximity özelliği one-hot encoding ile sayısal hale getirildi.

Özellik Mühendisliği (Feature Engineering):

Modelin tahmin gücünü artırmak için hane başına düşen oda sayısı gibi yeni ve anlamlı özellikler türetildi.

Veri Dönüşümü:

Veri dağılımının normalleşmesini sağlamak amacıyla PowerTransformer (Yeo-Johnson) dönüşümü uygulandı.

Model Karşılaştırması ve Optimizasyon:

Proje, bir baseline modeli olarak Linear Regression ile başladı.

Ardından Random Forest ve XGBoost gibi ağaç tabanlı, güçlü regresyon modelleri test edildi.

En iyi performansı veren modeli bulmak için RandomizedSearchCV ile hiperparametre optimizasyonu yapıldı.

Elde Edilen Sonuçlar
Farklı modellerin test verisi üzerindeki R² skorları aşağıdaki gibidir:

Model	R² Skoru	Açıklama
Linear Regression	~0.61	Düşük performans gösterdi.
Random Forest	~0.79	Performansı önemli ölçüde artırdı.
XGBoost	~0.826	En iyi başlangıç skorunu verdi.
XGBoost (Ayarlanmış)	~0.828	Optimizasyonla en yüksek performansa ulaştı.

E-Tablolar'a aktar
Sonuç olarak, XGBoost modelinin bu veri setinde en yüksek tahmin doğruluğunu sunduğu gözlemlenmiştir.

Kullanılan Teknolojiler
Python

Pandas

NumPy

Scikit-learn

XGBoost

Matplotlib

Seaborn
