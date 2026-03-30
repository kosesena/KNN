# Bölüm 5 — K-En Yakın Komşu Algoritması / Chapter 5 — K-Nearest Neighbors Algorithm

🇹🇷 Bu dosya, **Bölüm 5** ders notundaki tüm konuları içerir.
🇬🇧 This file covers all topics from the **Chapter 5** course notes.

---

## İçindekiler / Table of Contents

| # | 🇹🇷 Konu | 🇬🇧 Topic | Notebook Bölümü / Section |
|---|---------|----------|--------------------------|
| 1 | KNN Algoritması Nedir? | What is the KNN Algorithm? | Section 1 — Intro |
| 2 | Öklid Uzaklık Formülü | Euclidean Distance Formula | Section 1 — Intro |
| 3 | KNN Adım Adım (K=4, 2D) — Uygulama 1 | Step-by-step KNN (K=4, 2D) — Example 1 | Manual Examples |
| 4 | Min-Max Normalizasyonu ile KNN — Uygulama 2 | KNN with Min-Max Normalization — Example 2 | Manual Examples |
| 5 | Ağırlıklı Oylama (K=3) — Uygulama 3 | Weighted Voting (K=3) — Example 3 | Manual Examples |
| 6 | Gerçek Veri: Göğüs Kanseri Teşhisi | Real Dataset: Breast Cancer Diagnosis | Sections 2–9 |
| 7 | Etiket Kodlama (M→1, B→0) | Label Encoding (M→1, B→0) | Section 4 |
| 8 | Normalizasyon (Min-Max) | Normalization (Min-Max) | Section 6 |
| 9 | Eğitim / Test Ayrımı (%70/%30) | Train / Test Split (70%/30%) | Section 7 |
| 10 | KNN Modeli ve K Değeri Seçimi | KNN Model and K Selection | Section 8 |
| 11 | Ağırlıklı Oylama (`weights='distance'`) | Weighted Voting (`weights='distance'`) | Section 8b |
| 12 | Manuel Doğruluk Hesabı | Manual Accuracy Calculation | Section 10a |
| 13 | `accuracy_score` ile Doğruluk | Accuracy via `accuracy_score` | Section 10b |
| 14 | Hata Matrisi (Confusion Matrix) | Error Matrix (Confusion Matrix) | Section 11 |

---

## 1. KNN Nedir? / What is KNN?

🇹🇷 **KNN (K-En Yakın Komşu)**, sınıfı belli olan bir örnek kümesindeki gözlemlerden yararlanarak yeni bir gözlemin hangi sınıfa ait olduğunu belirleyen bir makine öğrenmesi algoritmasıdır.
🇬🇧 **KNN (K-Nearest Neighbors)** is a machine learning algorithm that determines which class a new observation belongs to by using labeled observations in a sample set.

🇹🇷 **Temel mantık:**
🇬🇧 **Core idea:**

- 🇹🇷 Yeni veri noktasına en yakın K komşu belirlenir.
  🇬🇧 The K nearest neighbors of the new data point are identified.
- 🇹🇷 Bu komşuların çoğunluğunun sınıfı, yeni noktanın sınıfı olarak atanır.
  🇬🇧 The majority class among these neighbors is assigned to the new point.
- 🇹🇷 KNN "lazy learner"dır — eğitim sırasında hiçbir şey öğrenmez, sadece veriyi saklar.
  🇬🇧 KNN is a "lazy learner" — it learns nothing during training, it just stores the data.

---

## 2. Öklid Uzaklık Formülü / Euclidean Distance Formula

🇹🇷 İki nokta arasındaki uzaklık şu formülle hesaplanır:
🇬🇧 The distance between two points is calculated with this formula:

$$D(i,j) = \sqrt{\sum_{k=1}^{p} (x_{ik} - x_{jk})^2}$$

🇹🇷 **Örnek / Example:** (2, 4) ile (8, 4) arasındaki uzaklık / Distance between (2, 4) and (8, 4):

$$D = \sqrt{(2-8)^2 + (4-4)^2} = \sqrt{36 + 0} = 6.00$$

---

## 3. KNN Algoritması Adımları / Algorithm Steps

🇹🇷
```
1. K parametresini belirle  →  Kaç komşuya bakılacak?
2. Tüm mesafeleri hesapla   →  D(i,j) = √Σ(xᵢₖ - xⱼₖ)²
3. Mesafeye göre sırala     →  En küçük K tanesini seç
4. Sınıfları belirle        →  Seçilen K komşunun sınıflarına bak
5. Çoğunluk oylaması        →  En çok tekrarlanan sınıf → tahmin
```

🇬🇧
```
1. Set K parameter          →  How many neighbors to consider?
2. Compute all distances    →  D(i,j) = √Σ(xᵢₖ - xⱼₖ)²
3. Sort by distance         →  Select the K smallest distances
4. Identify classes         →  Look at the classes of selected K neighbors
5. Majority vote            →  Most frequent class → prediction
```

---

## 4. Manuel Uygulamalar / Manual Examples

### Uygulama 1 / Example 1 — Temel KNN / Basic KNN (K=4, 2D)

🇹🇷 Aşağıdaki gözlem tablosunda **(8, 4)** noktasının sınıfını K=4 ile bulalım.
🇬🇧 Using the observation table below, find the class of point **(8, 4)** with K=4.

| X1 | X2 | 🇹🇷 Sınıf / 🇬🇧 Class |
|----|----|----|
| 2 | 4 | KÖTÜ / BAD |
| 3 | 6 | İYİ / GOOD |
| 3 | 4 | İYİ / GOOD |
| 4 | 10 | KÖTÜ / BAD |
| 5 | 8 | KÖTÜ / BAD |
| 6 | 3 | İYİ / GOOD |
| 7 | 9 | İYİ / GOOD |
| 9 | 7 | KÖTÜ / BAD |
| 11 | 7 | KÖTÜ / BAD |
| 10 | 2 | KÖTÜ / BAD |

🇹🇷 **En yakın 4 komşu / 🇬🇧 Nearest 4 neighbors:**

| X1 | X2 | 🇹🇷 Sınıf / 🇬🇧 Class | 🇹🇷 Uzaklık / 🇬🇧 Distance | 🇹🇷 Sıra / 🇬🇧 Rank |
|----|----|----|---------|------|
| 6 | 3 | İYİ / GOOD | 2.24 | 1 ← |
| 10 | 2 | KÖTÜ / BAD | 2.83 | 2 ← |
| 9 | 7 | KÖTÜ / BAD | 3.16 | 3 ← |
| 11 | 7 | KÖTÜ / BAD | 4.24 | 4 ← |

🇹🇷 1× İYİ, 3× KÖTÜ → **Sonuç: (8,4) = KÖTÜ**
🇬🇧 1× GOOD, 3× BAD → **Result: (8,4) = BAD**

---

### Uygulama 2 / Example 2 — Min-Max Normalizasyonu ile KNN / KNN with Min-Max Normalization (K=3, 3D)

🇹🇷 **(7, 8, 5)** noktasının sınıfını bulmak için önce Min-Max normalizasyonu uygulanır.
🇬🇧 To find the class of **(7, 8, 5)**, Min-Max normalization is applied first.

🇹🇷 **Neden normalizasyon?** KNN mesafeye dayanır. Farklı ölçeklerdeki özellikler büyük ölçeklinin sonucu baskılamasına neden olur.
🇬🇧 **Why normalize?** KNN relies on distance. Features at different scales cause larger-scale ones to dominate the result.

**Min-Max Formülü / Formula:**

$$X^* = \frac{X - X_{min}}{X_{max} - X_{min}}$$

🇹🇷 **Orijinal gözlemler / 🇬🇧 Original observations:**

| X1 | X2 | X3 | 🇹🇷 Sınıf / 🇬🇧 Class |
|----|----|----|------|
| 10 | 5 | 19 | EVET / YES |
| 8 | 2 | 4 | HAYIR / NO |
| 18 | 16 | 6 | HAYIR / NO |
| 12 | 15 | 8 | EVET / YES |
| 3 | 15 | 15 | EVET / YES |

🇹🇷 Normalize edilmiş değerler ve (7,8,5) → (0.26, 0.43, 0.07):
🇬🇧 Normalized values and (7,8,5) → (0.26, 0.43, 0.07):

| X1* | X2* | X3* | 🇹🇷 Uzaklık / 🇬🇧 Distance | 🇹🇷 Sınıf / 🇬🇧 Class |
|-----|-----|-----|---------|------|
| 0.47 | 0.21 | 1.00 | 0.98 | EVET / YES |
| 0.33 | 0.00 | 0.00 | 0.44 | HAYIR / NO ← |
| 1.00 | 1.00 | 0.13 | 0.93 | HAYIR / NO |
| 0.60 | 0.93 | 0.27 | 0.63 | EVET / YES ← |
| 0.00 | 0.93 | 0.73 | 0.87 | EVET / YES ← |

🇹🇷 En yakın 3 komşu: 1× HAYIR, 2× EVET → **Sonuç: (7,8,5) = EVET**
🇬🇧 3 nearest neighbors: 1× NO, 2× YES → **Result: (7,8,5) = YES**

---

### Uygulama 3 / Example 3 — Ağırlıklı Oylama / Weighted Voting (K=3)

🇹🇷 Standart oylamada her komşunun oyu eşittir. Ağırlıklı oylamada ise yakın komşular daha fazla etki eder.
🇬🇧 In standard voting, every neighbor's vote is equal. In weighted voting, closer neighbors have more influence.

🇹🇷 **Ağırlık formülü** / 🇬🇧 **Weight formula:**

$$w_i = \frac{1}{d(i,j)^2}$$

🇹🇷 **(0.10, 0.50)** noktası için K=3 en yakın komşu:
🇬🇧 K=3 nearest neighbors for point **(0.10, 0.50)**:

| 🇹🇷 Komşu / 🇬🇧 Neighbor | 🇹🇷 Uzaklık / 🇬🇧 Distance | 🇹🇷 Sınıf / 🇬🇧 Class | 🇹🇷 Ağırlık / 🇬🇧 Weight |
|-------|---------|-------|---------|
| (0.15, 0.55) | 0.07 | KADIN / FEMALE | **200.00** |
| (0.20, 0.25) | 0.27 | ERKEK / MALE | 13.79 |
| (0.08, 0.20) | 0.30 | ERKEK / MALE | 11.05 |

🇹🇷 **Standart oylama:** 2× ERKEK, 1× KADIN → ERKEK
🇬🇧 **Standard voting:** 2× MALE, 1× FEMALE → MALE

🇹🇷 **Ağırlıklı oylama:** KADIN: 200.00 > ERKEK: 24.84 → **KADIN**
🇬🇧 **Weighted voting:** FEMALE: 200.00 > MALE: 24.84 → **FEMALE**

🇹🇷 Aynı veri, farklı yöntem → farklı sonuç. Ağırlıklı oylama yakın komşuya daha fazla güvenir.
🇬🇧 Same data, different method → different result. Weighted voting trusts closer neighbors more.

---

## 5. Gerçek Veri Uygulaması / Real Dataset Application

🇹🇷 **Veri seti:** Göğüs Kanseri Teşhisi (Wisconsin Breast Cancer Dataset)
🇬🇧 **Dataset:** Breast Cancer Diagnosis (Wisconsin Breast Cancer Dataset)

🇹🇷 **Hedef:** Tümörün Malign (M — kötü huylu) mu yoksa Benign (B — iyi huylu) mu olduğunu tahmin etmek.
🇬🇧 **Goal:** Predict whether a tumor is Malignant (M — cancerous) or Benign (B — non-cancerous).

### Etiket Kodlama / Label Encoding

🇹🇷 Makine öğrenmesi modelleri metin yerine sayısal verilerle çalışır:
🇬🇧 Machine learning models work with numbers, not text:

```
M → 1  (Malignant / Kötü Huylu)
B → 0  (Benign    / İyi Huylu)
```

### Normalizasyon / Normalization

🇹🇷 KNN mesafeye dayalı olduğundan tüm özellikler [0, 1] aralığına çekilir:
🇬🇧 Since KNN is distance-based, all features are scaled to [0, 1]:

```python
x = (x_data - np.min(x_data)) / (np.max(x_data) - np.min(x_data))
```

### Eğitim / Test Ayrımı / Train / Test Split

🇹🇷 Veri %70 eğitim, %30 test olarak bölünür. `random_state=1` ile bölünme sabitlenir.
🇬🇧 Data is split 70% training, 30% testing. `random_state=1` ensures reproducibility.

```python
x_train, x_test, y_train, y_test = train_test_split(x, y, test_size=0.3, random_state=1)
```

### K Değeri / K Parameter

🇹🇷 `n_neighbors=10` — en yakın 10 komşuya bakılır.
🇬🇧 `n_neighbors=10` — looks at the 10 nearest neighbors.

| 🇹🇷 K değeri | 🇬🇧 K value | 🇹🇷 Etki | 🇬🇧 Effect |
|-------------|------------|---------|----------|
| Çok küçük / Too small | < 3 | Overfitting — gürültüye duyarlı / sensitive to noise |
| Çok büyük / Too large | > 20 | Underfitting — sınırlar bulanıklaşır / blurry boundaries |
| Optimal | ≈ √n | Dengeli sonuç / balanced result |

---

## 6. Ağırlıklı Oylama (sklearn) / Weighted Voting in sklearn

🇹🇷 `weights='distance'` parametresiyle aktif edilir:
🇬🇧 Activated with the `weights='distance'` parameter:

```python
knn = KNeighborsClassifier(n_neighbors=10, weights='distance')
```

---

## 7. Hata Matrisi / Confusion Matrix

🇹🇷
```
                 Tahmin: 0 (B)    Tahmin: 1 (M)
Gerçek: 0 (B) │      TN         │      FP       │
Gerçek: 1 (M) │      FN ⚠️      │      TP       │
```

🇬🇧
```
                  Predicted: 0 (B)   Predicted: 1 (M)
Actual: 0 (B)  │       TN          │       FP        │
Actual: 1 (M)  │       FN ⚠️       │       TP        │
```

| 🇹🇷 Terim | 🇬🇧 Term | 🇹🇷 Açıklama | 🇬🇧 Description |
|----------|----------|------------|----------------|
| **TN** (Doğru Negatif) | True Negative | Benign, benign tahmin edildi | Benign correctly predicted as benign |
| **TP** (Doğru Pozitif) | True Positive | Malign, malign tahmin edildi | Malignant correctly predicted as malignant |
| **FP** (Yanlış Pozitif) | False Positive | Benign ama malign tahmin edildi | Benign incorrectly predicted as malignant |
| **FN** (Yanlış Negatif) ⚠️ | False Negative ⚠️ | Malign ama benign tahmin edildi | Malignant incorrectly predicted as benign |

🇹🇷 **FN en tehlikeli hata:** Hasta biri sağlıklı zannedilerek tedavisiz bırakılır.
🇬🇧 **FN is the most dangerous error:** A cancer patient is left untreated, believing they are healthy.

### Değerlendirme Metrikleri / Evaluation Metrics

| Metrik / Metric | Formül / Formula | 🇹🇷 Ne zaman önemli? | 🇬🇧 When does it matter? |
|----------------|-----------------|---------------------|--------------------------|
| **Accuracy** | (TP+TN) / Total | Dengeli veri setlerinde | Balanced datasets |
| **Precision** | TP / (TP+FP) | FP maliyetliyse | When FP is costly |
| **Recall** | TP / (TP+FN) | FN maliyetliyse (tıp) | When FN is costly (medicine) |
| **F1 Score** | 2×(P×R)/(P+R) | İkisi de önemliyse | When both matter |
