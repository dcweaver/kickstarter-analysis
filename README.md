# Kickstarting with Excel

## Overview of Project

### Purpose

The purpose of this analysis was to help Louise look at how her campaign for her play *Fever* compares in relation to other, similar campaigns, in relation to when the campaigns launched and what the funding goal was. This was done through the functions and techniques learned throughout module 1 and week 1 of class.

### Analysis and Challenges

#### Analysis of Outcomes Based on Launch Date

The first goal of the analysis was to determine which month to set a launch date for Louise's campaign in order to have the highest chance of successfully funding her play. In order to accomplish this, first the YEAR() function was used to extract the launch year of every kickstarter campaign in the data set. From there, a pivot table was created from the data. By filtering the pivot table to show only kickstarters for plays, the category that Louise would be launching hers as, selecting launch month as the rows, and selecting the columns to show all possible outcomes for kickstarters, the pivot table below was created.

![](images/pivotTable1-03.png){width="228"} ![](images/pivotFields1-01.png){width="210"}

From this pivot table, a line chart was created to visualize the outcomes of Theater kickstarters, as shown below.

![](images/lineChart1-01.png){width="428"}

### Analysis of Outcomes Based on Goals

The next goal of the analysis was to determine how successful relevant kickstarters have been based on what their funding goal was set to be. In order to accomplish this, first a new worksheet was created and the columns shown below were created to hold the data we are looking for.

![](images/goalColumns-01.png){width="645"}

From here, the columns were created and range from less than 1000 to 50000 or more, jumping by increments of \~4999. In order to populate this new table we created, COUNTIF() functions were used to populate the first three columns. The COUNTIF() functions used for the first three columns are shown below.

=COUNTIFS(Kickstarter!\$D:\$D,"\<1000", Kickstarter!\$F:\$F,"successful",Kickstarter!\$R:\$R,"plays")

=COUNTIFS(Kickstarter!\$D:\$D,"\<1000", Kickstarter!\$F:\$F,"failed",Kickstarter!\$R:\$R,"plays")

=COUNTIFS(Kickstarter!\$D:\$D,"\<1000", Kickstarter!\$F:\$F,"canceled",Kickstarter!\$R:\$R,"plays")

The next column, total projects, was populated using a SUM() function, adding together the total number of projects from the previously populated columns. To populate the final three columns dealing with percent of total being successful, failed, or cancelled, the ROUND() function was used. The code for those three columns is shown below. For each column, the number of successful, failed, and cancelled were divided by the total number of projects within that goal range, and rounded to the nearest whole number. The data type for the final three columns was changed to percentage, so there was no need to multiply the result by 100.

=ROUND(C2/(C2+D2+E2),2) =ROUND(D2/(C2+D2+E2),2) =ROUND(E2/(C2+D2+E2),2)

#### Final Outcome by Goal Table

Shown below is the final table for determining outcomes based on goal.

![](images/goalTable-01.png){width="539"}

Lastly, a line chart was created from this table, comparing the percentage of successful, failed, and cancelled based on what the goal was set to. The y-axis was set to the percentage, and the x-axis was set to show different goal ranges. The graph is shown below.

![](images/goalLineChart-01.png){width="536"}

### Challenges and Difficulties Encountered

#### Deliverable 1 challenges

The challenges in this first analysis was mainly in setting up the pivot table, as I am not that familiar in using them, and I find the setting up of the filters and fields in the pivot table are not very intuitive if you have not had much experience working with them before. The other challenge that I found during this first part of the analysis came more due to my own error, as I unintentionally skipped a step in the modules leading up to the challenge, and didn't have the required "date created conversion column" that was used in conjecture with the YEAR() function to extract the launch year of all kickstarters.

#### Deliverable 2 challenges

For the second analysis, the main challenge came in using the COUNTIFS() function to populate the table with the number of successful, failed, and cancelled kickstarters by goal. The challenge in this came with using multiple parts to the COUNTIFS() funtcion, as it can be tricky when adding multiple parameters to an if function.

## Results

-   What are two conclusions you can draw about the Outcomes based on Launch Date?

    Looking at Outcomes based on Launch Date, we can conclude very concretely that launching a kickstarter campaign for a play is most successful when launched in May or June. There is a sharp spike in the success rate when launched in those two months when compared to the other months. Another conclusion that can be drawn from this date is that very few play kickstarters get cancelled before the end of the campaign, with no more than 7 being cancelled in a single month, and most having only 2 or 3 cancelled at all.

-   What can you conclude about the Outcomes based on Goals?

    When looking at Outcomes based on Goals, it can be concluded that the ideal range for the goal is either 5000 or below, or between 34999 and 44999. Both of those ranges have by far the highest percentage of successful campaigns, with success rates of \~75% and 67% respectively.

-   What are some limitations of this dataset?

    Some limitations on the data are that we did not take into account how long the campaigns went on for in our analysis, which would have a large impact on whether or not a campaign would be successful or not. Another limitation of this dataset would be that when looking at outcomes based on goals, there is not a sufficient sample size for all of the categories, with some only having 1 single campaign in that goal range. This means that we might not be getting the true likelihood of outcome based on goals for every goal range.

-   What are some other possible tables and/or graphs that we could create?

    Some other possible tables or graphs that we could create for this data would be to look at the success rate based on how long a campaign was active on kickstarter for. This would give Louise a better idea of how long she should be expecting to run her campaign to fund raise for her play.
