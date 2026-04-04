# 🏠 Real Estate Growth Tracker — Power BI Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Pages](https://img.shields.io/badge/Pages-3-blue?style=for-the-badge)

A comprehensive **Real Estate Analytics Dashboard** built in Power BI that tracks property pricing, growth trends, amenities impact, and market delay causes across major European cities.

---

## 📊 Dashboard Overview

The project contains **3 pages**:

| Page | Name | Description |
|------|------|-------------|
| 1 | `presented by` | Introduction / landing page |
| 2 | `dashboard1` | Main KPIs, price analysis, property features |
| 3 | `dashboard2` | Amenities table, map, delay causes analysis |

---

## 🖼️ Screenshots
![Images](https://github.com/saeedullah-tech/REAL-ESTATE-dashboard/blob/615215aca19ea5119874c2ede43daea642b0e615/Power%20BI%20Desktop%2003_04_2026%2012_18_36.png)

### Dashboard 1 — Price & Growth Analysis
![Images](https://github.com/saeedullah-tech/REAL-ESTATE-dashboard/blob/478561926d32a2a1eca5c53b12d2e515036d76b3/Power%20BI%20Desktop%2003_04_2026%2012_33_32.png)

### Dashboard 2 — Amenities & Delay Analysis
![Dashboard 2](https://github.com/saeedullah-tech/REAL-ESTATE-dashboard/blob/478561926d32a2a1eca5c53b12d2e515036d76b3/Power%20BI%20Desktop%2003_04_2026%2012_34_58.png)

---

## 📈 Key Metrics Tracked

| KPI | Value (Sample) |
|-----|---------------|
| 💰 Avg Price | £635K |
| 📈 Sum of Price Growth | £23M |
| 📐 Avg Price per m² | 3.15K |
| 🏘️ Total Listings | 5K |

---

## 🗺️ Features

### Dashboard 1
- **KPI Cards** — Avg Price, Price Growth, Price per m², Total Listings
- **Pie Chart** — Prices/percentage of Different Property Types
- **Dot Plot** — Avg Price per m² by Country and City (toggle between Avg Price / Price per m²)
- **Bar Chart** — Property Features and Their Average Price (gym, parking spots)
- **Bar Chart** — Price by Bathrooms, Bedrooms & Age Group
- **Slicers** — Filter by Property Type, City, Country

### Dashboard 2
- **Data Table** — Amenities breakdown (elevator, swimming pool, gym, parking) per property
- **Map Visual** — % GT Sum of Price Growth by City and Country (geographic view)
- **Scatter Plot** — Causes of Property Delay Sales by Price Status and Property Type
- **Bar Charts** — Count of Days on Market by City and Property Type

---

## 🏙️ Cities Covered

Amsterdam · Berlin · Brussels · Lisbon · Madrid · Paris · Prague · Rome · Vienna · Warsaw

---

## 🔍 Analysis Questions Answered

- Which property types are most profitable?
- Do premium amenities (parking, elevator, gym, pool) command higher prices?
- Which properties stay longest on the market, and why?
- How does price grow across different European cities?
- What causes property sales delays (overpriced, below district average, slightly overpriced)?

---

## 🛠️ Tools & Technologies

- **Power BI Desktop** — Dashboard development
- **DAX** — Custom measures and calculated columns
- **Microsoft Bing Maps** — Geographic visualizations
- **Excel / CSV** — Data source

---

## 📁 Project Structure

```
real-estate-growth-tracker/
│
├── realstate.pbix          # Main Power BI project file
├── README.md               # Project documentation
│
├── screenshots/            # Dashboard screenshots
│   ├── dashboard1.png
│   └── dashboard2.png
│
└── data/                   # Source data (if applicable)
    └── real_estate_data.csv
```


---

## 📌 DAX Measures Used

```dax
-- Price Growth
Price Growth % = 
DIVIDE(
    [Current Price] - [Last Sold Price],
    [Last Sold Price]
) * 100

-- Avg Price per m²
Avg Price Per M = DIVIDE(SUM([Price]), SUM([Area SQM]))

-- Days on Market
Days On Market = DATEDIFF([Listing Date], [Sale Date], DAY)

-- Profitability Score
Profitability Score = 
SWITCH(TRUE(),
    [ROI %] > 30, "High",
    [ROI %] > 15, "Medium",
    [ROI %] > 5,  "Low",
    "Not Profitable"
)
```

---


## 📄 License

This project is for educational and portfolio purposes.
![image](https://github.com/saeedullah-tech/REAL-ESTATE-dashboard/blob/6f9f578ba86e02c6622f699c2b9a8d0818edd07e/Power%20BI%20Desktop%2003_04_2026%2012_18_36.png)
