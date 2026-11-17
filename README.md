# E-Commerce Profitability & Business Performance Analysis

An end-to-end data analytics project that takes raw e-commerce order data through cleaning, feature engineering, exploratory analysis in **Python**, business queries in **MySQL**, and an interactive **Power BI** dashboard to understand sales, profit, products, categories, regions and time trends.

**Workflow:** Raw Excel Data → Python (Google Colab) → Cleaned CSV → MySQL → Power BI Dashboard → Insights & Recommendations

---

## Table of Contents
- [Project Objective](#project-objective)
- [Dataset](#dataset)
- [Tools & Technologies](#tools--technologies)
- [Project Structure](#project-structure)
- [Methodology](#methodology)
- [Key Metrics](#key-metrics)
- [Key Insights](#key-insights)
- [Recommendations](#recommendations)
- [Power BI Dashboard](#power-bi-dashboard)
- [Limitations](#limitations)
- [How to Run](#how-to-run)
- [Author](#author)

---

## Project Objective
To analyse e-commerce order data and answer practical business questions:
- How much **sales, profit and quantity** is the business generating?
- Which **products, categories and regions** perform best and worst?
- How do **sales and profit change over time** (monthly, quarterly, yearly)?
- What is the **profit margin**, and where is it strong or weak?
- Are there products with **high sales but relatively low profit**?

## Dataset
| Item | Details |
|---|---|
| Records | 3,500 orders |
| Period | 1 Jan 2022 – 9 Sep 2024 |
| Raw columns (7) | `Order Date`, `Product Name`, `Category`, `Region`, `Quantity`, `Sales`, `Profit` |
| Engineered columns (5) | `Year`, `Month`, `Month_Name`, `Quarter`, `Profit_Margin` |
| Categories | Accessories, Electronics, Office |
| Regions | East, North, South, West |
| Products | 10 (Camera, Monitor, Printer, Mouse, Smartphone, Smartwatch, Keyboard, Tablet, Laptop, Headphones) |

The cleaned dataset has **no missing values and no duplicate rows**.

## Tools & Technologies
- **Python** (Pandas, Matplotlib) in Google Colab: cleaning, feature engineering, EDA, charts
- **MySQL**: database creation, data import and SQL business analysis
- **Power BI**: data model, KPI cards, charts, slicers and multi-page dashboard
- **Excel / CSV**: raw and cleaned data storage

## Project Structure
```
Ecommerce-Profitability-Business-Performance-Analysis/
│
├── data/
│   ├── Ecommerce_Raw_Sales_Data.xlsx
│   └── Ecommerce_Cleaned_Data.csv
├── notebooks/
│   └── Ecommerce_Profitability_Analysis.ipynb
├── sql/
│   └── Ecommerce_Profitability_SQL_Analysis.sql
├── dashboard/
│   └── Ecommerce_Business_Performance_Dashboard.pbix
├── docs/
│   └── Ecommerce_Profitability_Project_Documentation.docx
├── images/            # dashboard screenshots
└── README.md
```

## Methodology

**1. Data Understanding & Cleaning**
- Loaded the 3,500-row dataset and checked shape, columns and data types
- Checked missing values, duplicates and descriptive statistics
- Converted `Order Date` to datetime and validated for invalid values (non-positive quantity, negative sales)

**2. Feature Engineering**
- Extracted `Year`, `Month`, `Month_Name` and `Quarter` from the order date
- Created `Profit_Margin = (Profit / Sales) × 100`

**3. Exploratory Data Analysis (Python)**
- Total sales, profit, quantity, transactions and average order value
- Sales / profit / quantity by category, region, product and time period
- Top 5 and bottom 5 products by sales and profit
- Correlation between sales, profit and quantity
- Visualisations: bar charts, line charts and a sales-vs-profit scatter plot

**4. SQL Analysis (MySQL)**
- Imported the cleaned CSV into a MySQL database
- Wrote queries for KPIs, category / region / product breakdowns, yearly and monthly trends, profit margins, top and bottom products, and high-sales / low-profit products

**5. Power BI Dashboard**
- Built a multi-page report with KPI cards, column / bar / line / donut / scatter charts, tables and slicers

## Key Metrics
| Metric | Value |
|---|---|
| Total Sales | 10,667,881 |
| Total Profit | 1,844,665 |
| Total Quantity Sold | 17,261 units |
| Total Orders | 3,500 |
| Overall Profit Margin | 17.29% |
| Average Sales per Order | 3,047.97 |

## Key Insights

**Category**
- **Electronics** is the largest category with about **50% of total sales** (5.33M) and the highest profit (923K).
- **Accessories** contributes about 40% of sales (4.25M).
- **Office** (Printer only) contributes about 10% of sales and has the lowest margin (16.94%).

**Region**
- **West** leads in both sales (2.84M) and profit (495K).
- **North** is the lowest on both measures, with sales of 2.49M and the lowest margin (17.13%).
- Regional differences are small, with margins between 17.1% and 17.4%.

**Products**
- **Camera** is the top product by sales (1.18M) and profit (208K).
- **Laptop** has the **highest margin (18.47%)** but ranks only 9th in sales, so it is a high-margin product with room to grow volume.
- **Tablet** has the **lowest margin (16.36%)**, with the lowest total profit among the top products by sales.

**Time**
- Sales rose from 3.26M in 2022 to 3.79M in 2023, the peak year.
- Profit margin fell from about 17.6% in 2022–2023 to **16.7% in 2024**, even though 2024 unit sales were the highest at 5,949 units. Selling more units at a lower margin is worth investigating.
- **May** is the strongest month for sales overall (1.03M).

**Profitability**
- **No order in the dataset is loss-making**, and profit margins are consistently close to 17% across categories, regions and products.

## Recommendations
1. **Grow high-margin products:** promote Laptop (18.47% margin) through bundles and targeted campaigns, since its sales rank is low relative to its margin.
2. **Review Tablet pricing and costs:** it has the lowest margin (16.36%), so a small pricing or cost improvement could lift overall profit.
3. **Investigate the 2024 margin decline:** check whether discounts, cost increases or product mix caused the drop from about 17.6% to 16.7%.
4. **Strengthen the North region:** it is the weakest region, so test region-specific promotions or inventory focus.
5. **Plan around seasonality:** prepare stock and campaigns ahead of high-sales months such as May.
6. **Protect the Electronics core:** with half of all sales, keep Electronics stock and supply stable.

## Power BI Dashboard
The `.pbix` report contains multiple pages with KPI cards, slicers and charts covering sales, profit, quantity, product, category, region and time-based analysis.

> Add screenshots here after exporting them from Power BI:
>
> `![Dashboard Overview](images/dashboard_overview.png)`

## Limitations
- The dataset has only 7 original columns, so there is no customer, discount, cost or shipping data. This limits deeper profitability analysis.
- **2024 data ends on 9 Sep 2024**, so yearly sales for 2024 are not directly comparable with the full years 2022 and 2023.
- Profit margins are very uniform and no loss-making orders exist, which suggests the data may be synthetic or heavily simplified. Findings should be read as a demonstration of the analytics workflow.
- Currency is not specified in the source data.

## How to Run
1. **Python:** open the notebook in Google Colab or Jupyter, upload `Ecommerce_Raw_Sales_Data.xlsx`, and run all cells. It exports `Ecommerce_Cleaned_Data.csv`.
2. **MySQL:** create the database and table, import the cleaned CSV, then run the queries in the `.sql` file. Make sure the table name in the queries matches your table.
3. **Power BI:** open the `.pbix` file in Power BI Desktop. If prompted, point the data source to the cleaned CSV.

## Author
**Pondara Uday Kiran**
Aspiring Data Analyst | B.Sc. Computer Science
Hyderabad, Telangana, India

- GitHub: [pondaraudaykiran07-sketch](https://github.com/pondaraudaykiran07-sketch)
- LinkedIn: *add your profile link*
- Email: *add your email*

---
If you found this project useful, feel free to star the repository.
