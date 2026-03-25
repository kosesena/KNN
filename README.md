# KNN Classification — Iris Dataset

K-En Yakın Komşu (KNN) algoritmasının Iris veri seti üzerinde uygulanması.

## Hakkında

Bu proje, KNN sınıflandırma algoritmasını kullanarak Iris çiçeğinin türünü tahmin etmeyi amaçlamaktadır.

**Tahmin edilen sınıflar:**
- Setosa
- Versicolor
- Virginica

## Kullanılan Teknolojiler

- Python 3
- NumPy
- Pandas
- Matplotlib & Seaborn
- Scikit-learn

## İçerik

- **Veri keşfi (EDA):** Özelliklerin dağılımı, korelasyon ısı haritası
- **Ön işleme:** Min-Max normalizasyon, stratified train-test split (%70/%30)
- **Hiperparametre optimizasyonu:** 5-fold cross-validation ile en iyi k değerinin bulunması
- **Model değerlendirme:** Accuracy, confusion matrix, classification report

## Kurulum

```bash
pip install numpy pandas matplotlib seaborn scikit-learn notebook
jupyter notebook KNN_Iris.ipynb
```
