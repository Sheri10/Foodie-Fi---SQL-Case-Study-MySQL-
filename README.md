# Foodie-Fi---SQL-Case-Study-MySQL-
A SQL analysis of a subscription streaming service: customer journeys, churn, conversion from the free trial, and a payments table built from the subscription history. This is Case Study #3 of Danny Ma's 8 Week SQL Challenge, solved in MySQL 8.0.
Business problem

Foodie-Fi is a streaming service with cooking content. New customers start with a 7-day free trial, and then continue to a basic or pro plan, or cancel. The company wants to understand how customers move between plans, how many churn, and how much they pay.

Dataset

Two tables in the foodie_fi database:

Table	Columns	Description
plans	plan_id, plan_name, price	The five plans: trial, basic monthly, pro monthly, pro annual and churn
subscriptions	customer_id, plan_id, start_date	The date each customer's plan starts (2,650 rows, 1,000 customers)
What I did
A. Customer journey: a short description of the onboarding journey of 8 sample customers.
B. Data analysis: customer counts, monthly trial sign-ups, plan events after 2020, churn counts and percentages, the plan customers choose after the trial, the plan breakdown at a given date, upgrades to annual plans, days to upgrade (in 30-day periods) and downgrades.
C. Challenge: a payments table for 2020 with the amount of every payment, following the billing rules (monthly payment on the same day of the month, upgrade discounts, no payments after churn).
D. Outside the box: written answers on growth rate (calculated with LAG and a moving average), key metrics, customer journeys to analyse, an exit survey and ways to reduce churn.
Some findings
Foodie-Fi has had 1,000 customers, and 307 of them (30.7%) have churned.
92 customers (9%) cancel right after the free trial.
After the trial, most customers choose basic monthly (54.6%), then pro monthly (32.5%), pro annual (3.7%) and churn (9.2%).
SQL skills

Joins, CTEs, window functions (LAG, LEAD, ROW_NUMBER, moving averages), conditional aggregation with CASE, percentage calculations, date functions (DATE_ADD, DATEDIFF), CROSS JOIN with a month list to create rows, and CREATE TABLE / INSERT ... SELECT.

Files
File	Purpose
00_init_foodie_fi_mysql.sql	Creates the foodie_fi database and the two tables, and loads the data with INSERT statements
foodie_fi_queries.sql	The queries and written answers for sections A to D
How to run
Open MySQL Workbench and connect to a local MySQL 8.0+ instance.
Run 00_init_foodie_fi_mysql.sql. It drops and recreates the foodie_fi database, so don't run it where a database with that name matters.
Run the queries in foodie_fi_queries.sql. If you re-run the init script, run the payments queries again, because the table is removed with the database.
Credits

Case study and dataset by Danny Ma as part of the 8 Week SQL Challenge. Queries written by me as part of a personal SQL learning project.
