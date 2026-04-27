# COVID-19 Tahmin Ödevi

Kaggle üzerinden aldığım COVID-19 veri setini kullanarak, bir kişinin semptomlarına göre hasta olup olmadığını tahmin eden bir çalışma yaptım. Ödev kapsamında derste gördüğümüz 4 farklı algoritmayı karşılaştırdım.

Veri Seti: [Kaggle - COVID-19 Dataset](https://www.kaggle.com/datasets/meirnizri/covid19-dataset)

### Veri Ön İşleme Adımları
* **Temizlik:** Verideki 97, 98 ve 99 gibi ne olduğu belli olmayan değerleri ayıkladım. "DATE_DIED" sütunu da çok fazla boşluk içerdiği için analizi etkilememesi adına sildim.
* **Ölçeklendirme:** KNN gibi modellerin mesafe mantığıyla doğru çalışması için StandardScaler kullandım. Notlarda bu adımın kritik olduğunu görmüştüm.

### Kullanılan Algoritmaların Mantığı
Ödevde istenen 4 modeli de denedim:
1. **Logistic Regression:** Sınıflandırma için en temel doğrusal yöntem olduğu için.
2. **KNN:** Verilerin birbirine yakınlığına göre tahmin yaptığı için.
3. **Decision Tree:** Karar kuralları oluşturarak sonucu dallandırdığı için.
4. **Random Forest:** Birçok ağacı birleştirip daha sağlam sonuç verdiği için.

### Model Performans Karşılaştırması
Kodları çalıştırdığımda çıkan gerçek rakamlar şu şekilde oldu:

| Algoritma | Accuracy | Precision | Recall |
| :--- | :--- | :--- | :--- |
| **Logistic Regression** | **%63.2** | 0.63 | 0.74 |
| **Random Forest** | %59.7 | 0.61 | 0.66 |
| **KNN** | %59.1 | 0.61 | 0.66 |
| **Decision Tree** | %58.8 | 0.61 | 0.61 |

### Modellerin Analizi ve Karşılaştırma
Veri setini temizleyip modelleri eğittiğimde, Logistic Regression algoritmasının diğerlerinden daha tutarlı sonuçlar verdiğini gördüm. Accuracy bazında %63.2 ile en yüksek başarıyı bu model sağladı. Karar ağaçları (Decision Tree) ve Random Forest modelleri bu veri setinde beklediğimden biraz daha düşük performans gösterdi.

### Sonuç
Bu çalışmada benim için en önemli kriter **Recall** (Duyarlılık) değeriydi. Çünkü tıp ile ilgili bir konuda, hasta olan birine yanlışlıkla "sağlıklı" demek (Yanlış Negatif hatası) çok riskli bir durum. Bu yüzden Accuracy değerinin yanında Recall değerine de baktım.

Logistic Regression modeli %74 Recall başarısı göstererek, hasta olan kişileri tespit etme konusunda denediğim diğer 3 algoritmanın önüne geçti. Hem genel doğruluğu hem de hastaları yakalama kapasitesi bakımından bu veri seti için en mantıklı çözümün Logistic Regression olduğuna karar verdim.

### Kodlar Nasıl Çalıştırılır?
Repodaki .ipynb dosyasını indirip Google Colab'a yükledikten sonra veri setini de içine atınca bütün hücreler sırayla çalışıyor.
