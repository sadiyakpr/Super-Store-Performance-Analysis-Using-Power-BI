# Super-Store-Performance-Analysis-Using-Power-BI

 What new have I implemented

🌟Multi-page dashboard | 🌟Subtle colors visuals | 🌟Column quality | 🌟Replace errors | 🌟Company logo | 🌟Buttons | 🌟Page navigator | 🌟Back button | 🌟Legends field for multiple line graphs | 🌟New column using DATEDIFF function | 🌟Outlier detection | 🌟New measure using AVERAGE and MEDIAN functions | 🌟Forecasting | 🌟Upper and Lower bound | 🌟Zoom slider  | 🌟Tooltips.

# A quick glimpse of the multi-page report

Page 1:

![Screenshot 2024-10-12 234052](https://github.com/user-attachments/assets/adc5b5b8-43ee-46c0-94ed-3e45e5683e56)

Page 2:

![Screenshot 2024-10-12 234703](https://github.com/user-attachments/assets/922ef7cf-8d8e-4b9f-9866-9cc1558fff71)

### Dashboard PDF : [powerBIProject4.pdf](https://github.com/user-attachments/files/17351283/powerBIProject4.pdf)

## Problem Statement

This dashboard provides insights into the store's performance over two years. It enables the company to track total profit, revenue, profit margin, states it serves, and more.
Using the dashboard, the store is accessed and areas for improvement are identified. This will enable us to sustain our performance levels while driving improvement in areas where we currently face challenges.
### Steps followed 

- Step 1: Load data into Power BI Desktop, dataset is an Excel file.

  The following are the labels in the original dataset before transformation and loading,

     - Category
     - City
     - Country
     - Customer ID
     - Customer Name
     - Order Date
     - Payment Mode
     - Product ID
     - Product Name
     - Profit
     - Quantity
     - Region
     - Returns
     - Row ID
     - Sales
     - Segment
     - Ship Date
     - Ship Mode
     - State
     - Sub-category
     - ind1
     - ind2
  
- Step 2: Transformations

  Open the Power Query Editor to make the necessary transformations to the dataset. To achieve this select the Transform data option under the Home tab.
- Step 3: Remove duplicates

  To remove all the duplicates from the table, select the table by clicking anywhere in the dataset and clicking ctrl + A, under the Home tab click remove rows and select the Remove duplicates option.
- Step 4: Understand values in columns

  ![Screenshot 2024-10-13 010338](https://github.com/user-attachments/assets/4c9faea2-3d52-4216-b156-69ababb4681e)

  To understand values in each column, under the view tab tick Column quality this will show the percent of correct, error, and empty cells in each column.
- Step 5: Handle any inappropriate values

  It was observed that two columns "ind1" and "ind2" had all their values as null.
      - These columns were removed by simple selection of the columns and selecting "remove columns" by clicking "remove columns" option under the view tab.
  One column "return" consisted of error values.
      - These error values were set to "N/A" indicating information being not available. These column values were replaced by 0.
- Step 6: Distinct values in columns

  Next, to view all distinct values in each column, click the down arrow icon next to each column label this will scroll down a list of all the distinct values in a column.

- Step 7: Add necessary columns

  The "DaysTaken" column was added using the new column option under the Table Tools tab, this option allows the addition of a new column to the dataset.

   - The DAX query used for the column is,

         DaysTaken = DATEDIFF(Sheet1[Order Date], Sheet1[Ship Date], DAY)

  Then, modify the default column names to more convenient and concise labels.
     
- Step 8: Click the "Close & Apply" option at the window's top-right corner once all transformations are completed. Power BI does not make changes to the original raw dataset.

  This will open the Power BI Report view section, where visualizations are created for all the tasks and goals of the performance analysis report.
  
- Step 9: Give a one-line summary on the top of the canvas using a text box. The report summary is "Super Store Performance Analysis."

  Additionally, a sub-title could be added, to the report, it is "2019-2020."

- Step 10: Add the company logo.

  Under the insert tab in the elements section select the icon option.

  This allows you to choose your desired image file.

  Snap of company logo,

  ![Screenshot 2024-10-12 221953](https://github.com/user-attachments/assets/b3df4b32-8695-4382-aea1-7da134030170)

  This is just a dummy logo for the sake of the project and getting familiar with the facilities on Power BI.
- Step 11: Produce KPIs (Key Performance Indicators) for the following factors
  - Total profit store makes
  - Total revenue store makes
  - Total profit margin store makes

  The "New measure" option was used to create this KPI. Under the Home tab in the calculate section select the "New measure" option this will open the DAX query tab.

  The following DAX query was used,

      Profit Margin = sum(Sheet1[Profit])/sum(Sheet1[Sales])
  
  This was formatted to percentage.

  The "new measure" option is quicker than the "new column" option. It does not create a new column in the dataset. 

  Snap of the profit margin KPI,

  ![Screenshot 2024-10-12 213452](https://github.com/user-attachments/assets/7f5a2b0a-1263-47d5-b88d-6f98ab8b5228)

  - Total states serving

  - Average days for delivery

  To calculate the average for any numerical column, it is important to understand the distribution of its values.

  The distribution ranges from 0 to 8.

  The column values follow a normal distribution. This inference was made by calculating the average and median for the column using new measure DAX queries.

  Calculating the Average of "DaysTaken,"

      Average of Days Taken = AVERAGE(Sheet1[DaysTaken])

  Calculating the Median of "DaysTaken,"

      Median of Days Taken = MEDIAN(Sheet1[DaysTaken])

  ![Screenshot 2024-10-12 215352](https://github.com/user-attachments/assets/606b2a29-e790-406b-9a88-12ea57f935d1)

  Since the values are approximately equal the average represents the days to deliver a product.

  Snap of the average days to deliver KPI,

  ![Screenshot 2024-10-12 220840](https://github.com/user-attachments/assets/482e34e4-18d0-4c7f-97b8-221140d8a618)


- Step 11: Add a line chart to observe monthly trends in revenue and profit.
 
    Snap of monthly trends in revenue,

    ![Screenshot 2024-10-12 223610](https://github.com/user-attachments/assets/f4252c74-2165-4954-a221-65818b6e030d)

    Snap of monthly trends in profit,

    ![Screenshot 2024-10-12 223635](https://github.com/user-attachments/assets/c1b50dc5-7300-4555-8bbd-fb50603b63ff)

    To get multiple lines on a single chart based on year, a legend field is used. It represents the data on a chart based on categories, in this case, 2019 and 2020 are the categories.

- Step 11: Three Horizontal bar charts were added for the following,
  - Revenue by category
  - Revenue by sub-category
  - Revenue by ship-mode
 
    Snap for a horizontal chart used on the dashboard, revenue by category is below,

    ![Screenshot 2024-10-12 232621](https://github.com/user-attachments/assets/8066882e-b51b-41c8-bbc5-1bceedc64a8a)

 
- Step 12: Two doughnut charts were added for the following,
  - Revenue by payment mode
  - Revenue by segment
 
    Snap for a doughnut chart used on the dashboard, revenue by payment mode is below,

    ![Screenshot 2024-10-12 232741](https://github.com/user-attachments/assets/7e02bb10-7a2e-4830-b150-8b212dcd66e3)

    Label content for the doughnut chart was set to "category, percent of total".

  
- Step 13: Visual filter (Slicer) were added for regions.

- Step 14: Three buttons are used for the following,
  - A navigation bar to navigate to different pages of the report
  - A clear all slicer button to clear all slicers applied to the report
  - A  left arrow to go to the previous page of the report
 
    Snap for one of these buttons, the navigation bar,

    ![Screenshot 2024-10-12 235221](https://github.com/user-attachments/assets/0c63956d-d90c-4dbe-a682-8c538fbf17c8)

    These buttons are followed using ctrl + click.

- Step 15: A real-time geographical map added, represents the top 5 states generating maximum revenue.

- Step 16: Create a new page for the report.
  
  At the down-left of the window search for a + sign, it should be aligned to the page name you are currently on.

- Step 17: Create a forecast for revenue and profit of the store.

  On the visualization pane on the right side click the Analytics icon this will display analytics options and turn on the forecast.

  Set units as days and forecast as 15. This will produce a forecast for the next 15 days.

- Step 18: Add a zoom slider to the charts. 

  Click the Format Visuals option and turn on the Zoom slider.

  This will allow zooming a time period on the chart.

  Snap of the forecast charts,

  ![Screenshot 2024-10-12 232021](https://github.com/user-attachments/assets/d9b40c4b-2223-4723-9022-fe9faf04600f)

  The forecasting shows the forecast for the day, and possible range of value using the upper and lower bound.

  When hovered on the forecast tooltips is displayed with the information.

  Tooltips are messages that appear when hovering over any visual with additional information related to the visual.

  When turned off this information is not displayed. 
  
- Step 19: The report was then published to Power BI Service.

![Screenshot 2024-10-12 233318](https://github.com/user-attachments/assets/63f468f6-6c99-4fc1-b3b8-ff9e5edcb326)

# Snapshot of Dashboard (Power BI Service)

![Screenshot 2024-10-12 233636](https://github.com/user-attachments/assets/a11e9b34-28b9-4f34-a50d-f7276cd8ae5f)

![Screenshot 2024-10-12 233711](https://github.com/user-attachments/assets/6b1e86d5-52dc-43ab-a7b2-21a734365f7d)

# Insights

A single-page report was created on Power BI Desktop & it was then published to Power BI Service.

The following inferences can be drawn from the dashboard,

### [1] Total store profit

    175K Dollars.
    
### [2] Total store revenue 

    1,566K Dollars.

### [3] Profit Margin

    11.2%.    
    
### [4] Total states serving

    49.

### [4] Average days for delivery

    4 Days.   

### [4] Revenue by category

    Rank 1: Office supplies
   
    Rank 2: Technology
   
    Rank 3: Furniture

  Ranking based on share in revenue. These ratings will change if different visual filters are applied.
    
### [4] Revenue by sub-category

    Rank 1: Phones
   
    Rank 2: Chairs
   
    Rank 3: Binders

  Ranking based on share in revenue. These ratings will change if different visual filters are applied.

 ### [4] Revenue by ship mode

    Rank 1: Standard Class
   
    Rank 2: Secondary Class
   
    Rank 3: First Class 

    Rank 4: Same Day

  Ranking based on share in revenue. These ratings will change if different visual filters are applied.   
    
### [2] Top 5 states by revenue

     Rank 1: California
   
    Rank 2: New York
   
    Rank 3: Washington
   
    Rank 4: Michigan

    Rank 5: Indiana

   Ranking based on share in revenue. These ratings will change if different visual filters are applied.
           
### [3] Revenue by payment mode

    Rank 1: COD (Cash On Delivery) (42.61%)
   
    Rank 2: Online (35.39%)
   
    Rank 3: Card (22%)

 Ranking based on share in revenue. These ratings will change if different visual filters are applied.
  
  ### [4] Revenue by segment
  
    Rank 1: Consumers (48.08%)

    Rank 2: Corporate (32.56%)

    Rank 2: Home Office (19.36%)


Ranking based on share in revenue. These ratings will change if different visual filters are applied. 

   ### [6] Revenue and order count by month
  -- 2019
  
    -- Revenue
  
    Lowest revenue-making month: January
  
    Highest revenue-making month: November
    
    -- Profit
  
    Lowest profit-making month: August
  
    Highest profit-making month: December

  -- 2020
  
    -- Revenue
  
    Lowest revenue-making month: April
  
    Highest revenue-making month: December
    
    -- Profit
  
    Lowest profit-making month: April
  
    Highest profit-making month: March 


This may change if different visual filters are applied.
