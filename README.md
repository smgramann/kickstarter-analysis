
# Kickstarting with Excel

## Overview of Project

### Background
Louise's Kickstarter campaign for her play, Fever, came close to its fundraising goal in a short amount of time.  The purpose of these additional analyses is to help Louise understand other campaigns’ performances as they relate to launch date and funding goals.

### Purpose
To gain further information on Kickstarter campaign trends, analyses were conducted to assess outcomes of varying campaigns as it relates to their launch months and funding goals.  Data pertaining to theater Kickstarters were first organized by month of campaign launch and then by outcome to visualize on a simple line chart.  Next, data pertaining to ‘play’ Kickstarter campaigns were organized by 12 different goal funding ranges, the outcomes for each range were converted to percentage of total projects with a particular outcome, and then visualized in a line chart. 

## Analysis and Challenges
### Analysis of Outcomes Based on Launch Date
To analyze outcomes of campaigns based on launch date:

1)	A “Years” column was created in the kickstarter worksheet based on the “Date Created Conversion” column utilizing a simple Year() function.
2)	A pivot table was then created to aggregate the outcomes by launch date (grouped by months) with the table filters set to Parent Category = Theater and Years = All and the outcomes filtered on successful, failed, and canceled.  Outcomes were sorted in descending order.

![Theater Outcomes By Launch Date Pivot](https://user-images.githubusercontent.com/80165223/111924085-a7232280-8a70-11eb-9fab-bf31f95fc8dd.png)


3)	A line chart was created to visualize the trend lines of the three different outcomes of the theater campaigns (successful, failed, and canceled) over the course of the 12 months in a year, including all years in the dataset.

![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/80165223/111924111-c8840e80-8a70-11eb-9c31-eee88923a35f.png)


### Analysis of Outcomes Based on Goals

To analyze outcomes based on goals:

1)	A new worksheet was created with eight new headers:  Goal, Number Successful, Number Failed, Number Canceled, Total Projects, Percentage Successful, Percentage Failed, and Percentage Canceled.
2)	In the goal column 12 dollar-amount ranges were created between “Less than 1K” and “Greater than 50K”
3)	The CountIF() function was utilized to populate the count of campaign outcomes (columns B-D) by goal dollar-amount ranges with ‘play’ campaigns as criteria.  Below is a picture of table set up with an example of the CountIF() formula used to populate a cell:

![Outcomes by Goal-Amount - CountIF() Function](https://user-images.githubusercontent.com/80165223/111924149-fd906100-8a70-11eb-9749-dafa414642c4.png)


4)	The total projects column was populated utilizing the sum() function for each outcome within each goal dollar-amount range.

![Outcomes by Goal-Amount - Total Project Calculation](https://user-images.githubusercontent.com/80165223/111924165-0f720400-8a71-11eb-950a-5c9a10758e41.png)


5)	The percentage of each outcome type by each goal dollar-amount range was calculated by dividing the outcome count for each goal dollar-amount by the total project for the dollar amount range.

![Outcomes by Goal-Amount - Percentage of Outcome Calc](https://user-images.githubusercontent.com/80165223/111924172-1731a880-8a71-11eb-866d-1fa40db98bea.png)


6)	A line graph was created to visualize the percentage of each outcome (for plays) across the various goal-amount ranges.

![Outcomes_vs_Goals](https://user-images.githubusercontent.com/80165223/111924180-20227a00-8a71-11eb-9b36-f34af9f3bb84.png)


### Challenges and Difficulties Encountered

One major challenge was encountered in this analysis that pertained to the CountIF() function.  It took several attempts to get the formula set up correctly and then to figure out the most efficient way to carry those formulas across the various goal outcomes and dollar-amount cells to avoid typing the formula into each cell.  First, I forgot to add in the ‘play’ criteria, which I caught and added in.  Next, when I would drag the CountIF() formula created across the columns, the source data column in the Kickstarter sheet would change.  I utilized the dollar sign ($) in my formula to fix the source column across my Outcomes Based on Goals columns.

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

1)   Theater campaigns tend to be most successful in May, June, and July, especially May.
2)  Theater campaigns tend to have equal success and failure rates in the month of December

- What can you conclude about the Outcomes based on Goals?

In general, it can be concluded that as the goal dollar-amount increases for ‘play’ campaigns the likelihood of failure increases, especially once the goal is over $45,000.

- What are some limitations of this dataset?

A few limitations have been identified in this dataset.  First, it provides no basic information about the backers, which would be helpful for analysis and launching very targeted campaigns to increase success.  Second, more information about each campaign would be helpful to understand how it was advertised, city/state/territory where it was launched, etc. to identify the components of those that succeed and those that fail. 

- What are some other possible tables and/or graphs that we could create?

Additional tables and graphs might include the following:

   1) A cluster bar chart that focuses on year and outcome to identify whether certain years were more successful than others thus driving the trends of the month-over-month line  chart.
   2) A table that aggregates ranges for count of backers by the goal range would help identify how wide-reaching advertising of the campaign might be needed to obtain the right number of backers.
