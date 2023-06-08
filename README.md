# PowerBI Project HR Employees Data Insight With CSV Dataset

[Follow me on LinkedIn](https://www.linkedin.com/in/abhishekmishra3/) &nbsp;&nbsp; | &nbsp;&nbsp;  [Github Repository Link](https://github.com/abhishekmishra8/PowerBI_Project_HR_Employees) &nbsp;&nbsp; | &nbsp;&nbsp; [Github Page Link](https://abhishekmishra8.github.io/PowerBI_Project_HR_Employees/)

Project Report Video shown below:  

<video width="360" height="360" controls autoplay muted loop>
<source src="Input Files/Video/HR Employees Report Video.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>  

Dashboard Screenshots as follow:-  

<img src="Input Files/Images/Power BI Report HR Employees - Home.JPG" width="400" height="250" /> &nbsp;&nbsp; <img src="Input Files/Images/Power BI Report HR Employees - Details.JPG" width="400" height="250" />  




## key Learning are as follow:-

1. Import CSV File -> Transform in Power Query -> Split Column by Delimiter.  
-Select Tab -> Advance option Columns -> ok
-Use First Row as Headers
- Applied Steps : You can time travel to see what happened in those steps and re-edit them if needed.  
- Load it in Power BI : Close & Apply.  
<img src="Input Files/Images/Importing Data from CVS File.JPG" width="400" height="250" />  &nbsp;&nbsp;  <img src="Input Files/Images/Applied Steps in Power Query.JPG" width="400" height="250" />

2. Create the Shapes for background of Visual with some Cosmetic changes. 

3. Create new table for all new measures. Home -> Enter Data. Create New Measures here.
- `Total Exmployees = COUNTROWS('HR Analytics Data')`
- `Male = CALCULATE([Total Exmployees],'HR Analytics Data'[Gender]="Male")`
- `Female = CALCULATE([Total Exmployees],'HR Analytics Data'[Gender]="Female")`
- `% MALE = DIVIDE([Male],[Total Exmployees],0)`
- `% FEMALE = DIVIDE([Female],[Total Exmployees],0)`

4. Create Cards and place it in places. Total Emp, Male Female with percentage data.
- Insert Male Female image icon.

5. Add new conditional column in Power Query. 
- Promotion Status. Whoever had never been promoted since last 10 yrs is now due for promotion.
- Add Column -> Add Contional Column -> Close and Apply  
<img src="Input Files/Images/Add Conditional Column Promotion Status.JPG" width="400" height="250" />

6. Create Dax Measures of Percentage and Count of Employee Promotion data.
- `Due for Promotion = CALCULATE([Total Exmployees], 'HR Analytics Data'[Promotion Status]="due for promotion")`
- `Not due for promotion = CALCULATE([Total Exmployees], 'HR Analytics Data'[Promotion Status]="Not Due")`
- `% Due for promotion = DIVIDE([Due for Promotion], [Total Exmployees],0)`
- `% Not Due = DIVIDE([Not due for promotion], [Total Exmployees],0)`

7. Create Cards to show Employee Promotion data with formattings applied.

8. Service Years Data. Transform data in Power Query.
- Add Column -> Column from Selection -> select column YearAtCompany -> Enter data 6 Years -> It will populate Sufix Year in all data in new Column.
- Repeat same steps and create new Column with Job Levels data.
- Close & Apply

9. Create Bar Chart to show Service Years Visual against Total no. of Employess.
- add new more columns in Tooltips to show additional details of employess.  
<img src="Input Files/Images/Add Tooltip in BarChart.png" width="400" height="250" />

10. Create Column Chart to display Job Level Views.  
<img src="Input Files/Images/Column Chart Job Level View.png" width="400" height="250" />  

11. Retrenchment Scenario. Company will layoff the employees who spent 18+ years in organization and rest will stay.
- Create new column in Power Query. Conditional coloumn -> YearsAtCompany - is greater than or equal to - 18 - Output will be retrenched. Else - On Service.  

12. Create Dax Measures to get count and percentage of retrenchment data.
- `On Service = CALCULATE([Total Exmployees], 'HR Analytics Data'[Retrenchment Status]="On Service")`
- `Will be retrenched = IF(ISBLANK(CALCULATE([Total Exmployees], 'HR Analytics Data'[Retrenchment Status]="Will be retrenched")),0,CALCULATE([Total Exmployees], 'HR Analytics Data'[Retrenchment Status]="Will be retrenched"))`
- `% On service = DIVIDE([On Service], [Total Exmployees], 0)`
- `% will be retrenched = DIVIDE([Will be retrenched], [Total Exmployees], 0)`  

13. Create cards to display the retrenchment data.  
<img src="Input Files/Images/Retrenchment data on Cards Visual.png" width="400" height="250" />  

14. Employees staying very far, very close, near to the office. Create new column in Power Query.
- Add Contional column -> DistanceFromHome - greater than Equal to - 20 = Very Far ; 10 = Close ; Else = Very Close
- Display this data in Donut chart against Total number of Employees.  
<img src="Input Files/Images/Donut Chart Emplyees Far from office.png" width="400" height="250" />  

15. Import new table of Employees available in CSV file. Transform in Power Query.
- Go to HR Analytics Data -> Home -> Merge Queries -> locate column EmployeeNumber -> Select table HR Employee Data -> select column EmployeeNumber -> Ok
- Set relation of table by checking EmplyeeName	as shown below.Close and Apply.    
<img src="Input Files/Images/Relationship HR Employee Data.JPG" width="400" height="250" /> &nbsp;&nbsp; <img src="Input Files/Images/After Result of Relation Set.JPG" width="400" height="250" />

16. Create new Column in Power Query of Job Satisfaction and performance status using Conditional Column.

17. Create Visuals of Employees showing insights.
- Column bar Chart : Job Satisfaction against Total Employess. 
- Donut Chart : How many Employess do the Over Time
- Employess performance show on card in percentage.
- Diplay Employee Data and Retrenchment in Job Role wise using Table visual.

18. Create a page Navigation of both the report pages.


Credits :-  Thanks to Data with Decision

[Guided Project Youtube Video Click Here](https://www.youtube.com/watch?v=0BKlUySopU4&t=246s) 
