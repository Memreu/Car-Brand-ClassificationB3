# Car Brand Classification Using EfficientNet-B3

## 1. Başlık ve Özet  
Bu çalışma, derin öğrenme tabanlı bir görüntü sınıflandırma yaklaşımı ile otomobil marka tanıma problemini çözmeyi hedeflemektedir. EfficientNet-B3 mimarisi, transfer öğrenme yöntemi ve veri artırma stratejileri kullanılarak sınıflandırma performansı optimize edilmiştir. Proje, otomobil görsellerinden marka tahmini yapabilen bir model geliştirerek bilgisayarla görme alanında literatüre katkı sunmayı amaçlamaktadır.

## 2. Giriş  
Otomotiv sektöründe markaların otomatik olarak tanınması, stok yönetiminden pazarlama analizlerine kadar çeşitli uygulama alanlarına sahiptir. Derin öğrenme mimarilerinin görüntü sınıflandırma performansları, geleneksel yöntemlere kıyasla kayda değer şekilde artmıştır. Bu proje, EfficientNet-B3’ün verimlilik ve doğruluk dengesinden yararlanarak otomobil markalarını yüksek doğrulukla sınıflandırmayı amaçlamaktadır.

## 3. Veri Seti  
Projede çeşitli otomobil markalarına ait etiketlenmiş görüntüler içeren bir veri seti kullanılmıştır. Görseller farklı açılardan ve koşullardan elde edilmiştir. Veri seti eğitim, doğrulama ve test alt kümelerine bölünmüş, veri dengesizliğini azaltmak için sınıf dağılımları incelenmiştir.

## 4. Ön İşlem ve Veri Artırma  
Görseller öncelikle belirli bir çözünürlüğe (EfficientNet-B3 girdi boyutu) yeniden boyutlandırılmış ve normalize edilmiştir. Veri artırma stratejileri (örneğin rastgele döndürme, yatay çevirme, parlaklık/kontrast ayarı vb.) modelin genelleme kabiliyetini artırmak ve aşırı uyum (overfitting) riskini azaltmak için uygulanmıştır.

## 5. Model ve Yöntem  
Modelin temelini EfficientNet-B3 mimarisi oluşturmaktadır. Önceden eğitilmiş ImageNet ağırlıkları yüklenerek transfer öğrenme gerçekleştirilmiş ve üst katmanlara tam bağlantılı sınıflandırıcı eklenmiştir. Optimizasyon için genellikle Adam veya SGD gibi optimizatörler ve uygun öğrenme oranı stratejileri kullanılmıştır. Erken durdurma ve düzenlileştirme teknikleri (dropout vb.) aşırı uyumu önlemek için uygulanmıştır.

## 6. Deneysel Kurulum  
- **Veri Bölünmesi:** Eğitim/Doğrulama/Test setleri  
- **Batch Size / Epoch:** Uygun değerler belirlenerek modelin eğitim dengesi sağlanmıştır  
- **Çalışma Ortamı:** GPU destekli bir derin öğrenme ortamı (CUDA + PyTorch/TensorFlow)  
- **Rastgelelik:** Tekrarlanabilirlik için seed ayarları yapılmıştır  

## 7. Sonuçlar ve Değerlendirme  
Modelin doğruluk, precision, recall ve F1-score metrikleri hesaplanmıştır. Eğitim ve doğrulama kayıpları ile doğruluk grafikleri incelenmiş, modelin karışıklık matrisi üzerinden sınıf bazlı performansı analiz edilmiştir.  

- **Eğitim Doğruluğu (Train Acc): 0.8368**  
- **Doğrulama Doğruluğu (Val Acc): 0.7317**  

Bu sonuçlar, modelin eğitim verisi üzerinde tatmin edici bir performansa ulaştığını, ancak doğrulama setinde daha düşük doğruluk elde ettiğini göstermektedir. Bu fark, modelin sınırlı ölçüde aşırı uyum (overfitting) eğiliminde olabileceğini işaret etmektedir. Veri artırma tekniklerinin daha yoğun kullanımı veya hiperparametre optimizasyonu ile doğrulama performansı iyileştirilebilir. Yine de, elde edilen doğruluk oranları otomobil markalarının görsel özelliklerine dayalı sınıflandırma için güçlü bir temel sunmaktadır.

## 8. Kullanım Talimatları  
1. Gerekli bağımlılıkları yükleyin (`requirements.txt` veya environment.yml)  
2. Veri setini belirtilen dizine yerleştirin  
3. Eğitim için `train.py` veya notebook içindeki hücreleri çalıştırın  
4. Model ağırlıklarını kaydedip daha sonra tahmin yapmak için `inference.py` veya ilgili notebook hücrelerini kullanın  

## 9. Dosya Yapısı  
```
├── car-brand-classification-using-efficientnet-b3.ipynb  # Ana notebook
├── data/                                                 # Veri seti klasörü
├── models/                                               # Kaydedilmiş modeller
├── results/                                              # Eğitim sonuçları ve grafikler
└── README.md                                             # Bu dosya
```
