# 🛒 Sales Forecasting & Food Waste Reduction

📌 Project Overview

Food retailers face a critical challenge: balancing product availability with minimizing food waste.
Overstocking leads to waste and financial loss, while understocking results in lost sales and poor customer experience.

This project applies time-series forecasting and data-driven inventory planning to:

Forecast daily grocery demand

Estimate food waste caused by overstocking

Evaluate how forecasting can reduce waste and cost

🎯 Business Problem

The grocery store currently relies on manual or heuristic-based inventory planning that does not fully account for:

Demand variability

Weekly seasonality

Product-level differences

As a result, perishable items are frequently overstocked, leading to unnecessary food waste.

🎯 Objectives

Analyze historical grocery sales data to understand demand patterns

Forecast daily demand using Facebook Prophet

Design a realistic food waste estimation framework

Compare waste levels before vs after forecast-based planning

Provide actionable business recommendations

📊 Dataset

Source: Kaggle – Supermarket Sales Dataset
Granularity: Transaction-level grocery sales
Time Period: January – March 2019

Key Columns

date

product_line

quantity

unit_price

sales

branch

customer_type

⚠️ Note: The dataset does not directly include food waste. Waste is estimated using demand-based assumptions, similar to real-world retail operations.

🧹 Data Cleaning

Standardized column names

Converted date and time fields to proper datetime formats

Removed duplicate invoices

Validated numeric fields (quantity, price, sales)

Aggregated transaction data into daily product-level demand

🔍 Exploratory Data Analysis (EDA)

Key insights from EDA:

Sales show strong daily and weekly patterns

Weekend demand is consistently higher than weekdays

Demand varies significantly across product lines

Some products exhibit high demand volatility, increasing waste risk

A small subset of product lines contributes to a large portion of sales and waste

🔮 Demand Forecasting

Implemented Facebook Prophet for daily demand forecasting

Modeled demand at the product-line level

Captured weekly seasonality

Forecasted short-term demand (14 days)

Evaluated forecast accuracy using MAE and MAPE

Prophet was selected for its interpretability and suitability for business forecasting.

🗑️ Food Waste Estimation Logic

Since waste data was not available, a realistic estimation approach was used.

Assumptions

Inventory is stocked based on forecasted demand + safety stock

Safety stock is set to 15%

Waste occurs when stocked quantity exceeds actual sales

Food cost is assumed to be 60% of selling price

Waste Formula
Stocked Quantity = Forecasted Demand × (1 + Safety Stock)
Waste = max(Stocked Quantity − Actual Sales, 0)

📉 Waste Reduction Evaluation

Two scenarios were compared:

Baseline planning (rolling average / fixed buffer)

Prophet-based forecasting

Result

Forecast-based planning significantly reduces estimated food waste

Waste reduction is especially strong for high-variability product lines

Improved balance between availability and sustainability

📌 Key Business Insights

Forecast-driven inventory planning can reduce food waste without increasing stockouts

High-variability products should have lower safety buffers

Inventory strategies should be product-specific, not uniform

Data-driven planning supports both cost savings and sustainability goals

✅ Actionable Recommendations

Adopt demand forecasting models for daily inventory planning

Reduce safety stock for low-variability products

Monitor high-waste product lines and adjust production quantities

Implement dynamic pricing or promotions for slow-moving items

Continuously retrain models as new sales data becomes available

🛠️ Tools & Technologies

Python (Pandas, NumPy)

Matplotlib & Seaborn

🚀 Future Improvements

Add holiday and promotion features

Forecast at store/branch level

Extend to multi-item or hierarchical forecasting

Integrate real waste tracking data if available

Deploy model as a simple inventory decision-support tool

👤 Author

Amaya Gunawardhana
Aspiring Data Scientist | Data Analytics & Forecasting
📍 Sri Lanka

Facebook Prophet

Jupyter Notebook
