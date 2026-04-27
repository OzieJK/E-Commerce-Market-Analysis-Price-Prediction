# 📊 E-Commerce Market Analysis & Price Prediction

Bu proje, Kaggle üzerindeki çok parçalı bir e-ticaret veri setini kullanarak; veri entegrasyonu, gelişmiş veri temizleme teknikleri, keşifçi veri analizi (EDA) ve makine öğrenmesi süreçlerini kapsayan uçtan uca bir veri bilimi çalışmasıdır.

## 🎯 Projenin Amacı
Farklı kategorilerdeki binlerce ürünün fiyat dağılımını analiz etmek ve ürün özelliklerinin (reyting, indirim oranı vb.) satış fiyatı üzerindeki etkisini matematiksel modellerle ortaya koymaktır.

## 🛠 Kullanılan Teknolojiler
* **Python 3.x**
* **Pandas:** Veri manipülasyonu ve entegrasyonu.
* **Matplotlib & Seaborn:** İstatistiki görselleştirme ve veri keşfi.
* **Scikit-Learn:** Doğrusal regresyon (Linear Regression) modellemesi.
* **NumPy:** Sayısal veri işlemleri.
* **Regex (Düzenli İfadeler):** Ham metin verilerinin temizlenmesi.

## 🚀 Proje Hattı (Pipeline)

### 1. Veri Entegrasyonu ve Otomasyon
Dataset, kategorilere ayrılmış çok sayıda CSV dosyasından oluşmaktadır. `glob` kütüphanesi kullanılarak tüm dosyalar otomatik olarak tarandı. Her ürünün kategorisi, dosya adından dinamik olarak çekilerek ana veri setine yeni bir öznitelik (feature) olarak eklendi.

### 2. Veri Temizleme (Data Wrangling)
Ham verinin analiz edilebilir hale getirilmesi için şu teknikler uygulandı:
- **Para Birimi Temizliği:** Fiyat sütunlarındaki özel semboller (`₹`, `,`) RegEx kullanılarak temizlendi.
- **Tip Dönüşümü:** Sayısal olması gereken metin verileri `float64` formatına dönüştürüldü.
- **Eksik Veri Yönetimi:** Analizi bozabilecek `NaN` değerler, veri kaybını minimize edecek şekilde filtrelendi.

### 3. Keşifçi Veri Analizi (EDA)
- **Kategori Analizi:** Ürün gruplarının fiyat ortalamaları ve standart sapmaları incelendi.
- **Korelasyon Analizi:** Fiyat, indirim oranı ve reyting arasındaki ilişkiler Pearson korelasyon katsayısı ile hesaplandı.

### 4. Makine Öğrenmesi
Ürünlerin **reyting** ve **indirim oranlarını** girdi (X) olarak kullanarak **final_price** tahmini yapan bir **Linear Regression** modeli eğitildi. 
- Veri seti %80 eğitim, %20 test olarak ayrıldı.
- Model performansı **R2 Score** ve **MAE** metrikleri ile değerlendirildi.

## 📈 Önemli Bulgular
- Ürün puanı (rating) ile fiyat arasında doğrusal bir bağın zayıf olması, fiyatlandırmanın marka değeri ve materyal kalitesi gibi dış faktörlere daha duyarlı olduğunu göstermektedir.
- Bazı kategorilerdeki yüksek fiyat varyansı, ilgili kategorideki lüks ve ekonomik segment ayrımının keskinliğini kanıtlamaktadır.

## 📂 Dosya Yapısı
- `data/`: Ham CSV dosyalarının bulunduğu dizin.
- `E-Commerce Analys.ipynb`: Tüm analiz ve modelleme kodlarını içeren Jupyter Notebook.
- `requirements.txt`: Projenin çalışması için gerekli kütüphaneler.
