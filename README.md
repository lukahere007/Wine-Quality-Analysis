#  Wine Quality Factor Analysis

![Python](https://img.shields.io/badge/python-3.8%2B-blue.svg) ![scikit-learn](https://img.shields.io/badge/scikit--learn-1.2%2B-green.svg)

Interactive factor analysis & clustering of Portuguese Vinho Verde wine physicochemical data.

---

##  Repository Structure

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

##  Quickstart

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


---

## 📦 Requirements

```text
Python (pandas, numpy, matplotlib, seaborn)

scikit-learn

factor_analyzer

statsmodels

xgboost

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
