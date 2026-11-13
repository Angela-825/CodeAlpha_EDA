# CodeAlpha_EDA

Exploratory Data Analysis of the Superstore Sales dataset using Python.

Completed as part of the **CodeAlpha Virtual Data Analytics Internship** (Task 2: Exploratory Data Analysis).

---

## 1. Project Objective

To explore the Superstore sales data, understand how sales are distributed across time, products, regions and customer segments, detect data quality issues and anomalies, and test assumptions with statistics.

## 2. Questions Answered

1. How have sales changed over time, and is there a seasonal pattern?
2. Which categories and sub-categories generate the most and the least sales?
3. Which regions, states and cities perform best?
4. Which customer segments and individual customers contribute the most?
5. Does delivery time differ by ship mode?
6. Are there outliers or anomalies in the sales values?

## 3. Dataset

- **Source:** Superstore Sales Dataset (Kaggle), file `train.csv`
- **Size:** 9,800 rows and 18 columns
- **Period covered:** 3 January 2015 to 30 December 2018
- **Key columns:** Order Date, Ship Date, Ship Mode, Customer ID, Segment, City, State, Region, Category, Sub-Category, Product Name, Sales
- **Limitation:** This version has no Profit, Quantity or Discount columns, so the analysis focuses on sales, not profitability.

## 4. Tools and Libraries

- Python 3
- pandas and NumPy (data handling)
- Matplotlib and Seaborn (visualization)
- SciPy (statistical tests)
- Jupyter Notebook in VS Code

## 5. Methodology

**Data inspection**
- Checked the shape, column types and a sample of rows.

**Data cleaning**
- Found 11 missing values in Postal Code, all for Burlington, Vermont. Filled them with that city's ZIP code (05401) and converted Postal Code to text, since it is an identifier.
- Confirmed there were no duplicate rows.
- Converted Order Date and Ship Date from text to datetime (day/month/year format).
- Created new columns: Year, Month, Month Name and Delivery Days (ship date minus order date).
- Dropped Row ID (a counter) and Country (only one value).

**Exploratory analysis**
- Summary statistics and the distribution of Sales, including a log scale because of heavy skew.
- Breakdowns by category, sub-category, region, state, city, segment, customer and ship mode.
- Time-series analysis of yearly and monthly sales, plus a seasonality check.

**Outlier detection**
- Used the IQR method and a box plot. Outliers were kept because they are genuine high-value purchases.

**Hypothesis testing**
- Kruskal-Wallis tests (non-parametric, because Sales is heavily skewed) at a 0.05 significance level.

## 6. Key Findings

- **Sales trend:** Sales dipped about 4% in 2016 (from about 479,856 to 459,436), then grew about 31% in 2017 (about 600,193) and about 20% in 2018 (about 722,052).
- **Seasonality:** November, December and September are the strongest months. February, January and April are the weakest. The highest single month is November 2018 (about 117,938).
- **Products:** Technology generates the most sales (about 36.6%), followed by Furniture (32.2%) and Office Supplies (31.2%), even though Office Supplies has the most order lines (about 60%). Phones and Chairs are the top sub-categories.
- **Geography:** The West is the top region (about 31.4%). California (about 446,306) and New York (about 306,361) are the top states, and the top three states make up about 41% of sales.
- **Customers:** Consumer is the biggest segment (about 50.8%). Sales are spread across 793 customers, and the top 10 account for only about 6.8% of sales.
- **Shipping:** Average delivery is about 0 days for Same Day, 2.2 for First Class, 3.3 for Second Class and 5 for Standard Class, the most used mode.
- **Outliers:** About 11.7% of order lines are outliers (above about 500.64), but they account for about 64.3% of total sales. The largest are copiers, videoconferencing units and printers.
- **Hypothesis tests:**
  - Sales per order line does **not** differ significantly between segments (Kruskal-Wallis H = 0.439, p = 0.80).
  - Delivery time **does** differ significantly between ship modes (H = 5937.8, p < 0.001).

## 7. Recommendations

1. Prepare stock, staffing and promotions for September to December, and run campaigns in the slow months (January, February and April).
2. Prioritise Technology and Furniture, especially Phones and Chairs, and review the weakest sub-categories (Fasteners, Labels and Envelopes).
3. Investigate why the South has the lowest sales share (about 17.2%) before deciding on further investment there.
4. Track the large equipment orders separately and build relationships with the customers who place them, since they drive most of the revenue.

## 8. Limitations

- The dataset has no profit, quantity or discount data, so profitability cannot be assessed.
- All orders are from one country (the United States).
- A small number of very large orders have a large influence on total sales.
- Reasons behind patterns, such as holiday-season peaks, are plausible explanations and are not confirmed by the data.

## 9. Repository Structure

```
CodeAlpha_EDA/
├── Superstore_EDA.ipynb      # Main analysis notebook
├── train.csv                 # Dataset
├── requirements.txt          # Python dependencies
└── README.md                 # Project documentation
```

## 10. How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/Angela-825/CodeAlpha_EDA.git
   ```
2. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Open `Superstore_EDA.ipynb` in Jupyter Notebook or VS Code and run all cells.

## 11. Video Walkthrough

https://lnkd.in/p/eihyNnep

## 12. Author

**Angela Iseriehen**
 https://www.linkedin.com/in/angela-iseriehen-052732120 (https://github.com/Angela-825)

---

*Completed as part of the CodeAlpha Data Analytics Internship.*