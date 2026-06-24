 # Employee-HR-Analytics-Dashboard-
 Step 1: Import Dataset
Open Power BI Desktop.
Click Get Data → Excel Workbook.
Select Employee_HR_Analytics_Dataset.xlsx.
Click Load.
Step 2: Verify Data Types
Go to Data View.
Check:
EmployeeID → Text
Name → Text
Department → Text
Gender → Text
Salary → Whole Number
Experience → Whole Number
Rating → Whole Number
Status → Text
Step 3: Create Measures
Right-click Employee table.
Click New Measure.
Create:
Total Employees = COUNT(Employee[EmployeeID])
Total Salary = SUM(Employee[Salary])
Average Salary = AVERAGE(Employee[Salary])
Highest Salary = MAX(Employee[Salary])
Lowest Salary = MIN(Employee[Salary])
Active Employees =
CALCULATE(
COUNT(Employee[EmployeeID]),
Employee[Status]="Active"
)
Employees Left =
CALCULATE(
COUNT(Employee[EmployeeID]),
Employee[Status]="Left"
)
Attrition Rate =
DIVIDE(
[Employees Left],
[Total Employees],
0
)*100
Step 4: Create Calculated Columns
Performance Category
Click New Column.
Performance Category =
IF(
Employee[Rating]>=4,
"High Performer",
"Needs Improvement"
)
Salary Band
Salary Band =
IF(
Employee[Salary]>=70000,
"High Salary",
"Normal Salary"
)
Dashboard Page 1 – HR Overview
Step 5: Add KPI Cards

Insert 6 Card Visuals:

Total Employees
Active Employees
Employees Left
Average Salary
Highest Salary
Attrition Rate
Step 6: Department Distribution
Insert Clustered Bar Chart.
Drag:
Department → Axis
EmployeeID → Values (Count)
Step 7: Gender Distribution
Insert Pie Chart.
Drag:
Gender → Legend
EmployeeID → Values (Count)
Dashboard Page 2 – Performance Analysis
Step 8: Rating Distribution
Insert Clustered Column Chart.
Drag:
Rating → Axis
EmployeeID → Values (Count)
Step 9: Performance Category
Insert Donut Chart.
Drag:
Performance Category → Legend
EmployeeID → Values (Count)
Step 10: Employee Details Table
Insert Table Visual.
Add:
EmployeeID
Name
Department
Salary
Experience
Rating
Performance Category
Dashboard Page 3 – Salary Analysis
Step 11: Average Salary by Department
Insert Bar Chart.
Drag:
Department → Axis
Average Salary → Values
Step 12: Salary Band Analysis
Insert Donut Chart.
Drag:
Salary Band → Legend
EmployeeID → Values (Count)
Step 13: Matrix Visual
Insert Matrix.
Drag:
Department → Rows
Gender → Columns
Average Salary → Values
Step 14: Add Slicers

Insert Slicers for:

Department
Gender
Status
Performance Category
Step 15: Format Dashboard
Add Title:
Employee HR Analytics Dashboard
Apply Theme:
View → Themes
Align visuals properly.
Add data labels and chart titles.
Final Dashboard Pages
Page 1
KPI Cards
Department Distribution
Gender Distribution
Page 2
Rating Distribution
Performance Category
Employee Details Table
Page 3
Average Salary by Department
Salary Band Analysis
Matrix Report
