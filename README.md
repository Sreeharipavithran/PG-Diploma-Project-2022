# 📱 Ideal Product Detection — Flagship Smartphone Analysis

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-red?logo=scikit-learn&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-Web_App-ff4b4b?logo=streamlit&logoColor=white)
![Tableau](https://img.shields.io/badge/Tableau-Dashboard-blue?logo=tableau&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

> An end-to-end Data Science project to detect the most ideal flagship smartphones (2020–2022) using ML price prediction, user survey analysis, and interactive Tableau dashboards — for both Gaming and Non-Gaming categories.

🔗 **[View Live Tableau Dashboard](https://public.tableau.com/views/IdealFlagships/Story1)**
📋 **[View Original Survey Form](https://docs.google.com/forms/d/1ar73GtGhk75lufdN5B5e0p86diH8ZIj29ad87WU97vw/edit)**

---

## 🎯 Objective

There is no single smartphone that has all ideal features under a reasonable price. This project aims to:
- Predict the **ideal price** of a flagship phone based on user-preferred specs
- Identify **real existing devices** that come closest to those ideal specs
- Compare ideal vs real devices using **interactive Tableau dashboards**

---

## 🗂️ Project Pipeline

```
Data Collection → Feature Engineering → ML Model → Streamlit Web App
      ↓                                                      ↓
 Survey (Google Form)  →  Ideal Spec Analysis  →  Tableau Dashboard
```

---

## 📦 Repository Structure

```
├── FLAGSHIP 20-22 Data.xlsx                          # Raw collected dataset (69 devices)
├── Ideal_Product_Detection_Feature_Engineering_      # Feature engineering notebook
│   and_ML_Model.ipynb
├── Ideal_spec_finding_analysis(from_survey_data).ipynb  # Survey analysis notebook
├── code_made_by_sreehari.ipynb                       # Custom countplot utility function
├── flaghship pycharm.txt                             # Streamlit web app source code
├── Best_device_Tblx_dashboradlink.txt                # Tableau dashboard link
├── Ideal Product detection-Report.pdf                # Full project report
└── Project_Summary.txt                               # Project overview
```

---

## 📊 Dataset

- **Source:** [Gadgets360](https://gadgets360.com/mobiles), [91mobiles](https://www.91mobiles.com/), [GSMArena](https://www.gsmarena.com/)
- **Scope:** 69 flagship smartphones from 2020–Jan 2022
- **Brands:** Apple, Samsung, OnePlus, Xiaomi, Poco, Realme, Vivo, Asus, IQOO, Lenovo, Motorola, Oppo
- **Criteria:** Snapdragon 855+, Dimensity 1000+, or Apple A-series chipset; 5G enabled
- **Fields:** 21 raw features → expanded to 30+ after feature engineering

---

## 🔧 Phase 1 — Feature Engineering

**Notebook:** `Ideal_Product_Detection_Feature_Engineering_and_ML_Model.ipynb`

- Removed unit strings (`MP`, `GB`, `Kg`) from columns for numeric conversion
- Split multi-value columns (e.g. `48+16+8` camera → 3 separate columns)
- Engineered **PPI** (Pixels Per Inch) from resolution + screen size
- Verified splits by checking unique values; corrected misaligned columns
- Final cleaned data exported as `Pythonsplit FLAGSHIP 20-22 Data.csv`

---

## 🤖 Phase 2 — ML Model (Price Prediction)

**Model:** Voting Regressor (RandomForest + GradientBoosting + ExtraTrees)

| Metric | Score |
|--------|-------|
| R² Score | **0.7747** |
| MAE | **0.1628** (log scale) |

- Correlation analysis to select best features
- Label encoding + OneHotEncoder via `ColumnTransformer`
- 80/20 train-test split
- Model exported using `pickle` → `pipe.pkl`, `vd.pkl`

---

## 🌐 Phase 3 — Streamlit Web App

A web-based price predictor built with **Streamlit** in PyCharm.

- Select brand, chipset, display, cameras, battery, and more
- Click **"Predict Product Price"** → get predicted INR price instantly
- Used to predict ideal device prices for each brand with survey-identified specs

```bash
streamlit run ipd.py
```

---

## 📋 Phase 4 — Survey & Ideal Spec Analysis

**Notebook:** `Ideal_spec_finding_analysis(from_survey_data).ipynb`

- Survey created via **Google Form** for both gamers and non-gamers
- Responses analyzed using custom `cp()` countplot function
- Most-selected features identified separately for **Gaming** and **Normal** flagship categories
- Example finding: Most users preferred **480Hz touch sample rate** for gaming devices, **Samsung sensor** for camera

---

## 📈 Phase 5 — Tableau Dashboard

**[🔗 View Interactive Dashboard](https://public.tableau.com/views/IdealFlagships/Story1)**

- **15 feature sheets** created for gaming + normal flagship comparison
- Devices with **8+ out of 15 matching ideal features** selected as best real products
- **Detected:** 5 best Gaming Flagships (ASUS ROG 5, Lenovo Legion Duel 2, OnePlus 9RT, Realme GT 2, GT Neo 2) and 11 best Normal Flagships
- Interactive comparison: click any brand → see how it compares to the ideal predicted device

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| `Python` | Core language |
| `Pandas`, `NumPy` | Data manipulation |
| `Matplotlib`, `Seaborn` | Visualization |
| `Scikit-learn` | ML models, encoding, evaluation |
| `Streamlit` | Web app |
| `Pickle` | Model export |
| `Tableau Public` | Interactive dashboards |
| `Google Forms` | Survey |
| `Google Colab` | Notebook environment |

---

## ▶️ How to Run

```bash
# Clone the repo
git clone https://github.com/Sreeharipavithran/PG-Diploma-Project-2022.git

# Install dependencies
pip install streamlit scikit-learn pandas numpy matplotlib seaborn openpyxl

# Run the web app (requires pipe.pkl and vd.pkl)
streamlit run "flaghship pycharm.txt"
```
> ⚠️ Note: The pre-trained model files (pipe.pkl, vd.pkl) are not included
> in this repo as they were built on a local system. To reproduce them,
> run the Feature Engineering and ML Model notebook end-to-end first,
> which will generate the pickle files needed for the Streamlit app.
---

## 📬 Connect with Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?logo=linkedin)](https://www.linkedin.com/in/sreeharipavithran30/)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black?logo=github)](https://github.com/Sreeharipavithran)
[![Tableau](https://img.shields.io/badge/Tableau-Dashboard-blue?logo=tableau)](https://public.tableau.com/views/IdealFlagships/Story1)
