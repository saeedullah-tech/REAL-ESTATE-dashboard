
# 🏠 Real Estate Growth Tracker — Power BI Dashboard

An interactive Power BI dashboard designed to analyze **Property Pricing, Market Growth, Amenities Impact, Sales Delay Causes, and Geographic Distribution** across major European cities.

This project uncovers the hidden relationship between:
**Property Value – Location – Amenities – Market Speed** within a single analytical model that enables real estate decision-makers to see what traditional reports fail to reveal.

---

## 🖼️ Screenshots
![Images](https://github.com/saeedullah-tech/REAL-ESTATE-dashboard/blob/615215aca19ea5119874c2ede43daea642b0e615/Power%20BI%20Desktop%2003_04_2026%2012_18_36.png)

### Dashboard 1 — Price & Growth Analysis
![Images](https://github.com/saeedullah-tech/REAL-ESTATE-dashboard/blob/478561926d32a2a1eca5c53b12d2e515036d76b3/Power%20BI%20Desktop%2003_04_2026%2012_33_32.png)

### Dashboard 2 — Amenities & Delay Analysis
![Dashboard 2](https://github.com/saeedullah-tech/REAL-ESTATE-dashboard/blob/478561926d32a2a1eca5c53b12d2e515036d76b3/Power%20BI%20Desktop%2003_04_2026%2012_34_58.png)

## Project Objective

Transform complex, scattered real estate data into clear, actionable insights to:

- Measure actual property price growth across cities and countries
- Identify which property types generate the highest returns
- Evaluate the impact of premium amenities on pricing
- Detect properties with the longest time on market and understand why
- Analyze price per m² across geographic regions
- Connect poor listing data quality directly to sales delays and revenue loss

---

## Challenges in Real Estate Data

Real estate data is one of the most difficult types of data to analyze because it is:

- Distributed across **5,000+ property listings**
- Spread over multiple domains (Residential, Commercial, Mixed-Use, Retail, Office, Warehouse)
- Geographically sensitive — tied to **Latitude & Longitude coordinates**
- Operationally complex with overlapping variables (age, amenities, size, location)
- Lacking direct linkage between quality, cost, and risk in traditional reporting systems

---

## Tools & Techniques

- **Power BI Desktop**
- **Data Modeling**
- **DAX Measures**
- **KPI Design for Real Estate Analytics**
- **Microsoft Bing Maps Integration**
- **Data Storytelling**

---

## Key Metrics in the Dashboard

- Avg Price vs Target
- Sum of Price Growth
- Avg Price per m²
- Total Listings Count
- Days on Market by Property Type
- Amenities Impact on Avg Price
- Price by Bedrooms, Bathrooms & Age Group
- Property Classification Distribution (Sensitive / Confidential)
- Geographic Price Distribution (City & Country level)
- Risk Exposure by Price Status (Overpriced / Below District / Normal)
- Quality vs Compliance Scatter Analysis
- Cost by Property Domain
- Top High-Cost Property Owners
- Governance Scorecard

---

## Business Value

This project does not answer the question:

> *What is the average property price?*

It answers the more critical question:

> **Where is the organization losing value due to overpriced listings, poor data quality, and weak market positioning?**

The dashboard enables leadership to:

- Make risk-driven investment and pricing decisions
- Reduce remediation and long holding costs
- Improve listing compliance and data accuracy
- Target data quality improvements across property domains
- Establish accountability for data owners and listing agents

---

## Dashboard Sections

- **Governance Overview** — Top-level KPIs: Avg Price, Price Growth, Price per m², Total Listings
- **Compliance & Risk Analysis** — Price Status breakdown: Overpriced, Below District Average, Normal, Slightly Overpriced
- **Data Criticality & Sensitivity** — Property type distribution and pricing tier segments
- **Geographic Distribution** — Map visual showing Price Growth % by City and Country across Europe
- **Cost by Domain** — Avg Price and feature breakdown by property category
- **High-Cost Owners** — Top data owners with highest operational and listing costs
- **Quality vs Compliance** — Scatter analysis of price vs days on market per property type
- **Governance Operational Details** — Granular amenities table with elevator, pool, gym, and parking data per listing

---

## Cities Covered

Amsterdam · Berlin · Brussels · Lisbon · Madrid · Paris · Prague · Rome · Vienna · Warsaw

---

## DAX Measures Used

```dax
-- Price Growth
Price Growth % = 
DIVIDE(
    SUM([Current Price]) - SUM([Last Sold Price]),
    SUM([Last Sold Price])
) * 100

-- Avg Price per m²
Avg Price Per M = DIVIDE(SUM([Price]), SUM([Area SQM]))

-- Days on Market
Days On Market = DATEDIFF([Listing Date], [Sale Date], DAY)

-- Market Speed Classification
Market Speed = 
SWITCH(TRUE(),
    [Days On Market] <= 30, "Fast (0-30 days)",
    [Days On Market] <= 60, "Moderate (31-60 days)",
    [Days On Market] <= 90, "Slow (61-90 days)",
    "Very Slow (90+ days)"
)

-- Profitability Score
Profitability Score = 
SWITCH(TRUE(),
    [ROI %] > 30, "⭐⭐⭐ High",
    [ROI %] > 15, "⭐⭐ Medium",
    [ROI %] > 5,  "⭐ Low",
    "❌ Not Profitable"
)

-- Premium Amenities Score
Premium Score = 
(IF([Parking] = "Yes", 1, 0)) +
(IF([Pool]    = "Yes", 1, 0)) +
(IF([Gym]     = "Yes", 1, 0)) +
(IF([Elevator]= "Yes", 1, 0))
```

---

## Project Structure

```
real-estate-growth-tracker/
│
├── realstate.pbix            # Main Power BI project file
├── README.md                 # Project documentation
│
├── screenshots/              # Dashboard screenshots
│   ├── dashboard1.png
│   └── dashboard2.png
│
└── data/                     # Source data (if applicable)
    └── real_estate_data.csv
```
