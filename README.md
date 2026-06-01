# 🏨 Hotel Booking Data Analysis — End-to-End Project

A complete exploratory data analysis (EDA) project investigating hotel booking trends, cancellation patterns, and pricing behaviour using a real-world dataset of ~119,000 hotel reservations.

---

## 📁 Project Structure

```
Hotel_Booking_End_to_End_Project_Resources/
│
└── Data Analysis Projects/
    ├── Data Analysis (Hotel Booking).ipynb   # Main Jupyter notebook
    ├── hotel_bookings 2.csv                  # Raw dataset (~119K rows)
    └── Report.pdf                            # Final analysis report
```

---

## 📊 Dataset Overview

| Property        | Details                              |
|-----------------|--------------------------------------|
| File            | `hotel_bookings 2.csv`               |
| Records         | ~119,390 rows                        |
| Features        | 32 columns                           |
| Hotel Types     | City Hotel, Resort Hotel             |
| Date Range      | 2015 – 2017                          |

### Key Columns

| Column | Description |
|--------|-------------|
| `hotel` | Hotel type (City Hotel / Resort Hotel) |
| `is_canceled` | Whether the booking was cancelled (1 = Yes) |
| `lead_time` | Days between booking and arrival |
| `adr` | Average Daily Rate (price per night) |
| `arrival_date_*` | Year, month, week, and day of arrival |
| `stays_in_weekend_nights` / `stays_in_week_nights` | Length of stay |
| `market_segment` | Booking channel (Online TA, Direct, Corporate, etc.) |
| `country` | Guest country of origin |
| `reservation_status` | Final status of the booking |
| `customer_type` | Type of customer (Transient, Contract, Group, etc.) |

---

## 🔍 Analysis Performed

### 1. Data Loading & Exploration
- Loaded the CSV with `pandas` and inspected shape, data types, and column summaries
- Converted `reservation_status_date` to datetime format

### 2. Data Cleaning
- Dropped `company` and `agent` columns (high null count)
- Removed rows with remaining null values
- Filtered outliers — removed records where `adr` ≥ 5000

### 3. Exploratory Data Analysis & Visualizations

| Analysis | Description |
|----------|-------------|
| **Cancellation Rate** | Overall proportion of cancelled vs. confirmed bookings |
| **Hotel-wise Cancellations** | Cancellation count broken down by hotel type |
| **Average Daily Rate (ADR) Over Time** | Line plot comparing City vs. Resort Hotel pricing trends |
| **Reservations per Month** | Monthly booking and cancellation count by hotel |
| **ADR for Cancelled Bookings by Month** | Bar chart of revenue lost to cancellations monthly |
| **Top 10 Countries by Cancellations** | Pie chart of guest nationalities with highest cancellation rates |
| **Market Segment Analysis** | Distribution of bookings and cancellations by market segment |
| **ADR: Cancelled vs. Not Cancelled** | Time-series comparison of pricing for cancelled vs. completed stays (2016–Sep 2017) |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| **Python 3** | Core programming language |
| **pandas** | Data loading, cleaning, and manipulation |
| **Matplotlib** | Bar charts, line plots, pie charts |
| **Seaborn** | Count plots and bar plots |
| **Jupyter Notebook** | Interactive development environment |

---

## 🚀 Getting Started

### Prerequisites

```bash
pip install pandas matplotlib seaborn jupyter
```

### Run the Notebook

```bash
# Clone or extract the project folder, then:
cd "Data Analysis Projects"
jupyter notebook "Data Analysis (Hotel Booking).ipynb"
```

> Make sure `hotel_bookings 2.csv` is in the same directory as the notebook before running.

---

## 📈 Key Findings

- A significant share of bookings were cancelled, with **City Hotels** showing higher cancellation rates than Resort Hotels.
- **Average Daily Rates** are higher for City Hotels during weekdays and peak months, while Resort Hotels see seasonal spikes.
- Cancellation rates vary notably by **month**, with certain months seeing disproportionately higher cancellations.
- A small number of **countries** account for the majority of cancellations.
- **Online Travel Agencies (OTA)** are the dominant market segment, representing the largest share of both bookings and cancellations.
- Cancelled bookings tend to have a **higher ADR** compared to completed stays, suggesting price sensitivity as a driver of cancellations.

---

## 📄 Report

A compiled PDF report (`Report.pdf`) summarising the findings and visualisations is included in the project folder.

---

## 📌 Notes

- The notebook suppresses warnings using `warnings.filterwarnings('ignore')` for cleaner output.
- ADR outliers (≥ 5000) were removed prior to analysis to prevent skewed visualisations.
- The `.ipynb_checkpoints/` folder is an auto-generated Jupyter artefact and can be ignored.
