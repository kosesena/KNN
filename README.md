<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=200&section=header&text=KNN%20Classification&fontSize=50&fontColor=fff&animation=twinkling&fontAlignY=35&desc=K-En%20Yakın%20Komşu%20%7C%203%20Farklı%20Veri%20Seti&descAlignY=55&descSize=18"/>

<br/>

[![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.x-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org/)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)

<br/>

[![Course](https://img.shields.io/badge/Ders-Veri%20Madenciliği%20Laboratuvarı-8A2BE2?style=for-the-badge&logo=academia&logoColor=white)]()

> **K-En Yakın Komşu (KNN)** algoritmasının üç farklı gerçek dünya veri seti üzerinde,
> tutarlı bir metodoloji ile uygulanması ve karşılaştırılması.
>
> 📚 Bu çalışma **Veri Madenciliği Laboratuvarı** dersi kapsamında hazırlanmıştır.

<br/>

</div>

---

## 🎯 Bu Proje Ne Öğretiyor?

Bu proje, makine öğrenmesine yeni başlayanlar için **teoriden pratiğe eksiksiz bir KNN rehberi** olmayı hedefler.

<details>
<summary><b>🧠 Kavramsal Öğrenme Hedefleri</b></summary>

<br/>

**1. KNN Algoritmasını Anlamak**
- "En yakın komşu" mantığının geometrik sezgisi nedir?
- k sayısı küçük olunca ne olur, büyük olunca ne olur?
- Neden veri normalizasyonu KNN için kritiktir?

**2. Veri Ön İşleme**
- Ham veriyi modele hazır hale getirme adımları nelerdir?
- Min-Max normalizasyonu neden Öklid mesafesini etkiler?
- Stratified split neden rastgele split'ten daha güvenilirdir?

**3. Hiperparametre Optimizasyonu**
- k değerini tahmin etmek yerine veriye dayalı nasıl seçeriz?
- Cross-validation neden tek bir test setinden daha güvenilirdir?
- Overfitting / Underfitting grafikte nasıl görünür?

**4. Model Değerlendirme**
- Accuracy tek başına yeterli midir?
- Precision, Recall ve F1-Score ne zaman önemlidir?
- Confusion matrix'ten hangi hatalar okunabilir?

**5. Boyut İndirgeme (PCA)**
- 13 veya 64 boyutlu veriyi gözle nasıl görürüz?
- PCA varyansın ne kadarını korur?

</details>

<details>
<summary><b>🔬 Pratik Beceri Hedefleri</b></summary>

<br/>

| Beceri | Nerede Uygulanıyor |
|---|---|
| `pandas` ile veri okuma ve keşif | Tüm notebook'lar |
| `matplotlib` & `seaborn` ile görselleştirme | Tüm notebook'lar |
| `MinMaxScaler` ile normalizasyon | Tüm notebook'lar |
| `train_test_split` ile stratified bölme | Tüm notebook'lar |
| `cross_val_score` ile k arama | Tüm notebook'lar |
| `KNeighborsClassifier` ile model kurma | Tüm notebook'lar |
| `confusion_matrix` & `classification_report` | Tüm notebook'lar |
| `PCA` ile boyut indirgeme ve görselleştirme | Wine & Digits |
| Görüntü verisi ile çalışma | Digits |

</details>

<details>
<summary><b>📊 Üç Farklı Veri Setiyle Ne Öğrenilir?</b></summary>

<br/>

Aynı algoritmanın farklı problem türlerine uygulanması şu soruları cevaplar:

- Az özellikle mi, çok özellikle mi daha iyi çalışır?
- Görüntü verisi sayısal veriyle aynı pipeline'a girer mi?
- Sınıf sayısı arttıkça doğruluk nasıl değişir?
- Hangisi daha zor: 3 sınıf mı, 10 sınıf mı?

```
Iris   →  Az özellik, dengeli sınıf, basit problem
Wine   →  Orta özellik, kimyasal veri, korelasyon analizi
Digits →  Çok özellik, görüntü verisi, gerçek dünya senaryosu
```

</details>

<br/>

---

## 📖 KNN Nedir?

<div align="center">

| 🇬🇧 İngilizce | 🇹🇷 Türkçe |
|:---:|:---:|
| **K-Nearest Neighbors** | **K-En Yakın Komşu** |

</div>

**KNN (K-Nearest Neighbors / K-En Yakın Komşu)**, yeni bir veri noktasını sınıflandırmak için eğitim setindeki en yakın `k` komşusuna bakan, basit ama güçlü bir makine öğrenmesi algoritmasıdır.

> **K** → Kaç komşuya bakılacağını belirleyen hiperparametre
> **Nearest** → En yakın (Öklid mesafesiyle ölçülür)
> **Neighbors** → Komşular (eğitim setindeki veri noktaları)

```
Yeni nokta → En yakın k komşuya bak → Çoğunluk oyuyla sınıf belirle ✓
```

KNN'in avantajları:
- Eğitim aşaması yoktur (lazy learner)
- Sezgisel ve anlaşılması kolaydır
- Yeni veriler eklendiğinde model yeniden eğitilmez
- Doğru normalizasyonla çok güçlü sonuçlar verir

---

## 📂 Veri Setleri

<div align="center">

| | Veri Seti | Notebook | Örnekler | Özellikler | Sınıflar |
|:---:|:---:|:---:|:---:|:---:|:---:|
| 🌸 | **Iris** | `KNN_Iris.ipynb` | 150 | 4 | 3 |
| 🍷 | **Wine** | `KNN_Wine.ipynb` | 178 | 13 | 3 |
| ✍️ | **Digits** | `KNN_Digits.ipynb` | 1797 | 64 | 10 |

</div>

---

<details>
<summary><h2>🌸 Dataset 1 — Iris (Çiçek Türü Sınıflandırması)</h2></summary>

<br/>

Botanikçi Edgar Anderson tarafından derlenen bu klasik veri seti, makine öğrenmesinin "Merhaba Dünya"sı olarak kabul edilir. Üç farklı Iris çiçeği türünü fiziksel ölçümlerle ayırt etmeyi amaçlar.

### Sınıflar

| Sınıf | Türkçe | Örnek Sayısı |
|---|---|---|
| *Iris Setosa* | Setosa | 50 |
| *Iris Versicolor* | Versicolor | 50 |
| *Iris Virginica* | Virginica | 50 |

### Özellikler

```
sepal length (cm)  →  Çanak yaprağı uzunluğu
sepal width  (cm)  →  Çanak yaprağı genişliği
petal length (cm)  →  Taç yaprağı uzunluğu
petal width  (cm)  →  Taç yaprağı genişliği
```

### Notebook İçeriği

- 📊 Özelliklerin türlere göre histogram dağılımı
- 🔥 Korelasyon ısı haritası
- 🔢 5-fold cross-validation ile en iyi k değerinin bulunması
- 📉 Eğitim / Test / CV doğruluk karşılaştırması
- 📋 Confusion matrix & classification report

</details>

---

<details>
<summary><h2>🍷 Dataset 2 — Wine (Şarap Üreticisi Sınıflandırması)</h2></summary>

<br/>

İtalya'daki üç farklı üreticiden alınan şarapların kimyasal analizine dayanan veri seti. 13 farklı kimyasal özellik kullanılarak şarabın hangi üreticiden geldiği tahmin edilmektedir.

### Sınıflar

| Sınıf | Açıklama | Örnek Sayısı |
|---|---|---|
| Üretici 1 | Birinci bölge şarapları | 59 |
| Üretici 2 | İkinci bölge şarapları | 71 |
| Üretici 3 | Üçüncü bölge şarapları | 48 |

### Özellikler (13 Adet)

```
alcohol          →  Alkol oranı
malic_acid       →  Malik asit
ash              →  Kül miktarı
alcalinity       →  Külün alkaliliği
magnesium        →  Magnezyum
total_phenols    →  Toplam fenoller
flavanoids       →  Flavonoidler
nonflavanoid_p.  →  Flavonoid olmayan fenoller
proanthocyanins  →  Proantosiyanidinler
color_intensity  →  Renk yoğunluğu
hue              →  Renk tonu
od280/od315      →  OD280/OD315 şarap sulandırması
proline          →  Prolin miktarı
```

### Notebook İçeriği

- 📦 Temel özelliklerin kutu grafikleri (boxplot)
- 🔥 13×13 korelasyon matrisi
- 🔢 5-fold cross-validation ile en iyi k değerinin bulunması
- 📉 Eğitim / Test / CV doğruluk karşılaştırması
- 📋 Confusion matrix & classification report
- 🎯 **PCA ile 2D görselleştirme** (13 özelliği 2 boyuta indirgeme)

</details>

---

<details>
<summary><h2>✍️ Dataset 3 — Digits (El Yazısı Rakam Tanıma)</h2></summary>

<br/>

Scikit-learn'ün kendi bünyesinde barındırdığı bu veri seti, el yazısıyla yazılmış 0-9 arası rakamların 8×8 piksel gri tonlamalı görüntülerinden oluşur. Gerçek dünya görüntü tanıma probleminin basitleştirilmiş bir versiyonudur.

### Sınıflar

10 sınıf — 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 rakamları (her biri ~180 örnek)

### Veri Yapısı

```
Her görüntü  →  8 × 8 piksel  =  64 özellik
Piksel değeri →  0 (beyaz) ... 16 (siyah)
Toplam örnek  →  1797 görüntü
```

### Notebook İçeriği

- 🖼️ Her rakamdan örnek görüntülerin gösterimi
- 🌡️ Ortalama piksel yoğunluğu haritaları (her rakam için)
- 📊 Sınıf dağılım grafiği
- 🔢 5-fold cross-validation ile en iyi k değerinin bulunması
- 📉 Eğitim / Test / CV doğruluk karşılaştırması
- 📋 10×10 Confusion matrix & classification report
- 🎯 **PCA ile 2D görselleştirme** (64 özelliği 2 boyuta indirgeme)
- ❌ **Yanlış tahmin edilen örneklerin görselleştirilmesi**

</details>

---

## ⚙️ Ortak Metodoloji

Her notebook'ta aynı sistematik pipeline uygulanmaktadır:

```
┌─────────────────────────────────────────────────────────┐
│                    KNN PIPELINE                         │
├─────────────────────────────────────────────────────────┤
│  1. Veri Yükleme & Keşif                                │
│     └─ boyut, sınıf dağılımı, temel istatistikler       │
│                                                         │
│  2. Görselleştirme (EDA)                                │
│     └─ veri setine özgü grafikler                       │
│                                                         │
│  3. Normalizasyon                                       │
│     └─ Min-Max Scaler → tüm değerleri [0, 1]'e taşı    │
│                                                         │
│  4. Train / Test Split                                  │
│     └─ %70 eğitim / %30 test, stratified               │
│                                                         │
│  5. Hiperparametre Optimizasyonu                        │
│     └─ k = 1..20 arası 5-fold cross-validation         │
│                                                         │
│  6. Model Eğitimi & Tahmin                              │
│     └─ KNeighborsClassifier(n_neighbors=best_k)        │
│                                                         │
│  7. Değerlendirme                                       │
│     └─ Accuracy · Precision · Recall · F1 · CM         │
└─────────────────────────────────────────────────────────┘
```

---

## 🚀 Kurulum & Kullanım

### Gereksinimler

```bash
pip install numpy pandas matplotlib seaborn scikit-learn notebook
```

### Çalıştırma

```bash
# Tüm notebookları listele
jupyter notebook

# Veya doğrudan aç
jupyter notebook KNN_Iris.ipynb
jupyter notebook KNN_Wine.ipynb
jupyter notebook KNN_Digits.ipynb
```

Her notebook bağımsız çalışır — harici veri dosyası gerekmez, veri setleri scikit-learn üzerinden otomatik yüklenir.

---

## 🛠️ Kullanılan Teknolojiler

<div align="center">

![Python](https://img.shields.io/badge/Python-FFD43B?style=flat-square&logo=python&logoColor=blue)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2C2D72?style=flat-square&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=flat-square&logo=python&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=flat-square&logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)

</div>

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=100&section=footer"/>

</div>
