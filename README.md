# Gaussian_Bayes_Algoritması_ve_Optimizasyonu
## GİRİŞ
Naive Bayes sınıflandırma, olasılık temelli bir sınıflandırma algoritmasıdır. Diyabet veri kümesi üzerinde bu algoritma uygulanarak, hastaların diyabet olup olmadığını tahmin etmeye çalışırız. Bu proje, bu sınıflandırma algoritmasının uygulanmasını, hiperparametre optimizasyonunu ve veri ön işleme adımlarını içerir.
## Metot
### Veri Yükleme ve Bölme:
İlk adım olarak, diyabet veri kümesi Pandas kütüphanesi ile yüklenir ve bağımsız değişkenler (X) ile bağımlı değişken (y) olarak ayrılır. Daha sonra veri seti eğitim ve test alt kümelerine ayrılır. Bu aşamada, veriye genel bir göz atış yapılır ve eksik verilerin olup olmadığı kontrol edilir.
### Model Eğitimi:
Gaussian Naive Bayes modeli kullanılarak eğitim verisiyle model eğitilir. Bu model, sınıflar arasındaki özelliklerin normal dağılıma sahip olduğunu varsayar. Bu varsayım modelin işlemlerinde basitlik sağlar. Ayrıca birçok gerçek dünya veri seti normal dağılım gösterir. Bu nedenle normal varsayım makul bir yaklaşımdır. Ve son olarak özellikler arasında yeterince bağımsızlık varsa ve normal dağılıma yakın bir dağılım gösteriyorsa iyi sonuçlar verir.
### Model Hiperparametre Optimizasyonu: 
İki farklı optimizasyon yöntemi kullanılarak hiperparametre optimizasyonu yapılır. İlk olarak Grid Search ve ardından Randomized Search yöntemi uygulanır. Grid Search, belirli bir hiperparametre aralığında tüm kombinasyonları deneyerek en iyi sonucu veren hiperparametreleri bulurken, Randomized Search rastgele seçilen bir alt kümeden deneme yaparak daha geniş bir arama alanını keşfeder.
### Veri Ön İşleme:
Veri ölçeklendirme ve normalleştirme adımları gerçekleştirilir. Veri ölçeklendirme, her bir özellik sütununu belirli bir aralığa yeniden ölçeklendirerek, algoritmanın daha iyi performans göstermesini sağlar. Normalleştirme ise verinin dağılımını değiştirerek, veri setindeki her bir özelliğin dağılımını belirli bir şekilde yeniden düzenler. Bu çalışmada, Standart Ölçekleme ve Power Transform yöntemleri kullanılmıştır. Burada Power Transformun tercih edilme nedeni Power Transform algoritması veri setinin dağılımını normal dağılıma yaklaştırır. Bu da Gaussian Naive Bayes algortimasının daha iyi sonuç vermesini sağlar.
### Model Performansının Değerlendirilmesi:
Her bir önişleme adımından sonra modelin performansı değerlendirilir. Performans ölçütleri arasında doğruluk (accuracy), karışıklık matrisi (confusion matrix) ve sınıflandırma raporu (classification report) bulunur.
## Sonuçlar ve Yorum
Grid Search ve Randomized Search yöntemleriyle en iyi hiperparametreler belirlenir. Veri önişleme adımları (ölçeklendirme ve normalleştirme) kullanılarak modelin performansı arttırılır. Her bir adımda elde edilen sonuçlar karşılaştırılarak en iyi modelin belirlenmesi sağlanır.
## Kullanılan Hiperparametrelerin Açıklaması
### var_smoothing: 
Gaussian Naive Bayes algoritmasında, varyansı sıfıra eşitlemek için veriye eklenen bir düzeltme terimi. Bu terim, varyansın sıfır olduğu durumlarda sınıflandırma hatalarını önler.
## Modelin Performansı
Veri Ön İşleme Uygulanmadan Önceki Doğruluk Skoru: 0.7362204724409449
Grid Search Sonrası Doğruluk Skoru: 0.7401574803149606
Randomized Search Sonrası Doğruluk Skoru: 0.7362204724409449
Standart Ölçekleme Sonrası Doğruluk Skoru: 0.7362204724409449
Power Transform Sonrası Doğruluk Skoru: 0.7716535433070866

Bu sonuçlara göre, veri ön işleme adımlarının (ölçeklendirme ve normalleştirme) modelin performansını artırdığını gözlemliyoruz. Özellikle Power Transform kullanıldığında, doğruluk skoru belirgin bir şekilde artmıştır.
## Repository'nin Kullanımı
Proje dizinine gidin. Gerekli kütüphaneleri yüklemek için pip install -r requirements.txt komutunu çalıştırın. diabetes.csv dosyasını yükleyin.
Naive_Bayes_Diabetes.ipynb dosyasını açarak çalıştırın veya terminalde python Naive_Bayes_Diabetes.py komutunu çalıştırarak sonuçları gözlemleyin.
