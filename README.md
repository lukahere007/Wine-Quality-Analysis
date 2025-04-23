# 🍷 Wine Quality Factor Analysis

![Python](https://img.shields.io/badge/python-3.8%2B-blue.svg) ![scikit-learn](https://img.shields.io/badge/scikit--learn-1.2%2B-green.svg)

Interactive factor analysis & clustering of Portuguese Vinho Verde wine physicochemical data.

---

## 📁 Repository Structure

```
wine-quality-analysis/
├─ data/                  # Original CSVs (red & white)
├─ figures/               # Generated plots (.png)
├─ notebooks/             # Jupyter notebooks of the analysis
├─ README.md              # This file
├─ requirements.txt       # Python dependencies
└─ LICENSE                
```

---

## 🚀 Quickstart

1. **Clone the repo**
   ```bash
   git clone https://github.com/lukahere007/wine-quality-analysis.git
   cd wine-quality-analysis
   ```
2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```
3. **Download data**  
   Place `winequality-red.csv` & `winequality-white.csv` into `data/`.
4. **Run the analysis**  
   ```bash
   jupyter lab
   ```
   Open `notebooks/wine_quality_factor_analysis.ipynb`.

---

## 🔍 Analysis Overview

<details>
<summary>1. Data Loading & Cleaning</summary>

- Handled quoting issues in `winequality-red.csv`.
- Standardized column names & combined red + white datasets.
- Added `is_white` dummy for wine color.
</details>

<details>
<summary>2. Factor Analysis</summary>

- Reduced 12 features (+ color) to **3 latent factors**.
- Applied Varimax rotation for interpretability.
</details>

<details>
<summary>3. Factor Interpretation</summary>

| Factor    | Key Loadings                       | Interpretation                                       |
|-----------|------------------------------------|------------------------------------------------------|
| **1**     | density (+), residual sugar (+), alcohol (–) | “Body/Sweetness vs. Alcohol”                        |
| **2**     | total SO₂ (+), free SO₂ (+), pH (+) | Sulfur & acidity balance                              |
| **3**     | volatile acidity (+), chlorides (+), is_white (–) | Acidity/oxidation & color (red vs. white separation) |
</details>

<details>
<summary>4. Quality Link</summary>

- **Factor 1** correlates modestly with quality (r ≈ –0.30): drier, higher-alcohol wines score higher.
- Factors 2 & 3 show negligible correlation.
</details>

<details>
<summary>5. Predictive Modeling</summary>

- **Linear Regression** on factors: R² ≈ 0.01  
- **Decision Tree Regressor** (tuned): R² ≈ 0.06  
  - Factor 1 was most important (≈ 73%), then Factor 2 (16%), Factor 3 (11%).
</details>

<details>
<summary>6. Clustering (K-Means)</summary>

- Optimal **k=4** clusters (silhouette ≈ 0.45) in factor space.
- Reveals four wine “styles” differing in sweetness, alcohol, SO₂, acidity profiles.
</details>

---

## 📊 Key Findings

- **Factor 1** is the primary quality driver:  
  - High density & sugar vs. high alcohol trade‐off.
- Raw chemical factors explain only a small fraction of sensory scores.
- **Cluster segmentation** groups wines into intuitive styles (sweet, dry, high‐SO₂, high‐acid).

---

## 🔮 Next Steps

- Integrate grape variety, vintage, or price data.
- Try ensemble/tree‐based models (Random Forest, XGBoost).
- Deploy an interactive dashboard for exploration.

---

## 📦 Requirements

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
jupyterlab
```

Install with:

```bash
pip install -r requirements.txt
```

---

## 📄 License

This project is licensed under the MIT License.

---

## 👤 Author

**Luke Wamalwa**  
https://github.com/lukahere007  
https://linkedin.com/in/luke-wamalwa-839624292  
*Created on Apr 23 2025*
