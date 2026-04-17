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

### Sonuç ve Yorumlar
Hocanın PDF notlarında tıp konusundaki tahminlerde en tehlikeli hatanın hastayı "sağlıklı" sanıp kaçırmak (Yanlış Negatif) olduğu yazıyordu. Bu yüzden ben en çok **Recall** (duyarlılık) değerine baktım. Testlerimde Logistic Regression hem genel başarıda hem de %74 Recall ile en mantıklı sonucu verdi.

### Kodlar Nasıl Çalıştırılır?
Repodaki .ipynb dosyasını indirip Google Colab'a yükledikten sonra veri setini de içine atınca bütün hücreler sırayla çalışıyor.
