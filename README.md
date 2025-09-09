# Building Sales Data Mart using SSIS

This is my **first SSIS project**, where I designed and built an **ETL pipeline** to create a **Sales Data Mart** from the **AdventureWorks2022** database.

---

## 📌 Project Overview

The goal of this project is to practice building a small-scale **Data Warehouse / Data Mart** using **SQL Server Integration Services (SSIS)**.  
The ETL process extracts data from the **AdventureWorks2022** OLTP database, transforms it, and loads it into a dimensional model with fact and dimension tables.

---

## 📦 ETL Packages

- **Dimensions**
  - `dim_customer ETL.dtsx`
  - `dim_product ETL.dtsx`
  - `dim_territory.dtsx`
  - `dim_date.dtsx`
- **Facts**
  - `fact sales Full load.dtsx`
  - `fact sales inc load.dtsx`

Connection managers:

- `Source DB.conmgr` → AdventureWorks2022 (OLTP)
- `Destination DB.conmgr` → EO_AdventureWorksDW2022 (DW)

---

## 🗄 SQL Queries

All SQL scripts and the reference Excel file are available inside the [`SQL queries/`](SQL%20queries/) folder:

- `01_create_database.sql` → Creates the Data Mart database.
- `02_dim_product.sql` → Creates DimProduct.
- `03_dim_customer.sql` → Creates DimCustomer.
- `04_dim_territory.sql` → Creates DimTerritory.
- `05_dim_date.sql` → Creates DimDate.
- `06_fact_sales.sql` → Creates FactSales.
- `81_metadata_control_table_and_audit_table.sql` → Metadata & audit tables for ETL control.
- `403_dim_customer_test_scd_setup.sql` → Test setup for SCD in DimCustomer.
- `404_dim_product_test_scd_setup.sql` → Test setup for SCD in DimProduct.
- `102_dim_date_01_populate_table.xlsm` → Excel mapping for DimDate population.

---

## 🖼 Screenshots

Screenshots of the project are available in the [`assets/`](assets/) folder:

- Control Flow – Fact_Sales (Incremental Load)
- Data Flow – Dim_Customer
- Data Flow – Fact_Sales (Incremental Load)
- Solution Explorer view

---

## 🛠 Tools & Technologies

- **SQL Server Integration Services (SSIS)** in Visual Studio
- **SQL Server** (source + destination databases)
- **AdventureWorks2022** sample database
- **GitHub** for version control and sharing

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/3mrZain7agag/Building-sales-Data-Mart-using-SSIS.git
   ```
2. Restore the **AdventureWorks2022** sample database (download from [here](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)).
3. Open the SSIS solution in **Visual Studio**.
4. Configure connection managers (`Source DB` and `Destination DB`) to point to your SQL Server instance.
5. Run the ETL packages to populate dimensions and facts.

---

## 🙏 Acknowledgments

This project was inspired and guided by a [YouTube playlist](https://youtube.com/playlist?list=PLcAbhg_RWLaLUaYpAAvOLu2hlyVgZlRjb&si=NH3UpgD0JfNGmWwP).  
Most of the SQL scripts were adapted from the tutorial, but I modified them to work with **AdventureWorks2022** instead of AdventureWorks2014 (including datatype adjustments and schema updates).

---

## 📜 License

This repository is for **educational purposes only**.  
Feel free to use or adapt, but please give credit if you reference it.
