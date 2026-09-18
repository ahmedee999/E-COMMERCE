# E-Commerce Marketplace Analytics

An end-to-end e-commerce data analytics project analyzing orders, customers, products, revenue, profitability, and return patterns using **Python, SQL, and Power BI**.

## 👥 Team & Contributions

This project was developed collaboratively as part of the **Digital Egypt Pioneers Initiative (DEPI)**.

| Team Member      | Main Contribution                           |
| ---------------- | ------------------------------------------- |
| Rojeh Tamer      | Data Modeling, DAX & Power BI Dashboard     |
| Hady Abohany     | Revenue & Profitability Analysis            |
| Yousef Sayed     | Customer Lifecycle & Activation Analysis    |
| Ahmed Mohamed    | Customer Valuation & Top Spender Analysis   |
| Ibrahim Desouky  | Product & Device Channel Analysis           |
| **Ahmed Shaban** | **Return Rate & Operational Risk Analysis** |

### My Contribution

* Analyzed order return rates across regions.
* Identified the main return reasons.
* Analyzed operational risks related to returned orders.
* Used SQL and data analysis to extract actionable insights.

---

## 📁 Project Structure

```text
E-COMMERCE/
├── data/
│   ├── ecommerce_data.sql
│   └── ecommerce_data.xlsx
├── notebooks/
│   └── ecommerce_project2_notebook_4.ipynb
├── dashboard/
│   └── E_Commerce_Dashboard.pbix
├── presentation/
│   └── E-Commerce_Analytics_Presentation.pdf
└── README.md
```

---

## 📊 Dataset

The dataset contains **32 months of e-commerce data** across:

* 6 regions: Cairo, Giza, Alexandria, Jeddah, Riyadh, Abu Dhabi
* 2 channels: Web and App
* 3,000 customers
* 15,000 orders
* 38,655 order items
* 1,531 returned orders

### Main Tables

| Table            | Records | Description                  |
| ---------------- | ------: | ---------------------------- |
| `p2_users`       |   3,000 | Customer information         |
| `p2_orders`      |  15,000 | Order and financial data     |
| `p2_order_items` |  38,655 | Product and quantity details |
| `p2_returns`     |   1,531 | Returned orders and reasons  |

---

## 📓 Python EDA

The Jupyter Notebook covers:

* Data cleaning and preprocessing
* Missing-value validation
* Date and data-type handling
* Customer lifecycle analysis
* Revenue analysis
* Product/category analysis
* Return analysis
* Data visualization

### Main Libraries

```text
Python
Pandas
NumPy
Matplotlib
Seaborn
Jupyter Notebook
```

---

## 🗄️ SQL Analysis

SQL was used to answer business questions and analyze:

* Monthly revenue
* Discounts
* Profitability
* Customer behavior
* Order performance
* Return rates
* Regional performance

### Example

```sql
SELECT 
    strftime('%Y-%m', order_dt) AS month,
    SUM(gmv) AS gross_revenue,
    SUM(gmv - discount) AS net_revenue,
    ROUND(
        SUM(discount) * 100.0 / SUM(gmv),
        2
    ) AS discount_rate_pct
FROM p2_orders
GROUP BY month
ORDER BY month ASC;
```

---

## 📈 Power BI Dashboard

The Power BI dashboard provides interactive analysis of:

* Revenue
* Profitability
* Margin Rate
* Customer performance
* Regional performance
* Product categories
* Return rates

### Core DAX Measures

**Net Revenue**

```DAX
Net Revenue =
SUM(p2_orders[gmv]) -
SUM(p2_orders[discount])
```

**Total Margin**

```DAX
Total Margin =
SUM(p2_orders[gmv]) -
SUM(p2_orders[discount]) -
SUM(p2_orders[cogs]) -
SUM(p2_orders[shipping_cost])
```

**Margin Rate**

```DAX
Margin Rate % =
DIVIDE([Total Margin], [Net Revenue], 0)
```

**Return Rate**

```DAX
Return Rate % =
DIVIDE(
    DISTINCTCOUNT(p2_returns[order_id]),
    DISTINCTCOUNT(p2_orders[order_id]),
    0
)
```

---

## 🎯 Key Business Insights

* GMV increased significantly during the analyzed period, reaching a peak of approximately **$245.4K in March 2025**.
* Regional profit margins remained relatively consistent, ranging from approximately **20.4% to 21.5%**.
* A high percentage of purchasing customers placed repeat orders.
* **Electronics (ELEC)** generated the highest revenue among product categories.
* The overall order return rate was approximately **10%**.
* **Damaged products** and **wrong size** were among the main return reasons.

---

## 🛠️ Tech Stack

* **Python:** Pandas, NumPy, Matplotlib, Seaborn
* **SQL:** SQLite
* **Business Intelligence:** Power BI, DAX
* **Data:** Microsoft Excel
* **Documentation:** Markdown
* **Notebook:** Jupyter

---

## 👤 Author

### Ahmed Shaban

Computer Science Student | Data Analytics Enthusiast

**Focus:** Python • SQL • Data Analysis • Power BI

---

## 📌 Project Type

**E-Commerce Data Analytics | DEPI Project**

This project demonstrates an end-to-end analytics workflow from raw data and SQL analysis to Python exploration, business insights, and Power BI visualization.
