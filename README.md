Wine Quality Analysis

This project explores the Wine Quality datasets (red & white) using factor analysis, regression, and clustering. The goal is to uncover latent dimensions of wine chemistry, assess their relationship with quality, and segment wines into distinct style clusters.

1. Data

Sources: winequality-red.csv, winequality-white.csv

Features: 11 physicochemical measurements (e.g. fixed acidity, pH, alcohol) + quality score (3–9) + binary is_white indicator.

2. Factor Analysis

Components: 3 factors extracted with Varimax rotation.

| Factor  | Key Loadings (>|0.4|)                        | Interpretation                                   |
|---------|------------------------------------------------|--------------------------------------------------|
| 1   | + density (0.94), + residual sugar (0.73),+ total SO₂ (0.26),- alcohol (–0.75),- is_white (–0.13) | Body / Sweetness vs. DrynessHigh‑density, sugar‑rich (often white) wines score high; dry, high‑alcohol (often red) wines score low. |
| 2   | + fixed acidity (–0.95), + pH (0.40),+ free SO₂ (0.18), + total SO₂ (0.18)      | Acid balance & preservationContrasts acidic (low pH) vs. sulfite‑driven preservation. |
| 3   | + volatile acidity (0.67), + pH (0.46),+ chlorides (0.48),- total SO₂ (–0.75),- is_white (–0.93) | Aromatic / oxidative notesHigh volatile acidity & salty character vs. sulfite levels; strongly separates reds from whites. |

Correlation with Quality

Factor 1 vs. Quality: r≈ –0.30 (better wines tend to be drier, higher‐alcohol)

Factor 2 vs. Quality: r≈ –0.08 (weak)

Factor 3 vs. Quality: r≈ –0.06 (weak)

3. Regression

Predicting quality from factor scores (5‑fold CV)

Linear Regression: R² ≈ 0.014

Decision Tree (tuned): R² ≈ 0.060

Best params: max_depth=5, min_samples_leaf=5

Feature importances: Factor 1 (0.73), Factor 2 (0.16), Factor 3 (0.11)

Even with latent factors, only ~6% of quality variance is explainable.

4. Clustering

Segment wines in factor space via K‑means (silhouette‑tuned):

Optimal clusters: k=4, n_init=5 (silhouette ≈ 0.45)

Cluster

Count

Mean Quality

Mean Factor_1

Mean Factor_2

Mean Factor_3

Style Profile

0

2768

6.09

–0.06

–0.14

–0.25

Balanced, moderate body

1

1161

5.55

+0.04

+0.01

+1.76

Aromatic / oxidative

2

2066

5.62

+0.73

+0.73

–0.70

Sweet/full‑bodied whites

3

502

5.75

–1.19

–2.25

+0.19

High‑acid, low sugar reds

Clusters reveal distinct style groups that partly align with red/white and quality.

Next Steps

Integrate these analyses into an interactive dashboard

Explore supervised models with raw + latent features

Compare to PCA or other dimensionality‑reduction methods

Author: lukew | Date: Apr 23 2025

