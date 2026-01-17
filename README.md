# Retail BI Dashboard — Excel + Power BI (University Project)

This repository showcases a Business Intelligence project developed for the course *Computer Lab for Business Decisions* (Università Cattolica del Sacro Cuore, A.Y. 2023–2024). 
Using Excel for preprocessing and Power BI for modeling, DAX measures, and visualization, the goal was to build a relational model and a multi-page interactive report to analyze sales, customers, products, inventory, and POS outages. 

## Business case & dataset

The provided dataset represents the management of multiple retail stores and includes tables for customers, geography, products (category/subcategory), promotions, sales, inventory snapshots (weekly per store), POS devices (machines), outage types, outage events, and stores. 

Project constraints included focusing on stores with Key 1–10, cleaning store names by removing “contoso” and “store”, and using the 2008–2009 time period as the reference window.

## Tools & workflow
![Table_Relationships](images\relationship.png)

- **Excel**
  - Initial inspection and data preparation (standardizing fields, applying required filters, validating data ranges, and cleaning store naming conventions).
- **Power BI Desktop**
  - Data model creation by relating all tables into an analysis-ready schema. 
  - DAX measures for KPIs (revenue, margin, YoY comparisons), customer segmentation, outage durations, and product banding.
  - Report design with consistent Year/Month slicers available across pages, plus additional contextual filters (e.g., promotions where relevant). 

## Report structure (pages)

The Power BI report is organized into the following analysis areas required by the assignment. 

### Sales analysis
Sales KPIs include total revenue and total margin for the selected period and the equivalent period in the previous year, with absolute and percentage deltas. 
The report supports breakdowns by store, product category, and customer geography, and it allows filtering by promotion periods.  

### Customer analysis
Customers are analyzed by geography with drill-down (Continent → Country/State → Region), income range, gender, and number of children.   
A dedicated attribute distinguishes “person” vs “company” customers to enable page-level filtering, while two measures display overall totals independently from that filter.   

### Outage time analysis (hour & weekday)
Outage duration is computed in minutes, then the number of outage reports is analyzed across hours of the day, with the ability to drill into store-level detail.  
A second visual analyzes outages by weekday from Monday to Sunday. 

### POS outage analysis
A “header/detail” layout presents store-level metrics (employees, number of POS devices, POS downtime) and a related POS-level detail table (machine name and downtime). 
A chart breaks down downtime by outage type to highlight the most impactful causes.  

### Product analysis (ABCD margin bands)
Products are segmented into A/B/C/D bands based on contribution to total margin: 50% / 30% / 15% / 5%. 
The report includes revenue comparison by band and a breakdown of product counts by band across manufacturers.  

### Inventory analysis
Inventory is analyzed by year and month for all stores, with the option to filter a single store; monthly/yearly aggregation uses the value at the latest available date in that period.  
A trend visual compares inventory (“stock”) against sales over time.   


## How to open the report

1. Go, to report folder, then open the `.pbix` file in Power BI Desktop.  
2. If needed, update data source paths to point to the dataset location (use "data.xlsx").  
3. Refresh the model and use the Year/Month slicers (available across pages) to explore all analyses. 

## Notes

This project is intended as a portfolio piece to demonstrate end-to-end BI work: data preparation in Excel, relational modeling, DAX-based KPIs, and interactive report design in Power BI.
