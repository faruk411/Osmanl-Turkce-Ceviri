## Projenin Açıklaması

Bu projemde, benim oluşturduğum veri setinde Osmanlı Türkçesi kelimeler içeren görüntüleri modern Türkçeye çevirebilen bir yapay zeka modeli geliştirdim. Model, Convolutional Neural Networks (CNN) ve Long Short-Term Memory (LSTM) ağlarını içeren bir encoder-decoder mimarisi kullanmaktadır.

MODELİN YAPISI

Model, Görüntüden Metin Çıkarımı (OCR) ve Çeviri olmak üzere iki aşamadan oluşmaktadır.

● OCR Aşaması: CNN ile görsel özellikler çıkarılır, ardından LSTM ile sıralı karakter tanıma yapılır.

Çeviri Aşaması:
● CNN’den gelen vektörler, kelime dizileriyle birleştirilir.
● LSTM tabanlı bir dil modeli, Osmanlı Türkçesi kelimelerini modern Türkçeye çevirir.
● Çıktı katmanında softmax aktivasyonu ile kelime tahmini yapılır.

Bu yapı sayesinde model, hem görsel hem de dil verisini etkili kullanarak yüksek doğrulukla çeviri yapmaktadır.

MODEL EĞİTİMİ
Eğitim sürecinde Adam optimizer, sparse categorical crossentropy ve çeviri doğruluk metriği ROUGE-1 -- ROUGE-2 -- ROUGE-L kullanılmıştır. Eğitim için GPU hızlandırmalı TensorFlow/Keras kütüphaneleri kullanılmıştır.

SONUÇ
Eğitilen modelin test doğruluk oranı 97% test kaybı 0.23 olarak ölçülmüştür. Doğruluk metriklerin sonuçları ise: 
 ● ROUGE-1 : 0.91
 ● ROUGE-2 : 0.50
 ● ROUGE-L : 0.91

Çeşitli test veri kümeleri üzerinde yapılan değerlendirmelerde modelin başarılı olduğu gözlemlenmiştir.

### Modelin çıktısı

![Ekran görüntüsü 2025-02-06 135238](https://github.com/user-attachments/assets/32436661-0452-4653-92a2-63abc1c48786)
