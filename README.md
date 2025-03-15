# Yorumlar uzerinden Restoran Performansinin Hedef ve Polarite Bazli Analizi
** DERLEM ÖZELLİKLERİ**

Seçtiğim derlem http://metashare.ilsp.gr:8080/repository/download/ff5dad70676311e5bf9c842b2b6a04d71fa7fa3ba4504a228dafe0c24560585b/ (SemEval-2016 ABSA Restaurant Reviews-Turkish: Train Data (Subtask 1))
İTU Doğal Dil İşleme grubu tarafından 2016 yılında restoran değerlendirmelerine ait toplamda 1317 cümleden içeren 320 tane döküman kullanılarak oluşturulmuştur.
Bu veri seti xml dosya formatı kullanılarak oluşturulmuştur.

** 1. ÇALIŞMANIN AMACI ve HEDEFİ**

Çalışmanın Amacı

Bu çalışmanın amacı, restoran yorumlarını analiz ederek hedef kategoriler (örneğin, servis, yemek, ambiyans) ve polarite (örneğin, olumlu, olumsuz, nötr) bazlı olarak restoran performansının genel bir resmini çıkarmaktır.Bu çalışmayla eğitilen model aynı zamanda restoran hakkında gelen yeni bir yorumun ait olabileceği hedef kategori ve polarite sınıflandırmasını duygu analizi ile yapabilmektedir


**2. Yöntem**

Çalışma kodlar ve metin satırlarını bir arada bulundurabilmesi özelliğinden dolayı Google Colab ile gerçekleştirilmiştir. Bir python not defteri oluşturularak her adım üzerinde açıklama yapılarak anlatılmıştır.
 sklearn kütüphanesi ile Büyük/küçük harf dönüşümü, noktalama işareti temizleme, stop words (Türkçe durak kelimeler) filtreleme gibi doğal dil işleme adımları yapılmıştır.Metinler, TF-IDF vektörizasyonuyla sayısal forma dönüştürülmüştür. Model RandomForest makine öğrenme modeli kullanılarak geliştirilmiştir. Veri okuma ve ön işleme aşamaları pandas kütüphanesi ile gerçekleştirilmiştir. python xml kütüphanesi ile google colab'a yüklediğimiz xml dosyasını açılıp, satır satır okunmuş ve İçindeki hali hazırda etiketlenmiş veriler bir dataframe'e  aktarılmıştır.

**2.1. Veri Okuma ,Data Frame oluşturma ve Veri Anlamlandırma**

 Veri okuma ve ön işleme aşamaları pandas kütüphanesi ile gerçekleştirilmiştir. python xml kütüphanesi ile google colab'a yüklediğimiz xml dosyasını açıp, satır satır okuyoruz. İçindeki hali hazırda etiketlenmiş verileri bir dataframe e aktarıyoruz.

Veri setinde veriler Text - Target - Category - Polarity olmak üzere 4 sütuna ayrılmıştır.
Text: Restoran hakkında yapılan yorum cümlesi.
Target: Yorumu ilgilendiren bölüm.
Category: Metinde bahsedilen hedefin nasıl daha geniş bir sınıfa dahil olduğunu belirtir.
Polarity: Metnin duygusunu ifade eden bölümdür.
