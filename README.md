Excel to Power BI
=================

![Excel to Power BI Animated Diagram](assets/images/kaggle_to_powerbi.gif)

Table of Contents
-----------------

*   [🎯 Project Overview](#project-overview)
*   [📈 Dashboard Design](#dashboard-design)
    *   [Mockup](#mockup)
    *   [Tools](#tools)
*   [🛠️ Data Development](#data-development)
    *   [Pseudocode](#pseudocode)
    *   [Data Exploration](#data-exploration)
    *   [Data Cleaning](#data-cleaning)
    *   [Transforming the Data](#transforming-the-data)
    *   [Creating the SQL View](#creating-the-sql-view)
*   [🔍 Testing and Validation](#testing-and-validation)
    *   [Row Count Check](#row-count-check)
    *   [Column Count Check](#column-count-check)
    *   [Data Type Check](#data-type-check)
    *   [Duplicate Check](#duplicate-check)
*   [📊 Visualization and Analysis](#visualization-and-analysis)
    *   [Results](#results)
    *   [DAX Measures](#dax-measures)
    *   [Key Findings](#key-findings)
    *   [ROI Validation](#roi-validation)
*   [💡 Recommendations](#recommendations)
    *   [Potential ROI](#potential-roi)
    *   [Action Plan](#action-plan)
*   [📋 Conclusion](#conclusion)

🎯 Project Overview
-------------------

### Objective

The objective of this project is to identify the top UK YouTubers in 2024, helping the marketing team decide which YouTubers would be ideal for upcoming marketing campaigns. The dashboard provides insights into metrics such as subscriber count, total views, total videos, and engagement metrics.

### Data Source

The data used in this analysis was sourced from [Kaggle](https://www.kaggle.com/datasets/bhavyadhingra00020/top-100-social-media-influencers-2024-countrywise?resource=download), specifically an Excel file containing data on the top 100 social media influencers in 2024.

📈 Dashboard Design
-------------------

### Mockup

The dashboard is designed to answer key questions, such as identifying the top 10 YouTubers by subscribers, most viewed channels, and those with the highest engagement rates. The visuals include tables, scorecards, and bar charts.

![Dashboard Mockup](assets/images/dashboard_mockup.png)

### Tools

*   **Excel**: Data exploration
*   **SQL Server**: Data cleaning, testing, and analysis
*   **Power BI**: Data visualization
*   **GitHub**: Project documentation and version control
*   **Mokkup AI**: Dashboard wireframe design

🛠️ Data Development
--------------------

### Pseudocode

1.  Get the data from Kaggle.
2.  Explore and clean the data in Excel.
3.  Load the cleaned data into SQL Server.
4.  Perform data transformations in SQL.
5.  Visualize the results in Power BI.
6.  Publish the project on GitHub.

### Data Exploration

Initial observations include identifying relevant columns, extracting YouTube channel names, and recognizing unnecessary columns to be removed.

### Data Cleaning

The data was cleaned to retain only relevant columns, with appropriate data types and no null values. Here is the final schema:

Column Name

Data Type

Nullable

channel\_name

VARCHAR

NO

total\_subscribers

INTEGER

NO

total\_views

INTEGER

NO

total\_videos

INTEGER

NO

### Transforming the Data

SQL was used to transform and clean the data. This involved extracting channel names and casting them into the correct format.

  

SELECT

    SUBSTRING(NOMBRE, 1, CHARINDEX('@', NOMBRE) -1) AS channel\_name,

    total\_subscribers,

    total\_views,

    total\_videos

FROM

    top\_uk\_youtubers\_2024

  

### Creating the SQL View

A SQL view was created to store the transformed data, making it easier to query and visualize in Power BI.

CREATE VIEW view\_uk\_youtubers\_2024 AS

SELECT

    CAST(SUBSTRING(NOMBRE, 1, CHARINDEX('@', NOMBRE) -1) AS VARCHAR(100)) AS channel\_name,

    total\_subscribers,

    total\_views,

    total\_videos

FROM

    top\_uk\_youtubers\_2024;

  

🔍 Testing and Validation
-------------------------

### Row Count Check

A row count check was conducted to ensure the number of records matched the expected total.

### Column Count Check

The number of columns was verified to ensure all necessary data fields were included.

### Data Type Check

The data types of each column were checked to ensure compatibility with SQL queries and Power BI.

### Duplicate Check

A check for duplicate records was performed to ensure data integrity.

📊 Visualization and Analysis
-----------------------------

### Results

The final dashboard was created in Power BI, highlighting the top UK YouTubers based on various metrics.

![GIF of Power BI Dashboard](assets/images/top_uk_youtubers_2024.gif)

### DAX Measures

Custom DAX measures were created to calculate key metrics such as total subscribers, total views, and average views per video.

### Key Findings

*   **Top YouTubers**: Dan Rhodes, NoCopyrightSounds, and DanTDM lead in subscriber count.
*   **Most Active Channels**: GRM Daily, Manchester City, and Yogscast have uploaded the most videos.
*   **Highest Views**: DanTDM, Dan Rhodes, and Mister Max have the highest total views.

### ROI Validation

Calculations were made to determine the potential ROI for different collaboration scenarios, focusing on maximizing net profit for the marketing campaigns.

💡 Recommendations
------------------

### Potential ROI

*   **Dan Rhodes** offers the highest potential ROI per video with an estimated net profit of $1,065,000.
*   **Mister Max** could generate a net profit of $1,276,000 through influencer marketing.
*   **NoCopyrightSounds** and **DanTDM** also present significant profit opportunities.

### Action Plan

1.  Initiate contact with Dan Rhodes for potential collaboration.
2.  Negotiate contracts within the allocated budget.
3.  Launch and monitor campaigns, adjusting based on performance and feedback.
4.  Consider future partnerships with other top channels if initial campaigns prove successful.

📋 Conclusion
-------------

This project demonstrates a comprehensive approach to identifying key YouTube influencers for marketing collaborations, from data extraction and cleaning in Excel and SQL Server to visualization in Power BI. By focusing on metrics like subscriber count and engagement, the recommended course of action will maximize ROI for the marketing team. Further partnerships with identified YouTubers could lead to highly successful marketing campaigns throughout the year.
