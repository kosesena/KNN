<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=220&section=header&text=KNN%20Classification&fontSize=50&fontColor=fff&animation=twinkling&fontAlignY=32&desc=K-En%20Yakın%20Komşu%20%7C%20K-Nearest%20Neighbors%20%7C%203%20Datasets&descAlignY=52&descSize=16"/>

<br/>

[![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.x-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org/)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)

<br/>

[![Course](https://img.shields.io/badge/Ders-Veri%20Madenciliği%20Laboratuvarı-8A2BE2?style=for-the-badge&logo=academia&logoColor=white)]()

> 🇹🇷 **K-En Yakın Komşu (KNN)** algoritmasının üç farklı gerçek dünya veri seti üzerinde, tutarlı bir metodoloji ile uygulanması ve karşılaştırılması.
>
> 🇬🇧 Implementation and comparison of the **K-Nearest Neighbors (KNN)** algorithm across three different real-world datasets using a consistent methodology.

<br/>

</div>

---

## Bu Proje Ne Öğretiyor? / What Does This Project Teach?

🇹🇷 Bu proje, makine öğrenmesine yeni başlayanlar için **teoriden pratiğe eksiksiz bir KNN rehberi** olmayı hedefler.

🇬🇧 This project aims to be a **complete, hands-on KNN guide** for beginners in machine learning — from theory to practice.

<details>
<summary><b>Kavramsal Öğrenme Hedefleri / Conceptual Learning Goals</b></summary>

<br/>

**1. KNN Algoritmasını Anlamak / Understanding the KNN Algorithm**

🇹🇷
- "En yakın komşu" mantığının geometrik sezgisi nedir?
- k sayısı küçük olunca ne olur, büyük olunca ne olur?
- Neden veri normalizasyonu KNN için kritiktir?

🇬🇧
- What is the geometric intuition behind "nearest neighbor" logic?
- What happens when k is too small or too large?
- Why is data normalization critical for KNN?

**2. Veri Ön İşleme / Data Preprocessing**

🇹🇷
- Ham veriyi modele hazır hale getirme adımları nelerdir?
- Min-Max normalizasyonu neden Öklid mesafesini etkiler?
- Stratified split neden rastgele split'ten daha güvenilirdir?

🇬🇧
- What are the steps to prepare raw data for a model?
- Why does Min-Max normalization affect Euclidean distance?
- Why is stratified split more reliable than random split?

**3. Hiperparametre Optimizasyonu / Hyperparameter Optimization**

🇹🇷
- k değerini tahmin etmek yerine veriye dayalı nasıl seçeriz?
- Cross-validation neden tek bir test setinden daha güvenilirdir?
- Overfitting / Underfitting grafikte nasıl görünür?

🇬🇧
- How do we select k based on data rather than guessing?
- Why is cross-validation more reliable than a single test set?
- How does overfitting / underfitting appear on a graph?

**4. Model Değerlendirme / Model Evaluation**

🇹🇷
- Accuracy tek başına yeterli midir?
- Precision, Recall ve F1-Score ne zaman önemlidir?
- Confusion matrix'ten hangi hatalar okunabilir?

🇬🇧
- Is accuracy alone sufficient?
- When do Precision, Recall, and F1-Score matter?
- What errors can be read from a confusion matrix?

**5. Boyut İndirgeme / Dimensionality Reduction (PCA)**

🇹🇷
- 13 veya 64 boyutlu veriyi gözle nasıl görürüz?
- PCA varyansın ne kadarını korur?

🇬🇧
- How do we visualize 13 or 64-dimensional data?
- How much variance does PCA preserve?

</details>

<details>
<summary><b>Pratik Beceri Hedefleri / Practical Skill Goals</b></summary>

<br/>

| Beceri / Skill | Nerede / Where |
|---|---|
| `pandas` — veri okuma ve keşif / data loading & exploration | All notebooks |
| `matplotlib` & `seaborn` — görselleştirme / visualization | All notebooks |
| `MinMaxScaler` — normalizasyon / normalization | All notebooks |
| `train_test_split` — stratified bölme / stratified splitting | All notebooks |
| `cross_val_score` — en iyi k / best k selection | All notebooks |
| `KNeighborsClassifier` — model kurma / model building | All notebooks |
| `confusion_matrix` & `classification_report` — değerlendirme / evaluation | All notebooks |
| `PCA` — boyut indirgeme / dimensionality reduction | Wine & Digits |
| Görüntü verisi / Image data handling | Digits |

</details>

<details>
<summary><b>Üç Farklı Veri Setiyle Ne Öğrenilir? / What Do Three Datasets Teach?</b></summary>

<br/>

🇹🇷 Aynı algoritmanın farklı problem türlerine uygulanması şu soruları cevaplar:

🇬🇧 Applying the same algorithm to different problem types answers:

- 🇹🇷 Az özellikle mi, çok özellikle mi daha iyi çalışır? / 🇬🇧 Does it work better with few or many features?
- 🇹🇷 Görüntü verisi sayısal veriyle aynı pipeline'a girer mi? / 🇬🇧 Can image data use the same pipeline as numerical data?
- 🇹🇷 Sınıf sayısı arttıkça doğruluk nasıl değişir? / 🇬🇧 How does accuracy change as the number of classes increases?

```
Iris   →  Few features,    balanced classes,  simple problem
Wine   →  Medium features, chemical data,     correlation analysis
Digits →  Many features,   image data,        real-world scenario
```

</details>

<br/>

---

## Bölüm 5 / Chapter 5

🇹🇷 Ders notundaki tüm konular `KNN.ipynb` notebook'unda ve ayrıntılı olarak **[BOLUM5.md](./BOLUM5.md)** dosyasında yer almaktadır.
🇬🇧 All course note topics are covered in `KNN.ipynb` and documented in detail in **[BOLUM5.md](./BOLUM5.md)**.

| 🇹🇷 Kapsanan Konular | 🇬🇧 Topics Covered |
|---------------------|-------------------|
| KNN Algoritması & Öklid Uzaklığı | KNN Algorithm & Euclidean Distance |
| 3 Manuel Uygulama (Uygulama 1, 2, 3) | 3 Manual Examples (Example 1, 2, 3) |
| Min-Max Normalizasyonu | Min-Max Normalization |
| Ağırlıklı Oylama | Weighted Voting |
| Göğüs Kanseri Gerçek Veri Uygulaması | Breast Cancer Real Dataset Application |
| Hata Matrisi (Confusion Matrix) | Confusion Matrix & Evaluation Metrics |

---

## KNN Nedir? / What is KNN?

<div align="center">

| 🇬🇧 English | 🇹🇷 Türkçe |
|:---:|:---:|
| **K-Nearest Neighbors** | **K-En Yakın Komşu** |

</div>

🇹🇷 **KNN**, yeni bir veri noktasını sınıflandırmak için eğitim setindeki en yakın `k` komşusuna bakan, basit ama güçlü bir makine öğrenmesi algoritmasıdır.

🇬🇧 **KNN** is a simple yet powerful machine learning algorithm that classifies a new data point by looking at its `k` nearest neighbors in the training set.

> **K** → 🇹🇷 Kaç komşuya bakılacağını belirleyen hiperparametre / 🇬🇧 Hyperparameter defining how many neighbors to consider
> **Nearest** → 🇹🇷 En yakın — Öklid mesafesiyle ölçülür / 🇬🇧 Closest — measured by Euclidean distance
> **Neighbors** → 🇹🇷 Komşular — eğitim setindeki veri noktaları / 🇬🇧 Data points in the training set

```
New point → Find k nearest neighbors → Majority vote → Assign class ✓
```

🇹🇷 KNN'in avantajları / 🇬🇧 Advantages of KNN:
- 🇹🇷 Eğitim aşaması yoktur (lazy learner) / 🇬🇧 No training phase (lazy learner)
- 🇹🇷 Sezgisel ve anlaşılması kolaydır / 🇬🇧 Intuitive and easy to understand
- 🇹🇷 Yeni veriler eklendiğinde model yeniden eğitilmez / 🇬🇧 No retraining needed when new data is added
- 🇹🇷 Doğru normalizasyonla çok güçlü sonuçlar verir / 🇬🇧 Delivers strong results with proper normalization

---

## Veri Setleri / Datasets

<div align="center">

| | Dataset | Notebook | Samples | Features | Classes |
|:---:|:---:|:---:|:---:|:---:|:---:|
| 🌸 | **Iris** | `KNN_Iris.ipynb` | 150 | 4 | 3 |
| 🍷 | **Wine** | `KNN_Wine.ipynb` | 178 | 13 | 3 |
| ✍️ | **Digits** | `KNN_Digits.ipynb` | 1797 | 64 | 10 |

</div>

---

<details>
<summary><h2>🌸 Dataset 1 — Iris (Flower Species Classification)</h2></summary>

<br/>

🇹🇷 Botanikçi Edgar Anderson tarafından derlenen bu klasik veri seti, makine öğrenmesinin "Merhaba Dünya"sı olarak kabul edilir. Üç farklı Iris çiçeği türünü fiziksel ölçümlerle ayırt etmeyi amaçlar.

🇬🇧 This classic dataset, compiled by botanist Edgar Anderson, is considered the "Hello World" of machine learning. It aims to distinguish three Iris flower species using physical measurements.

### Classes

| Class | Samples |
|---|---|
| *Iris Setosa* | 50 |
| *Iris Versicolor* | 50 |
| *Iris Virginica* | 50 |

### Features

```
sepal length (cm)  →  Çanak yaprağı uzunluğu  /  Sepal length
sepal width  (cm)  →  Çanak yaprağı genişliği /  Sepal width
petal length (cm)  →  Taç yaprağı uzunluğu    /  Petal length
petal width  (cm)  →  Taç yaprağı genişliği   /  Petal width
```

### Notebook Contents

- Feature distribution histograms by species
- Correlation heatmap
- Best k selection via 5-fold cross-validation
- Train / Test / CV accuracy comparison
- Confusion matrix & classification report

</details>

---

<details>
<summary><h2>🍷 Dataset 2 — Wine (Producer Classification)</h2></summary>

<br/>

🇹🇷 İtalya'daki üç farklı üreticiden alınan şarapların kimyasal analizine dayanan veri seti. 13 farklı kimyasal özellik kullanılarak şarabın hangi üreticiden geldiği tahmin edilmektedir.

🇬🇧 A dataset based on chemical analysis of wines from three different Italian producers. 13 chemical features are used to predict which producer the wine comes from.

### Classes

| Class | Samples |
|---|---|
| Producer 1 | 59 |
| Producer 2 | 71 |
| Producer 3 | 48 |

### Features (13)

```
alcohol          →  Alkol oranı         /  Alcohol content
malic_acid       →  Malik asit          /  Malic acid
ash              →  Kül miktarı         /  Ash content
alcalinity       →  Külün alkaliliği    /  Alcalinity of ash
magnesium        →  Magnezyum           /  Magnesium
total_phenols    →  Toplam fenoller     /  Total phenols
flavanoids       →  Flavonoidler        /  Flavanoids
nonflavanoid_p.  →  Fl. olmayan fen.    /  Nonflavanoid phenols
proanthocyanins  →  Proantosiyanidinler /  Proanthocyanins
color_intensity  →  Renk yoğunluğu     /  Color intensity
hue              →  Renk tonu           /  Hue
od280/od315      →  OD280/OD315         /  OD280/OD315 of wines
proline          →  Prolin miktarı      /  Proline
```

### Notebook Contents

- Boxplots of key features by producer
- 13×13 correlation matrix
- Best k selection via 5-fold cross-validation
- Train / Test / CV accuracy comparison
- Confusion matrix & classification report
- **PCA 2D visualization** (13 features → 2 dimensions)

</details>

---

<details>
<summary><h2>✍️ Dataset 3 — Digits (Handwritten Digit Recognition)</h2></summary>

<br/>

🇹🇷 Scikit-learn'ün kendi bünyesinde barındırdığı bu veri seti, el yazısıyla yazılmış 0-9 arası rakamların 8×8 piksel gri tonlamalı görüntülerinden oluşur. Gerçek dünya görüntü tanıma probleminin basitleştirilmiş bir versiyonudur.

🇬🇧 Built into scikit-learn, this dataset consists of 8×8 pixel grayscale images of handwritten digits 0–9. It is a simplified version of a real-world image recognition problem.

### Classes

10 classes — digits 0 through 9 (~180 samples each)

### Data Structure

```
Each image   →  8 × 8 pixels  =  64 features
Pixel value  →  0 (white) ... 16 (black)
Total samples →  1797 images
```

### Notebook Contents

- Sample images for each digit
- Average pixel intensity maps per digit
- Class distribution chart
- Best k selection via 5-fold cross-validation
- Train / Test / CV accuracy comparison
- 10×10 Confusion matrix & classification report
- **PCA 2D visualization** (64 features → 2 dimensions)
- **Visualization of misclassified samples**

</details>

---

## Ortak Metodoloji / Shared Methodology

🇹🇷 Her notebook'ta aynı sistematik pipeline uygulanmaktadır.
🇬🇧 The same systematic pipeline is applied across all notebooks.

```
┌─────────────────────────────────────────────────────────────────┐
│                         KNN PIPELINE                            │
├─────────────────────────────────────────────────────────────────┤
│  1. Data Loading & Exploration  /  Veri Yükleme & Keşif         │
│     └─ shape, class distribution, descriptive statistics        │
│                                                                 │
│  2. Visualization (EDA)  /  Görselleştirme                      │
│     └─ dataset-specific plots                                   │
│                                                                 │
│  3. Normalization  /  Normalizasyon                             │
│     └─ Min-Max Scaler → all values to [0, 1]                   │
│                                                                 │
│  4. Train / Test Split                                          │
│     └─ 70% train / 30% test, stratified                        │
│                                                                 │
│  5. Hyperparameter Optimization  /  Hiperparametre Optimizasyonu│
│     └─ k = 1..20 via 5-fold cross-validation                   │
│                                                                 │
│  6. Model Training & Prediction  /  Eğitim & Tahmin            │
│     └─ KNeighborsClassifier(n_neighbors=best_k)                │
│                                                                 │
│  7. Evaluation  /  Değerlendirme                                │
│     └─ Accuracy · Precision · Recall · F1 · Confusion Matrix   │
└─────────────────────────────────────────────────────────────────┘
```

---

## Kurulum & Kullanım / Setup & Usage

### Gereksinimler / Requirements

```bash
pip install numpy pandas matplotlib seaborn scikit-learn notebook
```

### Çalıştırma / Run

```bash
# List all notebooks
jupyter notebook

# Or open directly
jupyter notebook KNN_Iris.ipynb
jupyter notebook KNN_Wine.ipynb
jupyter notebook KNN_Digits.ipynb
```

🇹🇷 Her notebook bağımsız çalışır — harici veri dosyası gerekmez, veri setleri scikit-learn üzerinden otomatik yüklenir.

🇬🇧 Each notebook runs independently — no external data files needed, datasets are loaded automatically via scikit-learn.

---

## Kullanılan Teknolojiler / Tech Stack

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
