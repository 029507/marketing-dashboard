# 📊 Marketing Analytics Dashboard

A multi-page interactive marketing analytics web app built with **Python + Streamlit**. It visualizes campaign performance, spend trends, lead funnels, correlation heatmaps, and uses a **Random Forest ML model** to predict closures.

---

## 🚀 Features

| Page | Description |
|------|-------------|
| 🏠 Home (`app.py`) | Landing page with navigation guide |
| 📘 Assignment Dashboard | KPI metrics, daily trends, scatter plots, funnel chart — with sidebar filters |
| ✨ Extra Visuals | Rolling average visitor trend using Plotly |
| 🔥 Heatmap | Correlation heatmap across Spend, Visitors, Leads, SiteVisits, Closure |
| 🤖 Prediction | Random Forest model to predict Closures from campaign inputs |

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python)
![Streamlit](https://img.shields.io/badge/Streamlit-multipage-red?logo=streamlit)
![Plotly](https://img.shields.io/badge/Plotly-interactive-blueviolet?logo=plotly)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange?logo=scikit-learn)

- **Frontend/UI:** Streamlit (multi-page app)
- **Data Visualization:** Plotly Express, Seaborn, Matplotlib
- **Machine Learning:** scikit-learn (Random Forest Regressor)
- **Data Processing:** Pandas, NumPy
- **Dataset:** `marketing_dataset.csv` (Platform, Adset, Spend, Visitors, Leads, SiteVisits, Closure)

---

## 📁 Project Structure

```
marketing-dashboard/
│
├── app.py                      # Main entry point (Home page)
├── pages/
│   ├── 1_Assignment_Dashboard.py   # KPIs, charts, funnel
│   ├── 2_Extra_Visuals.py          # Rolling avg trend
│   ├── 3_Heatmap.py                # Correlation heatmap
│   └── 4_Prediction.py             # ML closure prediction
│
├── marketing_dataset.csv       # Dataset
├── requirements.txt            # Dependencies
└── README.md
```

> ⚠️ **Important:** The `1_`, `2_`, `3_`, `4_` prefixed files must be inside a folder named `pages/` for Streamlit's multi-page routing to work.

---

## ⚙️ How to Run Locally

### 1. Clone the repository

```bash
git clone https://github.com/029507/marketing-dashboard.git
cd marketing-dashboard
```

### 2. Create a virtual environment (recommended)

```bash
python -m venv venv

# Activate it:
# Windows
venv\Scripts\activate

# Mac/Linux
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Set up the folder structure

Make sure your numbered page files are inside a `pages/` folder:

```bash
mkdir pages
mv 1_Assignment_Dashboard.py pages/
mv 2_Extra_Visuals.py pages/
mv 3_Heatmap.py pages/
mv 4_Prediction.py pages/
```

### 5. Run the app

```bash
streamlit run app.py
```

The app will open at **http://localhost:8501** in your browser.

---

## 📊 Dataset Columns

| Column | Description |
|--------|-------------|
| `Date` | Campaign date |
| `Platform` | Ad platform (e.g., Facebook, Google) |
| `Adset` | Ad set name |
| `Spend` | Amount spent (₹) |
| `Visitors` | Number of visitors |
| `Leads` | Number of leads generated |
| `SiteVisits` | Site visits from the campaign |
| `Closure` | Final conversions/closures |

---

## 🤖 ML Model — Closure Prediction

The **Prediction** page trains a `RandomForestRegressor` on the dataset with these features:

- Input: `Spend`, `Visitors`, `Leads`, `SiteVisits`, `Platform`, `Adset`
- Output: Predicted `Closure` count
- Metrics displayed: **R² Score** and **MAE**

You can enter custom values and get a real-time closure prediction.

---

## 📸 Pages Overview

- **Assignment Dashboard** — Filter by Platform, Adset, and Date Range. See KPI cards, daily line charts, scatter plot, and a marketing funnel.
- **Extra Visuals** — Smooth rolling average trend of visitors over time.
- **Heatmap** — Coolwarm correlation heatmap to find relationships between metrics.
- **Prediction** — Input campaign parameters and predict expected closures.

---

## 🧑‍💻 Author

**Aarush** — [GitHub @029507](https://github.com/029507)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
