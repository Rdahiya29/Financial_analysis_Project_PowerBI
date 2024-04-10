
# Profit and Loss Statement Dashboard

## Problem Statement

This dashboard helps Turtle Co. analyze the company’s profitability. Over the timespan of 2 years ,it provides details on the revenue a company earns 
and the expenses involved in its operating activities. Overall, it provides more granular detail on the holistic operating activities of a company. Broadly, the income statement
shows the direct, indirect, and capital expenses a company incurs.


### ETL with Power Query

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so I select "column profiling based on entire dataset".
- Step 4 : Unpivoted the Dr and Cr Column of Journal Table  for further analysis and named the column as "Type" and "Account".
- Step 5 : Custom Column "TB Amount" is created , to negate the values where Type = "Dr" and Positive where Type = "Cr"
- Step 6 : Since we want to create a slicer for Division so new table from Division column(of Journal table) named "Division" is creadted by refrencing Journal table  
- Step 7 : Since the dataset doesn't have the Calendar table so new Calendar table is created using M Code and Year, Month, Month name column is created


### Date Modelling

- Step 1:  Star Schema is Created by joining Journal (the fact table) with COA , Division, Calendar table (The lookup table)
- Step 2 : The Cardinality formed between the lookup table and the fact table is One-to-many 


Further Measures are created to prepare the P and L statement

Here is the snapshot of the Dashboard 

![P L statement](https://github.com/Rdahiya29/Financial_analysis_Project_PowerBI/assets/165986652/f66bddd6-933c-4399-a91a-7c81a9d38dbf)
