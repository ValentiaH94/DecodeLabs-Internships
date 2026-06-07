DecodeLabs Internship – Ntsako Valentiah Baloyi

 Who Am I?

My name is Ntsako Valentiah Baloyi. I am a beginner in the field of Data Analytics, currently completing an internship with Decodelabs. This repository contains all the work I submitted during my internship — four tasks that together form a complete, real-world data analytics project.

 Details

Full Name Ntsako Valentiah Baloyi 
Email ntsakovalentia@gmail.com 
GitHub Username ValentiaH94 
Internship Organisation Decodelabs 
Internship Domain Data Analytics 

What Is This Repository About?

This repository documents a step-by-step data analytics project I completed during my Decodelabs internship. The project uses a real e-commerce dataset containing 1,200 sales records.

The four tasks follow a logical progression that mirrors how real data analysts work:


Raw Data → Clean It → Analyse It → Visualise It → Build a Dashboard
   ↑             ↑           ↑             ↑                ↑
(Given)      Task 1      Task 2         Task 3           Task 4

Each task builds directly on the one before it, showing growth and a complete understanding of the data analytics workflow.


Folder Structure

DecodeLabs-Internships/
│
├── Task 1/     ← Data Cleaning (Excel)
├── Task 2/     ← Exploratory Data Analysis (Excel/Statistics)
├── Task 3/     ← Data Visualisation (Databricks SQL)
├── Task 4/     ← Business Intelligence Dashboard (Power BI)
│
└── README.md   ← This file — overview of everything


Each folder contains one `.docx` file with my full written submission for that task.

 Task-by-Task Breakdown

 Task 1 — Data Cleaning
Folder `Task 1/`
Tool used:Microsoft Excel
Skill demonstrated:Preparing raw data for analysis

What I Did:
Before any analysis can happen, data must be clean and reliable. I received a raw e-commerce dataset with 1,200 rows and identified four categories of data quality problems. Here is exactly what I found and fixed:

Problem Found,Column Affected,What I Did,Result

 Missing values | Coupon Code | Filled all blank cells with the value `NA` | 0 missing values remaining |
| Duplicate records | Order ID (unique key) | Used Excel → Data → Remove Duplicates | 0 duplicates found |
| Wrong date format | Date | Standardised all dates to `YYYY-MM-DD` | All 1,200 dates correctly formatted |
| Inconsistent text & numbers | Product, Payment Method, Order Status, Referral Source, Quantity, Unit Price, Total Price, Revenue | Cleaned spelling, spacing, and number formats | Consistent data across all columns |

 Outcome:
All 1,200 records retained. Zero data lost. The dataset is 100% clean and ready for analysis.

Task 2 — Exploratory Data Analysis (EDA)
Folder: `Task 2/`
Tool used:Microsoft Excel (formulas, pivot tables)
Skill demonstrated:Asking and answering business questions using data

What Is EDA?
Exploratory Data Analysis means looking at the data carefully to discover patterns, trends, and unusual values — before drawing any formal conclusions. Think of it as "getting to know your data.

Questions I Investigated:

Question 1: What are the basic statistics for Total Price?
- Total number of orders: 1,200
- Average (mean) order value: R1,053.97
- Median order value: R769.38
- The median being lower than the mean tells us that a small number of very large orders are pulling the average up — this is useful business intelligence.

Question 2: What are the trends in Order Status?
- Most common status: Cancelled
- Second most common: Returned
- Third most common: Pending
- This is a concern for the business — it means many orders never complete successfully.

Question 3: Are there outliers in Unit Price?
- An outlier analysis was performed on the Unit Price column to identify unusually high or low prices that could distort analysis.

Question 4: Which products bring the most revenue?
- Laptop — highest revenue
- Printer — second highest
- Chair — third highest

Question 5: Which referral source brings the most orders?
- Instagram — most orders
- Email — second most
- Google— third most
- This tells the marketing team where to focus their advertising budget.

Outcome:
-Five key business questions answered. Actionable insights identified for marketing, inventory, and customer experience teams.


Task 3 — Data Visualisation
Folder: `Task 3/`
Tools used-Databricks free edition(SQL)
The  file contains screenshots of:
- The raw dataset displayed in Databricks
- The cleaned dataset displayed in Databricks
- The SQL queries I wrote

Uploaded the Dataset
1. Clicked Data on the left menu
2. Clicked Add Data→ Upload File
3. Uploaded the cleaned CSV file from Task 1
4. Databricks automatically created a table from the file

Created a SQL Notebook
1. Clicked New → Notebook
2. Selected SQL as the language
3. Attached the notebook to my cluster

Displayed the Raw Dataset
I ran this query to show the data before cleaning:

sql
SELECT *
FROM ecommerce_raw
LIMIT 20;

This showed all columns including missing values, inconsistent formatting, and messy data — the problems I fixed in Task 1.

Displayed the Cleaned Dataset
I ran this query to show the data after cleaning:

sql
SELECT *
FROM ecommerce_cleaned
LIMIT 20;

This showed the same dataset but fully cleaned — no missing values, no duplicates, consistent formatting throughout.

Total Revenue by Product
sql
SELECT Product, SUM(Revenue) AS TotalRevenue
FROM ecommerce_cleaned
GROUP BY Product
ORDER BY TotalRevenue DESC;


Total Orders by Referral Source
sql
SELECT ReferralSource, COUNT(OrderID) AS TotalOrders
FROM ecommerce_cleaned
GROUP BY ReferralSource
ORDER BY TotalOrders DESC;


 Order Status Breakdown
sql
SELECT OrderStatus, COUNT(OrderID) AS OrderCount
FROM ecommerce_cleaned
GROUP BY OrderStatus
ORDER BY OrderCount DESC;


Average Unit Price by Product
sql
SELECT Product, AVG(UnitPrice) AS AvgUnitPrice
FROM ecommerce_cleaned
GROUP BY Product
ORDER BY AvgUnitPrice DESC;

Raw Dataset vs Cleaned Dataset

| Issue | Raw Dataset | Cleaned Dataset |
|---|---|---|
| Missing values | Blank cells in Coupon Code column | Filled with NA |
| Duplicate records | Duplicate Order IDs present | All removed |
| Date format | Mixed and inconsistent | Standardised to YYYY-MM-DD |
| Text formatting | Inconsistent capitalisation and spacing | Fully standardised |
| Ready for analysis? | ❌ No | ✅ Yes |

Displaying both datasets in Databricks makes it immediately clear why data cleaning in Task 1 was essential. Running SQL on dirty data would have produced incorrect results.

What I Learned
- How to sign up for and use Databricks Community Edition
- How to upload a CSV file and create a table in Databricks
- How to create a SQL notebook and attach it to a cluster
- How to write SQL queries using SELECT, SUM, COUNT, AVG, GROUP BY, and ORDER BY
- How to compare raw and cleaned data side by side

 Task 4 — Power BI Dashboard 
Folder: `Task 4/`
Tool used: Microsoft Power BI
Skill demonstrated:Building interactive business intelligence dashboards

What Is Power BI?
Power BI is a professional business intelligence tool used by companies worldwide to create interactive dashboards. Unlike static Excel charts, a Power BI dashboard lets users click, filter, and drill down into the data in real time.

What I Did:
I combined everything from Tasks 1, 2, and 3 into a single, professional, interactive dashboard. The dashboard presents the key findings from the entire project in one visual interface.

The dashboard covers:
- Sales & Revenue Performance — total revenue, average order value, trends over time
- Order Status Distribution— proportion of completed, cancelled, returned, and pending orders
- Top Products by Revenue— which products are driving the most income
- Referral Source Analysis — which marketing channels bring in the most customers

Outcome:
-A fully functional Power BI dashboard. This is the kind of deliverable a junior data analyst would present to a manager or client at the end of a real project.


Tools & Technologies

| Tool | Version/Type | What I Used It For |
| Microsoft Excel| Desktop | Data cleaning, statistical analysis, charts (Tasks 1, 2) |
Databricks free edition(SQL)
Microsoft Power BI| Desktop (Free) | Interactive dashboard creation (Task 4) |
|Microsoft Word| `.docx` format | Writing up and documenting each task submission |
| GitHub| Web platform | Storing, organising, and sharing all work professionally |

What I Learned

This internship gave me hands-on experience with the full data analytics pipeline. Here is a summary of the specific skills I developed:

-Data Cleaning— identifying and resolving missing values, duplicates, and formatting errors
-Statistical Analysis — calculating mean, median, and count; identifying outliers
-Business Thinking— translating data questions into answers that matter to a business
-Data Visualisation — creating charts and graphs that communicate insights clearly
-Power BI Dashboarding— building interactive, professional reports
-GitHub & Version Control— organising and documenting work in a professional repository
-Technical Writing— documenting methodology, findings, and conclusions
