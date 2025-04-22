# Power-BI-Interview-Prep
This repository balances theory, hands-on practice, and troubleshooting, making it ideal for interview prep or hiring assessments. Adjust difficulty based on the role (Analyst, Developer, Architect).

## 1. Foundational Concepts
Basic Questions
What is Power BI, and what are its core components (Desktop, Service, Gateway, Mobile)?

Explain the difference between Import Mode, DirectQuery, and Dual Mode.

What is a Power BI Dataset, and how does it differ from a Dataflow?

How do you share a report with external stakeholders securely?

Intermediate Questions
What is DAX? Provide examples of common functions (e.g., CALCULATE, FILTER).

How do row-level security (RLS) and object-level security (OLS) work in Power BI?

What is the role of Power Query in data transformation?

Advanced Questions
Explain bidirectional cross-filtering and when it should be avoided.

How do you optimize a slow-performing Power BI report?

#2. Technical Skills & DAX
Scenario-Based DAX Questions
Scenario: A sales manager wants YoY growth by product category. Write the DAX formula.

Answer:

DAX
YoY Growth = 
VAR CurrentSales = SUM(Sales[Amount])
VAR PreviousSales = CALCULATE(SUM(Sales[Amount]), SAMEPERIODLASTYEAR(DateTable[Date]))
RETURN DIVIDE(CurrentSales - PreviousSales, PreviousSales)  
Scenario: Calculate a rolling 3-month average for sales.

Answer:

DAX
Rolling Avg = 
AVERAGEX(DATESINPERIOD(DateTable[Date], LASTDATE(DateTable[Date]), -3, MONTH), [Total Sales])  
Debugging Questions
Why might a Many-to-Many relationship cause incorrect totals, and how would you resolve it?

A measure returns blanks unexpectedly. What are the potential causes?

3. Data Modeling & Transformation
Scenario: Data Modeling
Task: Design a star schema for a retail sales dataset with tables for Sales, Products, Dates, and Stores.

Evaluation Criteria: Proper use of fact/dim tables, relationships, and avoiding circular dependencies.

Scenario: A column has values like "1,000" stored as text. How would you convert it to a number in Power Query?

Answer: Use Replace Values to remove commas, then change the data type.

Advanced Transformation
How do you handle slow-changing dimensions (Type 1/Type 2) in Power Query?

Write M code to merge quarterly Excel files from a folder dynamically.

4. Visualization & Reporting
Design Scenarios
Scenario: The CEO wants a dashboard showing real-time sales vs. targets. Which visuals and features would you use?

Answer: Line/bar charts, conditional formatting, alerts, and a DirectQuery connection.

How would you design a mobile-optimized report for field teams?

Troubleshooting
A visual displays incorrect data. How do you validate if the issue is in the data model, DAX, or the visual itself?

5. Performance Optimization
Scenario: Slow Report
Task: A report with 10M rows loads slowly. Identify bottlenecks and solutions.

Possible Fixes:

Use aggregations.

Switch from Import to DirectQuery.

Optimize DAX (avoid SELECTEDVALUE, use variables).

How does query folding improve performance, and how do you ensure it works?

6. Administration & Collaboration
How do you deploy reports across Dev, UAT, and Prod workspaces using pipelines?

Explain the process of scheduling dataset refreshes with an on-premises SQL Server.

7. Advanced Scenarios
Scenario: End-to-End Project
Task: Build a report from scratch using data from an API (e.g., Salesforce).

Steps:

Connect to the API via Power Query.

Clean/transform data (e.g., handle nested JSON).

Model data with appropriate relationships.

Create measures for KPIs.

Publish to Service, configure refresh, and set RLS.

Scenario: Data Discrepancy
Stakeholders report mismatched totals between Excel and Power BI. How do you diagnose?

Approach: Check filters, data types, and aggregation rules in both tools.

8. Behavioral & Best Practices
How do you ensure data governance in a shared Power BI environment?

Describe a time you resolved a conflict with a stakeholder over report design.
