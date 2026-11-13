# 🛒 E-Commerce Supply Chain & Revenue Analysis Dashboard

A comprehensive Power BI analytical solution tracking **23.99M Total Revenue**, **89K Customers**, and **3,735 Cities / 27 States** across an end-to-end e-commerce supply chain dataset (`Dim_Customers`, `Dim_Date`, `Dim_Products`, `Fact_Orders`).

---

## 📊 Dashboard Overview & Architecture

The report is structured into **6 core analytical pages** designed to evaluate regional performance, customer spending distribution, order fulfillment friction, payment preferences, and top-performing merchandise categories:

1. **Overall Performance:** High-level executive KPIs and state-level volume/revenue rankings[page: 1].
2. **Revenue Analysis:** Statistical dispersion (Median, CV, StdDev) and quarterly revenue trend decomposition[page: 2].
3. **Revenue Strength & Momentum:** Order volume trends, Average Order Value (AOV), and MoM revenue growth percentages[page: 3].
4. **Order Analysis & Supply Chain Friction:** Delivery delays, order statuses (`delivered`, `shipped`, `canceled`), and high-risk delayed stock items[page: 4].
5. **Payment Analysis:** Installment range distribution, payment type breakdown (Credit Card vs. Wallet/Voucher/Debit), and canceled order exposure[page: 5].
6. **Top Products:** Product category volume rankings and detailed top-sold item catalogs[page: 6].

---

## 🔍 Key Analytical Findings by Page

### 1. Overall Performance (Page 1)
* **Macro Scale:** Manages **23.99M** in total revenue from **89K customers** spanning **27 states** and **3,735 cities**[cite: 1].
* **Customer Volume Drivers:** São Paulo leads customer concentration (`38K`), followed by Rio de Janeiro (`17K`) and Minas Gerais (`10K`)[cite: 1].
* **Revenue Correlation:** Revenue composition directly mirrors customer volume density—regions with higher customer counts yield proportionally higher sales volume[cite: 1].

### 2. Revenue Analysis (Page 2)
* **Statistical Rigor:** Median Revenue stands at **`$171.86`**, while Revenue CV is **`128.19%`**, highlighting high right-skewness and extreme value outliers[cite: 2].
* **Typical Spend Range:** Approximately **68% of customers** spend within the range of **`$76` – `$613`** (StdDev: `344.39`, Average: `268.65`)[cite: 2].
* **Growth Trajectory:** Demonstrates a strong upward trend from late 2023 through mid-2025, with a notable structural dip in Q3.[cite: 2].

### 3. Revenue Strength & Momentum (Page 3)
* **Stable AOV:** Average Order Value remains remarkably stable between **`$250` and `$357`** across quarterly cohorts, confirming that revenue expansion is driven by transaction volume rather than inflationary price hikes[cite: 3].
* **Seasonal Slumps:** MoM analysis reveals a sharp Q3 performance dip (e.g., `-60.67%` in September), indicating predictable seasonal lulls in late summer rather than structural customer defection[cite: 3].

### 4. Order Analysis & Supply Chain Delays (Page 4)
* **Fulfillment Health:** The vast majority of orders (`$23.5M` revenue) deliver successfully, while canceled/unavailable orders account for minor portions (`$89.05K` and `$76.8K`)[cite: 4].
* **High-Risk Bottlenecks:** Delayed shipments are heavily concentrated in specific categories like **health_beauty** and **perfumery** experiencing delays up to 1.5–2 years, requiring immediate supplier push-delivery optimization[cite: 4].

### 5. Payment Analysis (Page 5)
* **Credit Card Dominance:** **~73% of transactions** are driven by credit cards (`$17.5M`), followed by wallet (`$4.6M`), voucher (`$1.5M`), and debit card (`$0.1M`)[cite: 5].
* **Installment Behavior:** Most installment frequencies cluster within **10 installments**, and cancellations are not exclusively tied to high-value product categories or extreme installment terms, pointing to general delivery friction rather than credit default[cite: 5].

### 6. Top Products (Page 6)
* **Category Volume Leaders:** The `toys` category dominates order volume (`67K`), outperforming secondary categories like `health_beauty`, `bed_bath_table`, and `sports_leisure`[cite: 6].
* **Granular Tracking:** Utilizes structured product ID catalogs to monitor item-level sales frequency and ensure stock availability for high-velocity SKUs[cite: 6].

---

## 🛠️ Technical Stack & Data Model
* **Tool:** Microsoft Power BI Desktop
* **Data Source:** Star-schema relational model comprising:
  * `Dim_Customers` (Customer demographics and regional geography)
  * `Dim_Date` (Time intelligence hierarchies: Year, Quarter, Month)
  * `Dim_Products` (Category, product ID, and attributes)
  * `Fact_Orders` (Transactional grain: revenue, order status, payment type, installment range, delivery delays)
* **Design Standards:** Dark-mode executive dashboard aesthetic utilizing custom KPI cards, clustered bar charts, filled maps, and synchronized page-level slicers (`product_category`, `state_name`, `payment_type`).
