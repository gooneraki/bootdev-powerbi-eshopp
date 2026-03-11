# Eshopp Power BI Data Visualization Project

This repository contains my completed project from the Boot.dev course:

Course: https://www.boot.dev/courses/learn-data-visualization-power-bi

The project simulates a business intelligence workflow for a fictional e-commerce company, Eshopp. Raw CSV data is transformed into an interactive, multi-page Power BI report designed for executive decision-making.

## Project Overview

This project demonstrates end-to-end BI development:

- Importing and cleaning raw CSV data
- Building a star schema data model
- Creating DAX measures for KPIs and analysis
- Designing interactive dashboard pages
- Applying report formatting and storytelling best practices

The report includes KPI tracking, revenue trends, session analytics, product and store performance, and geographic drilldowns.

## Tools and Technologies

- Power BI Desktop
- Power Query (ETL)
- DAX (Data Analysis Expressions)
- Star schema data modeling
- CSV data sources

## Key Concepts Applied

### Data Preparation

- Removed duplicates
- Split and merged columns
- Handled null values
- Corrected data types
- Improved transformation performance

### Data Modeling

- Designed fact and dimension tables in a star schema
- Configured one-to-many relationships
- Managed filter direction behavior

### DAX

- Differentiated calculated columns vs measures
- Built aggregate measures (`SUM`, `AVERAGE`)
- Used iterator functions (`SUMX`, `AVERAGEX`)
- Applied context-aware logic with `CALCULATE`
- Practiced row context vs filter context

### Visualization

- Built bar, column, line, area, scatter, ribbon, and waterfall charts
- Used gauges, cards, and donut visuals
- Added conditional formatting and drilldowns
- Configured page/report/visual filters and slicers

## Dashboard Highlights

The final executive dashboard includes:

- Total revenue (discount-adjusted)
- Total units sold
- Revenue trend by product category
- Session duration by store
- Sales by brand
- Population drilldown (Country -> State -> City)
- Date and region slicers

## Representative DAX Measures

The semantic model includes measures such as:

```dax
total_revenue = SUM(sales[discounted_price])
total_units_sold = SUM(sales[sale_quantity])
discounted_revenue = SUMX(sales, sales[sale_quantity] * sales[discounted_price])
session_quality_score_avg_scaled = INT(AVERAGEX(website_sessions, 100 * website_sessions[session_quality_score]))
```

## How to Open the Project

1. Install Power BI Desktop.
2. Clone or download this repository.
3. Open `eshopp.pbip` in Power BI Desktop.
4. If prompted, confirm data source paths for the CSV files in the repository root.
5. Refresh the model and explore the report pages.

## Repository Structure

- `eshopp.pbip`: Power BI project file
- `eshopp.Report/`: Report definitions (pages, visuals, themes)
- `eshopp.SemanticModel/`: Semantic model, tables, relationships, and DAX queries
- `customers.csv`, `dates.csv`, `geographies.csv`, `products.csv`, `sales.csv`, `stores.csv`, `website_sessions.csv`: Source datasets

## What I Learned

- Translating business questions into actionable dashboard metrics
- Building reliable DAX measures with correct context behavior
- Structuring maintainable and performant BI models
- Presenting insights clearly for non-technical stakeholders

## Future Improvements

- Publish to Power BI Service
- Simulate scheduled refresh workflows
- Add period-over-period KPI views (MoM, YoY)
- Add drill-through analysis pages

## License

This project is for educational purposes as part of the Boot.dev curriculum.