# Aygaz-Makine-Ogrenmesi-Bootcamp-Proje-Odevi
#Proje Kaggle Linki: https://www.kaggle.com/code/erenefeorhan/ml-ipynb
# Proje Özeti

Bu projede, **denetimli (supervised)** ve **denetimsiz (unsupervised)** öğrenme algoritmaları, aynı veri seti üzerinde çalıştırılarak performansları karşılaştırılmıştır. Veri seti finansal işlemler üzerindeki sahtekarlık tespitine yöneliktir ve her iki öğrenme türüyle incelenmiştir.

## Veri Seti
Veri seti, belirli özelliklere dayalı olarak finansal işlemlerin sahte (fraud) ya da gerçek (non-fraud) olduğunu belirlemeyi amaçlayan bir yapıya sahiptir. Veri seti, işlemin türü, miktarı, işlemden önce ve sonra bakiyeler gibi hem sayısal hem de kategorik değişkenler içermektedir. İlgili veri seti sahtekarlık tespiti problemi için oldukça uygun bir yapıya sahiptir.

- **Denetimli Öğrenme**: Özellikle hedef değişken olan 'isFraud' sahtekarlık olup olmadığını belirten etiketli veri ile çalışır.
- **Denetimsiz Öğrenme**: Etiketli veriye ihtiyaç duymadan, verideki doğal kümeleri veya anomalileri tespit eder.

## Algoritmaların Performansı

### Denetimli Öğrenme: Karar Ağaçları (Decision Tree)
Karar Ağaçları modeli, GridSearchCV ile optimize edilmiş hiperparametreler kullanılarak eğitildi. Modelin doğruluk oranı %99 üzerinde çıktı ve modelin sınıflandırma performansı oldukça başarılı oldu. 

- **Precision (Doğruluk)**: %91
- **Recall (Duyarlılık)**: %72
- **F1-Score**: %80

Veri setindeki dengesizlik (fraud işlemlerin çok az olması) nedeniyle, model zaman zaman "fraud" sınıflarını doğru tahmin etmekte zorlandı. Ancak genel olarak, model denetimli öğrenme için çok iyi bir sonuç verdi.

### Denetimsiz Öğrenme: K-Ortalamalar (K-Means)
Veri setinde, denetimsiz öğrenme algoritması olarak K-Means kullanıldı. K-Means, veri setini sahte ve gerçek işlemler olarak ikiye ayırmayı denedi. Ancak, etiketli veri olmadığından, algoritmanın sahtekarlık işlemlerini doğru tespit etmesi beklenenden zayıf oldu.

Sonuç olarak, denetimsiz öğrenme modelinin genel doğruluk performansı oldukça düşük oldu, çünkü veri setindeki işlem örüntüleri açıkça bir sınıfa dayalı olmadığı için model kümeleri doğru şekilde ayıramadı.

## Sonuç
Bu projede her iki öğrenme algoritması da test edilmiştir, ancak veri setinin doğası gereği **denetimli öğrenme algoritması** olan Karar Ağaçları modeli çok daha iyi sonuç vermiştir. Sahtekarlık tespiti gibi etiketli ve belirgin bir hedefin olduğu veri setlerinde denetimli öğrenme algoritmaları daha başarılıdır. Bununla birlikte, denetimsiz öğrenme algoritması olan K-Means gibi yöntemler, sadece belirli durumlarda yararlı olabilir.

**Sonuç olarak**, bu veri seti ve problem tipi, denetimli öğrenme algoritmaları için daha uygundur. Etiketli verinin varlığı ve sahtekarlık tespiti gibi belirgin bir hedef, denetimli modellerin gücünü öne çıkarmaktadır.
