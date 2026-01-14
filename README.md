# Tumor Texture Analysis - Machine Learning Project

**Autor:** Vocs Pouani  
**Modul:** Einführung und Vertiefung in Python

---

## Projektziel

Klassifikation von Tumorgewebe vs. normalem Gewebe mittels Textur- und Farbraum-Analyse auf H&E-gefärbten histopathologischen Bildern.

**Klinische Relevanz:** Automatisierte Unterstützung für Pathologen bei der Tumordiagnose durch quantitative Texturanalyse.

---

## Dataset

- **100 Mikroskopie-Bilder** (512×512 px)
- **50 Tumor-Samples** (label = 1, malignant)
- **50 Normal-Samples** (label = 0, benign)
- **H&E-Färbung:** Hämatoxylin (blau, Zellkerne) + Eosin (rosa, Zytoplasma)

---

## Methodik

### **Teil 1: Datenvorbereitung & Farbraum-Analyse**
- RGB → HSV Konversion zur Trennung von Farbinformation und Helligkeit
- Analyse der H, S, V Kanäle
- Identifikation des optimal diskriminierenden Kanals
- Schwellenwert-Maskierung für stark gefärbtes Gewebe

### **Teil 2: Textur-Feature-Extraktion**
- **Entropie:** Maß für Texturkomplexität/Unordnung (höher bei Tumoren)
- **Varianz:** Schwankung der Intensitätswerte
- **Median:** Zentrale Tendenz der Helligkeitswerte
- Integration der Features in Pandas DataFrame

### **Teil 3: Statistische Analyse & Visualisierung**
- Histogramm-Vergleich: Entropie-Verteilung Tumor vs. Normal
- Korrelations-Heatmap der Textur-Features
- Visuelle Gegenüberstellung: Tumor- vs. Normal-Beispiele mit Entropie-Werten

### **Teil 4: Machine Learning Klassifikation**
- Decision Tree Classifier auf 3 Features
- Feature Importance Analyse
- Interpretation: Welches Feature ist am wichtigsten?

---

## Projektstruktur

```
python-ml-histotexture/
│
├── data/
│   ├── raw/                    # Original-Bilder & CSV
│   └── processed/              # Verarbeitete Features
│
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_hsv_analysis.ipynb
│   ├── 03_feature_extraction.ipynb
│   └── 04_ml_classification.ipynb
│
├── src/
│   └── utils.py                # Wiederverwendbare Funktionen
│
├── results/
│   ├── figures/                # Visualisierungen 
│   └── models/                 # Trainierte ML-Modelle
│
├── README.md
├── requirements.txt
```

---

## Installation

```bash
pip install -r requirements.txt
```

---

## Quellen

- scikit-image Documentation: https://scikit-image.org/
- Texture Analysis in Medical Imaging: Shannon Entropy
- scikit-learn Decision Trees: https://scikit-learn.org/

---

## Dokumentation & Reflexion

Siehe Jupyter Notebooks für detaillierte Dokumentation des Vorgehens, einschließlich:
- Begründungen für methodische Entscheidungen
- Experimentelle Ansätze (erfolgreiche und gescheiterte)
- Interpretation der Ergebnisse
- Limitationen und mögliche Verbesserungen
