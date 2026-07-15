<img width="1877" height="635" alt="Corporate finance analysis dashboard" src="https://github.com/user-attachments/assets/ff96b5dd-647b-4195-b2e5-7607d0a94784" />

# Corporate Finance Analytics: Revenue Trajectory & Profit Leakage Audit
---

## 📈 Executive Summary
This project analyzes the financial performance of a global logistics and retail corporation managing **$14.9M in Gross Revenue**. While top-line sales show consistent growth, the business faces severe **margin compression**—retaining only **$1.52M in Net Profit (a 10.20% aggregate operating margin)**. 

By engineering an interactive Excel financial model, this analysis bypasses surface-level sales metrics to isolate hidden operational friction, structural cost leakages, and regional logistics inefficiencies.

📊 **[Link to Download Excel Dashboard](./Your_Excel_Workbook_Name.xlsx)**

---

## 🏛️ Business Challenges & Core Questions 
The Executive Board required an evaluation of corporate efficiency to answer four strategic questions:
1. **Revenue & Growth Trajectory:** Which product lines and geographic markets are driving top-line growth?
2. **Margin Compression Breakdown:** Why is net profit failing to keep pace with revenue expansion?
3. **Cost Leakage Identification:** Where are specific operational inefficiencies and financial leaks occurring?
4. **Forward-Looking ROI Optimization:** What strategic cost-cutting measures will yield the highest return?

---

## 🧹 Data Quality & Financial Governance 
The raw transactional ledger contained formatting defects and incomplete data inputs that required structural data governance:
* **Missing Structural Metrics:** The `Product Base Margin` column contained 63 blank rows. Leaving these blank would break downstream aggregate charts.
* **Treatment Applied:** Applied a **Mean Imputation** methodology. Filtered the active records, extracted the true baseline average product margin (**51.0%**), and programmatically mass-inserted this value into the 63 empty records using Excel's `Go To Special > Blanks` framework.
* **Data Typology & Integrity Check:** Validated text strings and aligned numeric values into an official Excel Table (`SalesData`) to eliminate formula drift. Removed empty filler rows to create an unbroken data schema.

---

## ⚙️ Derived Metrics & Formula Engineering ("Process" Phase)
To serve as diagnostic sensors for the corporate engine, three custom calculated columns were engineered into the data architecture:

1. **Transactional Profit Margin %**
   * *Formula:* `=[@Profit] / [@Sales]`
   * *Purpose:* Measures real-world bottom-line efficiency per transaction.
2. **Total Cost of Sales**
   * *Formula:* `=[@Sales] - [@Profit]`
   * *Purpose:* Aggregates the combined cost of goods sold (COGS) and localized operating expenses (OpEx).
3. **Operational Leakage Flag**
   * *Formula:* `=IF([@Profit] < 0, "Leakage", "Healthy")`
   * *Purpose:* Instantly isolates loss-making fulfillment routes and transactions.

---

## 🔍 Data Analysis & Executive Insights ("Analyze" Phase)

### 1. The Category Margin Trap (Furniture vs. Office Supplies)
* **The Insight:** Market demand for **Furniture** is massive, generating **$5,178,591** in sales. However, it returns an incredibly compressed net profit of just **$117,433**—a razor-thin **2.27% operating margin**. 
* **The Contrast:** By comparison, **Office Supplies** generates less top-line revenue ($3,752,762) but delivers **$518,021 in pure net profit** at a highly efficient **13.80% margin**.

### 2. Deep Operational Cost Leakages (The Furniture Sub-Categories)
By auditing the underlying base margins against actual profit yields, the "smoking guns" of the business were identified:
* **Tables:** Theoretical factory base margin of **69.32%**, but finishes with a massive real-world loss of **-$99,062.50**.
* **Bookcases:** Theoretical base margin of **65.99%**, but bleeds out **-$33,582.13**.
* **Analysis:** These items are highly profitable on paper. Their failure to generate positive returns points directly to operational friction: bloated freight charges, fulfillment inefficiencies, or uncontrolled promotional discounting.

### 3. Regional Volume vs. Value Anomaly (West vs. Ontario)
* **The Insight:** The **West Region** is the company's largest absolute sales engine, generating **$3,597,547** in sales. 
* **The Variance:** However, the **Ontario Region** generates **$346,869 in net profit** on a smaller sales volume ($3,063,212). The West region is heavily weighed down by systemic delivery and operational overheads, deflating its efficiency to **8.26%** compared to Ontario's **11.32%**.

---

## 🚀 Prescriptive Strategic Action Plan ("Act" Phase)
To maximize corporate ROI and halt capital erosion, the following data-backed recommendations have been presented to the board:

1. 🏷️ **Establish Furniture Pricing Floors:** Enforce a mandatory strict cap on sales representative discounting for the *Tables* and *Bookcases* categories to protect the baseline margins.
2. 🚚 **Logistics Freight Audit in the West:** Initiate an immediate operational audit on shipping carriers and third-party logistics (3PL) in the *West Region* to identify why fulfillment costs are vastly higher than *Ontario*.
3. 🎯 **Budget Reallocation for Higher ROI:** Shift 10% to 15% of underperforming marketing capital away from low-margin *Furniture* items and pivot it toward high-efficiency *Technology* (14.81% margin) and *Office Supplies* (13.80% margin) lines to immediately boost corporate cash flow.

---

## 🛠️ Tech Stack & Methodology
* **Tool:** Microsoft Excel (Advanced Modeling)
* **Features Used:** Excel Tables, Data Validation, Imputation Modeling, Custom Financial Number Formatting (`0.0%;[Red]-0.0%`), Multi-Axis Combo PivotCharts, Dynamic Slicer Report Connections.
