# 🏫 Victoria Schools Dashboard (PySpark + Power BI)

This project demonstrates how to transform raw school data using **PySpark in Google Colab** and then build an **interactive Power BI dashboard** for insights.

---

## Project Workflow

1. **Data Source**
   - Dataset: `dv402-SchoolLocations2025.csv`
   - 2,300+ rows, 24 columns
   - Attributes include: `School_Name`, `School_Type`, `Education_Sector`, `Region`, `LGA_Name`, geographic coordinates (`X`, `Y`).

2. **Data Wrangling with PySpark**
   - Loaded the dataset in **Google Colab** using PySpark.
   - Performed:
     - Duplicate removal
     - Null checks
     - Type casting
     - Aggregations by School Type, Sector, and Region
   - Exported a cleaned dataset (`schools_clean_final.csv`) to Google Drive.

3. **Dashboard with Power BI**
   - Connected cleaned CSV to Power BI.
   - Created DAX measures:
     ```DAX
     Total Schools = COUNTROWS(schools_clean_final)
     Unique Schools = DISTINCTCOUNT(schools_clean_final[School_No])
     Primary Schools = CALCULATE(COUNTROWS(schools_clean_final), schools_clean_final[School_Type] = "Primary")
     Secondary Schools = CALCULATE(COUNTROWS(schools_clean_final), schools_clean_final[School_Type] = "Secondary")
     ```
   - Built visuals:
     - KPI Card → **Total Schools**
     - Bar Chart → Schools by Region & Type
     - Bar Chart → Schools by School Type
     - Pie Chart → Schools by Education Sector
     - Table → School details (Name, Type, Sector, Region, LGA)
     - Map → Schools plotted geographically

---

## 📊 Key Insights
- **Total Schools:** 2,162
- **By Type:**
  - Primary: 1,491
  - Secondary: 360
  - Pri/Sec: 250
  - Special: 117
  - Language: 5
- **By Sector:**
  - Majority are **Government** schools
  - Catholic and Independent sectors represent smaller shares

---

## 🛠 Tools & Technologies
- **PySpark (Google Colab)** → Data wrangling
- **Google Drive** → Data storage
- **Power BI Desktop** → Dashboard & visualization
- **DAX** → Measures for KPIs

---

## Dashboard Preview
<img width="1308" height="730" alt="image" src="https://github.com/user-attachments/assets/3fdba0ae-0712-4351-a549-497fd243d8bd" />


---


