# Revenue Growth and Market Expansion Strategy in Global Superstore | Power BI

![banner](PICTURE/banner.png)

## Table of Contents  
1. [📌 Background & Overview](#-background--overview)  
2. [📂 Dataset Description & Data Structure](#-dataset-description--data-structure)  
3. [🧠 Design Thinking Process](#-design-thinking-process)  
4. [💡 Key Insights & Visualizations](#-key-insights--visualizations)  
5. [🔎 Final Conclusion & Recommendations](#-final-conclusion--recommendations)

## 📌 Background & Overview  

### What is this project about? 

🔥 Superstore is a global business with many markets. The company is growing fast and focuses on revenue growth and market expansion.

This project develops a strategic dashboard to analyze current performance and support decision-making for the upcoming year.

🎯 The goal is to answer three key questions:

- What is the current performance of Superstore?

- What is the expansion strategy in each market next year?

- Which products should be prioritized for strategic growth?

### 👤 Who is this project for?  

- Senior Managers evaluate business performance to drive next year’s strategic decisions.
  
- Marketing and sales teams monitor performance to adjust plans and tactical actions.

- Data analysts & business analysts extract insights to support and validate strategic choices.

## 📂 Dataset Description & Data Structure  

### Data Source  
- Source: Kaggle
- Size: 51,290 rows in Orders table

### Data Structure 
- The dataset consists of three tables: Orders, Returns, and People
  
<details>
  <summary>Table 1: Orders</summary>
  
| Column Name | Data Type | Description |
|---|---|---|
| Order ID | VARCHAR | Unique identifier for each order |
| Order Date | DATE | Date when the order was placed |
| Ship Date | DATE | Date when the order was shipped |
| Ship Mode | VARCHAR | Shipping method (e.g. Standard Class, First Class) |
| Customer ID | VARCHAR | Unique identifier for each customer |
| Customer Name | VARCHAR | Full name of the customer |
| Segment | VARCHAR | Customer segment (e.g. Consumer, Corporate, Home Office) |
| City | VARCHAR | City of the delivery address |
| State | VARCHAR | State or province of the delivery address |
| Country | VARCHAR | Country of the delivery address |
| Postal Code | FLOAT | Postal/ZIP code of the delivery address |
| Market | VARCHAR | Regional market (e.g. US, EU, APAC) |
| Region | VARCHAR | Geographic region within the market |
| Product ID | VARCHAR | Unique identifier for each product |
| Category | VARCHAR | Product category (e.g. Furniture, Technology, Office Supplies) |
| Sub-Category | VARCHAR | Product sub-category |
| Product Name | VARCHAR | Full name of the product |
| Sales | FLOAT | Revenue generated from the order |
| Quantity | INTEGER | Number of product units in the order |
| Profit | FLOAT | Profit earned from the order |
</details>

<details>
  <summary> Table 2: Returns</summary>
  
| Column Name | Data Type | Description |
|---|---|---|
| Returned | VARCHAR | Return status of the order (value: "Yes" or "No") |
| Order ID | VARCHAR | Identifier of the returned order, links to the Orders table |

</details>

<details>
  <summary> Table 3: People</summary>
  
| Column Name | Data Type | Description |
|---|---|---|
| Person | VARCHAR | Name of the sales representative |
| Region | VARCHAR | Region that the sales representative is responsible for |

</details>

### Data Relationships

![Data Modeling](PICTURE/modeling.png)

## 🧠 Design Thinking Process  

1️⃣ Empathize  
2️⃣ Define point of view  
3️⃣ Ideate  
4️⃣ Prototype and review  
<details>
<summary>Click to toggle</summary>
🧠 
</details>

## 💡 Key Insights & Visualizations  

#### I. Overview
![dashboard_page1](PICTURE/dashboard_page1.png)

📌 Key Insights:   

1. Business Performance in 2014
- Revenue reached $4.30M, a significant increase of +26.3% YoY. Strong revenue growth.
- Profit increased +23.9% YoY to $504K. Profit growth is slower than revenue growth, indicating declining efficiency.
- Orders increased +26.9%. Growth is primarily driven by order volume rather than value per order (AOV slightly declining)
- Profit in decreased by -1.87% YoY. This is a sign of margin pressure during revenue growth.
- Return Rate has improved with a decrease of -3.6% YoY, but at 4.55%, it remains high and requires attention.

2. Yearly Trends of Revenue, Profit, and Margin
- Revenue grew steadily from $2.3M (2011) to $4.3M (2014)
- Profit followed a similar trend (from $0.2M to $0.5M)
- Profit Margin remained relatively stable (~11–12%) over the years 
- Margin declined to 11.73% in 2014 after a steady upward trend in previous years
  
&nbsp; **Insight**:  Growth is consistent over time, and margin is low,→ structural growth. The decline in 2014 is a warning signal -> Strategy in 2015: Grow revenue while improving margin quality

3. Monthly Trends in 2014
- Revenue was highest in November ($0.56M) and lowest in February ($0.18M)
- YoY Revenue positive in all months (~+10-48%)
- Profit and Orders trends are quite similar to the revenue
- Margin showed a different trend: peaked early in the year (March ~14.2%) but decreased during the Q4 high-growth period. 
- Return rate highest (5.71%) in  February (the month with the lowest revenue, profit, and orders). 

 &nbsp; **Insight**: Business is seasonal-driven, Q4 drives revenue but reduces margin → Need careful campaign planning in Q4

4. Geographic Profitability
- Global presence in 138 countries, but 30 countries are reporting losses.
- Losses are concentrated in EMEA and LATAM, accounting for nearly half of all loss-making countries and more than 50% of total losses
  
&nbsp; **Insight**: Expansion is aggressive but lacks profitability control

5. Market in Revenue, Revenue Growth, and Profit Margin
- There are 7 markets with varying revenue contributions.
- EMEA has the highest revenue growth (+47.4%) but the lowest margin (7.49%)
- Canada has the smallest revenue ($0.02M) but the highest margin (25.88%)
- APAC has the highest revenue ($1.21M) but below-average margin (11.62%)
- EU is the most stable ($1.04M Revenue, 12.37% Margin)

&nbsp; **Insight**: The performance in every market is very different -> Each market requires different strategic action.

6. Category in Revenue, Revenue Growth, and Profit Margin
- There are 3 categories
- Technology has the highest revenue ($1.6M) and the highest margin (14.5%)
- Furniture has the lowest margin (6.5%)
- Office Supplies has the highest growth (+29.2%) and a high margin (13.8%)

&nbsp; **Insight**: Growth is driven by high-margin categories (Technology) → should be prioritized. Need to fix underperforming Furniture (especially sub-category level)

#### II. Market Analysis
![dashboard_page2](PICTURE/dashboard_page2.png)

📌 Key Insights:   
1. Revenue distribution by Market
- Based on Pareto analysis, categorizing markets into two groups: 4 Core (APAC, EU, US, LATAM) and 3 Small (EMEA, Africa, Canada)
- Core markets contribute 85.9% total revenue
  
&nbsp; **Insight**: Growth strategy should focus on scaling core markets, not small ones

2. Growth-Profitability Matrix
- Apply the matrix for 2 groups: core and small market
- Markets are segmented into 8 strategic groups based on Market Tier, Revenue Growth, and Profit Margin (2×2×2 framework)

<details>
<summary>Proposed Framework</summary>
  
|Market Tier| Revenue Growth| Profit Margin| Market Strategy|
|---|---|---|---|
|Core|High|High|DOMINATE|
|Core|High|Low|FIX MARGIN|
|Core|Low|High|RE-IGNITE|
|Core|Low|Low|RESTRUCTURE|
|Small|High|High|INCUBATE|
|Small|High|Low|VALIDATE|
|Small|Low|High|MAINTAIN|
|Small|Low|Low|MONITOR|
</details>

3. Top growth or bottom margin countries
- Top 1 growth revenue is Quata with +18,000% (margin 22.6%). A stunning and surprising number. Top 6 growth revenue is over 1,800%
- 6 Countries have a bottom Margin (<-150%). These extreme values require validation by combining revenue scale and loss to assess real impact

&nbsp; **Insight**: Identify outperformers to understand their growth levers. Simultaneously, analyze loss-making or low-margin countries to develop turnaround plans or exit paths

4. Profit Margin by Market and Category
- Canada has the highest margin in both 3 Categories (>20%).
- Most markets achieve the highest margin in Technology and the lowest in Furniture
- EMEA has a low margin in all 3 categories, the highest in Technology with only 11% (< Avg overall 11.73%)

&nbsp; **Insight**: Identify the top-performing categories within each market to scale up. For EMEA, a review is required to address ongoing issues. 

5. Return rate by market
- Core markets: high return rate and small markets: 0%
- EU: lowest orders in core (1,538) but highest return rate (6.5%)
- APAC: highest orders (1,885) but lowest return rate (5.04%)

👉 The following **next actions** aim to drive revenue growth by optimizing product mix and reviewing underperforming countries, with a focus on scaling core markets and selectively managing smaller markets.

| Market | Strategy | Next actions |
|--------|----------|--------------|
| EU | DOMINATE | Scale high-margin products; optimize product mix; reduce returns; review underperforming countries |
| US | RE-IGNITE | Shift away from low-margin Furniture; scale high-margin products; increase AOV through bundling and upsell |
| APAC | RESTRUCTURE | Improve product mix toward higher-margin; optimize pricing and discounting; review underperforming countries |
| LATAM | RESTRUCTURE | Simplify product portfolio; reduce low-margin products; apply selective price increases; review loss concentration |
| EMEA | VALIDATE | Improve product mix and pricing; focus on profitable SKUs; review loss concentration before scaling |
| Africa | MAINTAIN | Maintain efficient operations; selectively expand high-margin products |
| Canada | MAINTAIN | Maintain niche positioning; focus on profitability |

These actions aim to balance short-term performance improvement with long-term scalable growth, ensuring resources are allocated to the most impactful opportunities.

#### III. Product Analysis
![dashboard_page3](PICTURE/dashboard_page3.png)

📌 Key Insights:   
1. Pareto Analysis
- 8 sub-categories drive 80% revenue → need focus
- Technology dominates the core group

2. Tables Crisis
- Only sub-category with loss (-$30.55K in 2014)
- Margin -12.5% → main reason dragging Furniture
- High return rate (6.32%)
- Losses over 4 years (total > $60K)
- Losses in 5/7 markets -> no clear product-market fit

&nbsp; **Insight**: Tables is a big problem -> Increase price or remove

3. BCG Matrix 
- Stars: Phones, Copiers (High Revenue, High Margin)
- Question Mark: Paper, Arts (Low Revenue, High Margin)
- Cash Cows: Accessories, Storage (High Revenue,  Margin)
- Dogs: Tables, Binders, Supplies (Low Revenue, Low Margin)

Product strategy should prioritize Stars, optimize Cash Cows, fix/remove Dogs. 

4. Sub-Category x Market and Top 10 Products
- Identify product-market fit by analyzing which products perform best in each market
- Top 10 products by revenue, quantity, ASP, return rate

&nbsp; **Insight**: Optimize product mix, cross-sell, upsell


## 🔎 Final Conclusion & Recommendations 

- Revenue is growing strongly (+26% YoY) but profitability is declining
- Growth is concentrated in a few core markets and categories
- Significant imbalance across markets and products
- Small markets and low-performing products do not drive meaningful growth

🔥 Final Strategic Statement

“Revenue growth should be driven by scaling core markets and high-performing products, while improving margin quality and managing smaller markets as strategic options rather than primary growth drivers.”

🚀 Strategic Priorities
1. Scale What Works
- Core markets (EU, US, APAC)
- High-margin categories (Technology)
2. Fix Profitability Issues
- Reduce low-margin products (Furniture, Tables)
- Improve pricing & discount strategy
3. Optimize Quality
- Control risk in loss-making countries/ products
- Reduce return rate

