# 🛶 Illegal Immigration Trends: Analyzing UK Small Boat Crossings 
This project explores trends in illegal immigration to the UK via small boats, using datasets from [Migration Watch UK](https://www.migrationwatchuk.org/channel-crossings-tracker). The analysis leverages advanced data cleaning, transformation, and visualization techniques to uncover key insights into immigration patterns and government interventions.

## 🎯 Objective
To analyze and visualize data on illegal immigrants entering the UK by small boats from 2018-2024, focusing on trends over time, nationalities involved, and the impact of government measures.

## 📊 Project Steps

### 📂 Data Acquisition
- Collected five Excel CSV files:
  - Immigrants detected per month (2018–2024)
  - Nationalities of immigrants
  - Returned immigrants
  - Channel crossings after government acts
  - Small boats used per month
- Consolidated the datasets into a single Excel workbook, with each data range in a separate worksheet.

### 🧹 Data Cleaning and Preparation
- Converted data ranges into tables in Excel for better organization.
- Removed unnecessary rows and columns to focus on relevant data.
- Standardized column datatypes for consistency.
- Transformed data using **Power Query**:
  - **Unpivoted columns**: The original data format had years as column headers and nationalities or months as rows, forming a matrix structure. While this format is suitable for viewing raw data, it is not ideal for scalable analysis or visualization. So I Unpivoted columns of all tables to restructure matrices into long-format tables.
  -  Renamed columns for clarity.
  - In the "Immigrants by Month and Year" table:
    - Added a `Month Number` column using the formula:  
      `=MONTH(DATEVALUE([@Month] & " 1"))`
    - Created a `Quarter` column using:  
      `="Q" & ROUNDUP([@Month Number] / 3, 0)`
    - Copied the values from the `Quarter` column and pasted them as values in the same column.
    - Deleted the `Month Number` column after the values were finalized.

### 📈 Data Visualization in Tableau
- Loaded each table into Tableau as a separate data source to avoid inter-table relationships.
- Created five key visualizations:
  1. **Stacked Column Chart**: Number of immigrants by year and quarter.
     ![image](https://github.com/user-attachments/assets/daeef033-38cd-47a4-808b-bc2dc67938f1)
     
      - The chart shows a significant rise in illegal immigrants from 2018, peaking in 2022 with over 45,000 migrants.
      - Q3 consistently contributed the most migrants each year. After 2022, numbers declined in 2023 and 2024, stabilizing around 30,000–35,000.
      - The sharp increase between 2020 and 2021 marks a notable surge in migration activity
     
  2. **Pie Chart**: Top 7 nationalities entering the UK via small boats (2018-2024), with an interactive year filter.
 
     ![image](https://github.com/user-attachments/assets/13e3cdac-a504-4408-9bb3-540af28d0880)
     ![image](https://github.com/user-attachments/assets/3c3dc521-cd5c-459c-a07e-f2e8d9cde31b) 
      

       - Iran leads with 20,601 migrants, followed by Afghanistan (15,934) and Iraq (14,884).
       -  Other notable groups include Albania (14,419), Syria (8,025), Eritrea (7,803), and Sudan (5,247).
       -  The interactive year filter highlights trends over time. 

  3. **Bubble Chart**: Types of returns (enforced or voluntary) and their counts (2019–2024).
     
     ![image](https://github.com/user-attachments/assets/20ab9215-0982-412a-8f97-7b8bf962a972)

      ![image](https://github.com/user-attachments/assets/797a0e26-0f68-4dbe-9e5a-60e519ca6e46)

     - Voluntary returns (orange) consistently outnumber enforced returns (blue), peaking at 10,598 in 2022.
     -  Enforced returns peaked in 2019 (5,297) but declined afterward. Both categories dropped significantly by 2023.

  4. **Stacked Bar Chart**: Number of boats used per month for channel crossings (2018–2024).

     ![image](https://github.com/user-attachments/assets/60d5d26d-0e53-4d24-b603-2e49dae096a0)

     - Boat crossings to the UK have dramatically increased since 2018, especially in 2022.
     - Summer months see more crossings.

  5. **Bar Chart**: Crossings made since the government pledged to stop small boats.

     ![image](https://github.com/user-attachments/assets/9a961e41-a4c4-4891-909b-4c562e6c7227)

     - Pledges to "stop the boats" have not been effective. Crossings continue despite government efforts.
     - No single policy has significantly reduced crossings.
     - The issue remains a significant challenge for the UK government.

- Combined these visuals into an interactive **dashboard** for better insights.

  ![image](https://github.com/user-attachments/assets/2bdc111a-3c69-4548-b006-eb4367cecb33)


## 🛠️ Tools and Technologies
- **Excel**: Data cleaning and initial transformations.
- **Power Query**: Data unpivoting and preparation.
- **Tableau**: Visualization and dashboard creation.

## 📁 Repository Contents
- Excel workbook containing cleaned and transformed data tables.
- Tableau workbook with visuals and dashboards.
- A detailed report summarizing insights from the analysis.

## 📥 How to View the Project
1. Download the Tableau Public file from this repository.
2. Open the file in Tableau Public to explore the interactive dashboard.
