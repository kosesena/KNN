# KNN Sınıflandırması

K-En Yakın Komşu (KNN) algoritmasının üç farklı veri seti üzerinde uygulanması. Her notebook bağımsız çalışır ve farklı bir problem türünü ele alır.

---

## Veri Setleri

### 1. Iris — Çiçek Türü Sınıflandırması
**Notebook:** `KNN_Iris.ipynb`

| Özellik | Detay |
|---|---|
| Örnek Sayısı | 150 |
| Özellik Sayısı | 4 |
| Sınıf Sayısı | 3 (Setosa, Versicolor, Virginica) |
| Problem Türü | Çok sınıflı sınıflandırma |
| Özellikler | Sepal uzunluğu/genişliği, petal uzunluğu/genişliği (cm) |

**İçerik:**
- Özelliklerin türlere göre histogram dağılımı
- Korelasyon ısı haritası
- 5-fold cross-validation ile en iyi k seçimi
- Confusion matrix ve classification report

---

### 2. Wine — Şarap Üreticisi Sınıflandırması
**Notebook:** `KNN_Wine.ipynb`

| Özellik | Detay |
|---|---|
| Örnek Sayısı | 178 |
| Özellik Sayısı | 13 |
| Sınıf Sayısı | 3 (Üretici 1, 2, 3) |
| Problem Türü | Çok sınıflı sınıflandırma |
| Özellikler | Alkol, malik asit, kül, flavonoidler, renk yoğunluğu vb. |

**İçerik:**
- Temel özelliklerin kutu grafikleri (boxplot)
- 13 özellik arası korelasyon matrisi
- 5-fold cross-validation ile en iyi k seçimi
- Confusion matrix, classification report
- **PCA ile 2D görselleştirme**

---

### 3. Digits — El Yazısı Rakam Tanıma
**Notebook:** `KNN_Digits.ipynb`

| Özellik | Detay |
|---|---|
| Örnek Sayısı | 1797 |
| Özellik Sayısı | 64 (8×8 piksel) |
| Sınıf Sayısı | 10 (0–9 arası rakamlar) |
| Problem Türü | Görüntü sınıflandırma |
| Özellikler | Gri tonlamalı piksel yoğunlukları |

**İçerik:**
- Her rakamdan örnek görüntüler (8×8 piksel)
- Ortalama piksel yoğunluğu haritaları
- Sınıf dağılım grafiği
- 5-fold cross-validation ile en iyi k seçimi
- Confusion matrix (10×10)
- **PCA ile 2D görselleştirme**
- **Yanlış tahmin edilen örneklerin görselleştirilmesi**

---

## Ortak Metodoloji

Üç notebook'ta da aynı sistematik yaklaşım uygulanmaktadır:

1. **Veri Yükleme & Keşif** — boyut, sınıf dağılımı, temel istatistikler
2. **Görselleştirme** — veri setine özgü EDA grafikleri
3. **Normalizasyon** — Min-Max Scaler ile [0,1] aralığına ölçekleme
4. **Train-Test Split** — %70 eğitim / %30 test, stratified örnekleme
5. **Hiperparametre Optimizasyonu** — k=1..20 için 5-fold cross-validation
6. **Değerlendirme** — Accuracy, Precision, Recall, F1-Score, Confusion Matrix

---

## Kurulum

```bash
pip install numpy pandas matplotlib seaborn scikit-learn notebook
jupyter notebook
```

## Kullanım

Her notebook bağımsız çalışır, herhangi birini açıp tüm hücreleri çalıştırabilirsin.

```bash
jupyter notebook KNN_Iris.ipynb
jupyter notebook KNN_Wine.ipynb
jupyter notebook KNN_Digits.ipynb
```
