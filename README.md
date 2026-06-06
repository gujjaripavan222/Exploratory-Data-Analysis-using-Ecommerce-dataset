# 🛒 Exploratory Data Analysis — E-Commerce Dataset

<div align="center">

![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.0%2B-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.7%2B-11557C?style=for-the-badge)
![Seaborn](https://img.shields.io/badge/Seaborn-0.12%2B-4C72B0?style=for-the-badge)
![Plotly](https://img.shields.io/badge/Plotly-5.x-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

**A full-cycle EDA pipeline uncovering customer behavior, sales trends, and country-level insights from 541,909 real-world transaction records.**

[📓 View Notebook](./DATA_ANALYSIS_EDA_PROJECT_COMPLETE.ipynb) · [📊 Dataset](./data.csv) · [🐍 Source Script](./src.py)

</div>

---

## 📌 Project Overview

This project performs a comprehensive **Exploratory Data Analysis (EDA)** on a UK-based online retail dataset. With over **541,909 transaction records** spanning 8 key attributes — including invoices, products, unit prices, quantities, and customer locations — this pipeline delivers actionable business intelligence covering:

- Customer purchase behavior and segmentation
- Revenue trends across time (monthly, daily, hourly)
- Country-level order volumes and spending
- Price distribution analysis and anomaly detection
- Identification of free/promotional products

> **Dataset Source:** [UCI Machine Learning Repository — Online Retail Dataset](https://archive.ics.uci.edu/dataset/352/online+retail)

---

## 📂 Repository Structure

```
Exploratory-Data-Analysis-using-Ecommerce-dataset/
│
├── DATA_ANALYSIS_EDA_PROJECT_COMPLETE.ipynb   # Full Jupyter Notebook (end-to-end EDA)
├── src.py                                      # Standalone Python analysis script
├── data.csv                                    # Raw e-commerce transaction dataset
├── requirements.txt                            # Python dependencies
└── README.md                                   # Project documentation
```

---



## 🔍 Dataset Description

| Column | Description |
|---|---|
| `InvoiceNo` | Unique transaction identifier (prefix 'C' = cancellation) |
| `StockCode` | Product/item code |
| `Description` | Product name |
| `Quantity` | Number of units per transaction |
| `InvoiceDate` | Date and time of the transaction |
| `UnitPrice` | Price per unit (GBP) |
| `CustomerID` | Unique customer identifier (nullable = guest checkout) |
| `Country` | Country of the customer |

**Key observations:**
- Missing values in `CustomerID` and `Description` indicate guest checkouts
- Negative `Quantity` values represent returns/cancellations
- Zero `UnitPrice` entries represent free/promotional products

---

## 🧪 Analysis Pipeline

### Step 1 — Library Imports
All required data science libraries loaded: `pandas`, `numpy`, `matplotlib`, `seaborn`, `plotly`.

### Step 2 — Data Loading & Initial Inspection
- Loaded dataset from remote URL
- Inspected shape, head/tail, and column names
- Renamed columns to `snake_case` for consistency

### Step 3 — Data Cleaning
- Converted `invoice_date` to `datetime` format
- Standardized `description` to lowercase
- Identified and dropped missing values via `isna().sum()`
- Cast `cust_id` to `int64`
- Removed negative `quantity` values (returns/cancellations)
- Engineered `amount_spent` = `quantity × unit_price`

### Step 4 — Feature Engineering
Derived time-based columns from `invoice_date`:

| New Column | Description |
|---|---|
| `year_month` | Combined year and month for trend analysis |
| `month` | Extracted month number |
| `day` | Day of week (0 = Monday) |
| `hour` | Hour of day for peak hour analysis |

### Step 5 — Exploratory Data Analysis
- **Customer-level analysis:** Top customers by order count and total spend
- **Country-level analysis:** Orders and revenue aggregated by country
- **Temporal trends:** Monthly and daily order volume patterns
- **Price analysis:** Distribution of unit prices, outlier detection, free product identification
- **Promotional products:** Monthly trend of zero-price items

### Step 6 — Data Visualization

| Chart Type | Insight Delivered |
|---|---|
| Line plots | Orders & revenue by customer |
| Bar plots | Orders by month, day, and country |
| Horizontal bar plots | Country-level revenue (better readability) |
| Boxplot | Unit price distribution & outliers |
| Filtered bar plots | Non-UK country comparison (excluding dominant UK market) |

### Step 7 — Country-Level Analysis
- Identified top markets by order volume and total revenue
- Produced visualizations excluding the UK to surface smaller market trends

---

## 📊 Key Insights

- 📦 The **United Kingdom** dominates order volume, accounting for the majority of transactions
- 📅 Sales peak in **Q4 (Oct–Nov)**, consistent with holiday shopping behavior
- 🎁 A notable volume of **zero-price (free) products** exists — likely promotions or samples
- 👤 A small cohort of **high-value customers** drives a disproportionate share of revenue
- 🕙 Peak purchasing hours cluster in the **mid-morning to early afternoon**

---

## 🛠️ Tech Stack

| Library | Version | Purpose |
|---|---|---|
| `pandas` | ≥ 2.0 | Data manipulation and analysis |
| `numpy` | ≥ 1.24 | Numerical computation |
| `matplotlib` | ≥ 3.7 | Static visualizations |
| `seaborn` | ≥ 0.12 | Statistical visualizations |
| `plotly` | ≥ 5.0 | Interactive visualizations |

---

## ⚙️ Installation & Usage

### 1. Clone the Repository

```bash
git clone https://github.com/gujjaripavan222/Exploratory-Data-Analysis-using-Ecommerce-dataset.git
cd Exploratory-Data-Analysis-using-Ecommerce-dataset
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the Analysis

**Option A — Jupyter Notebook (Recommended):**
```bash
jupyter notebook DATA_ANALYSIS_EDA_PROJECT_COMPLETE.ipynb
```

**Option B — Python Script:**
```bash
python src.py
```

---

## 📈 Sample Visualizations

The notebook produces the following key charts:

- **Monthly sales trend** — line chart showing order volume and revenue over time
- **Top 10 customers by spend** — horizontal bar chart
- **Country-wise revenue distribution** — bar chart (with and without UK)
- **Unit price boxplot** — identifying outliers and free products
- **Hourly and daily heatmaps** — revealing peak shopping windows

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome. Feel free to open a pull request or raise an issue.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

---

## 👤 Author

**Pavan Kumar**

[![GitHub](https://img.shields.io/badge/GitHub-gujjaripavan222-181717?style=flat-square&logo=github)](https://github.com/gujjaripavan222)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

<div align="center">
  <sub>Built with ❤️ using Python · Pandas · Matplotlib · Seaborn · Plotly</sub>
</div>
