# Virtual Machine (VM) Exercises

## :information_source: Read this before getting started
- The two exercises should not replicate the exact actions shown in your screencast. The goal of exercises is for learners to apply what was learned in the screencasts to new problems or situations. This is best pedagogical practice for retaining and building skills. For example, this can be done by using another dataset between screencasts and exercises or focusing on a different portion of the dataset.
- We can only run free versions of BI software in our virtual machine exercises. In the case of Power BI, make sure the exercises can run on [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/) without any additional paid products. 
- Unsure what the scope of an exercise should be? Here's an [example](https://campus.datacamp.com/courses/introduction-to-power-bi/getting-started-with-power-bi?ex=14) from Introduction to Power BI. The first chapter of most DataCamp courses are free, so take a look at our [BI courses](https://learn.datacamp.com/courses?technologies=Tableau&technologies=Power%20BI) to get a feel for how we assess and guide learners.

## 1st VM Exercise: Create Costs Hierarchy

#### Dataset

Costs_Parent_Child.csv

#### Files

ex-1-initial.xlsx

ex-1-solution.xslx

#### Learning Objective

Enable students to transform a parent-child cost table into a costs hierarchy that enables more efficient data analysis and reporting.

#### Context

Flattening a parent-child table into a hierarchical table is crucial for financial analysts. This skill allows analysts to organise complex financial data structures that are organised in the parent-child format and create multi-level categorizations. Such data structures are present in cost structures, charts of accounts, project structures, client segmentation, revenue breakdown.

#### Steps to be executed by the student (max 6)

- Using the power query editor, load the parent-child table containing the cost type structure (Costs_Parent_Child.csv).

- Create a new query called COSTS_HIERARCHY by referencing the Costs_Parent_Child query.

- In the COSTS_HIERARCHY query, keep the roots only by joining the  COSTS_HIERARCHY query with itself on the Parent - Child column, and expand the Child column of the 2nd table in the join.

- Filter the COSTS_HIERARCHY query by keeping only the null values in the expanded Child column of the 2nd table in the join, keep only the Parent column of the 1st table in the join (remove the other columns), rename the Parent column to LVL1, and remove the duplicates in Parent column.

- In the COSTS_HIERARCHY query, create the level 2 of the hierarchy by joining the  COSTS_HIERARCHY query with itself on the Parent - Child column, expand the Child column of the 2nd table in the join and rename the column to LVL2.

- In the COSTS_HIERARCHY query, create the level 3 of the hierarchy by joining the  COSTS_HIERARCHY query with itself on the Parent - Child column, expand the Child column of the 2nd table in the join and rename the column to LVL3.

#### Exercise question:
Browse the COSTS_HIERARCHY using a pivot table, change the visualisation type to Outline Form and visualise the LVL1, 2 and 3 of the cost structure. What is the only LVL2 cost type that does not have a LVL3 value in the hierarchy?


#### End goal:
The only LVL2 cost type that does not have a LVL3 value in the hierarchy is Depreciation (see Costs Hierarchy worksheet in the Costs planning file):

![image](https://github.com/mdinu-hash/sme-bi-course-application-mdinu/assets/142972958/78602e0d-4066-4e3b-9122-36ab84c7fa61)


## 2nd VM Exercise: Create a Cost Analysis Data Model

#### Dataset

Costs_Parent_Child.csv
Operating_Expenses.csv

#### Files

ex-2-initial.xlsx
ex-2-solution.xlx

#### Learning Objective

Build a data model with cost hierarchies that enables efficient financial analysis by joining relevant tables and exploring the result in a pivot table.

#### Context

Building a robust data model for financial analysis is vital for gaining actionable insights. A robust data model is flexible enough to account for changes in the cost structure, such as adding a new cost type. This skill enables financial analysts to perform in-depth budgeting, forecasting, and decision-making processes.

#### Steps to be executed by the student (max 6)

- In the COSTS_HIERARCHY query, add the LEAF column showing the leaf of the hierarchy. Use the conditional column.

- Using the power query editor, load the operating expenses table (Operating_Expenses.csv).

- In the Operating_Expenses table, create the column Total Costs as equal to Units x Cost Per Unit.

- Create a relationship between Operating_Expenses table - column Cost type, and COSTS_HIERARCHY table - column LEAF.

- Create a pivot table to browse costs per month: Add the months as columns, LVL1,2 and 3 of the costs hierarchy to rows, and Cost Per Unit, Units and Total Costs in values.


#### Exercise question:
What are the total business expenses in march?

#### End goal:

Total business expenses in march is 13250, see Costs planning file -> Operating expenses sheet.

![image](https://github.com/mdinu-hash/sme-bi-course-application-mdinu/assets/142972958/40cd3e35-72fe-4c93-bc65-957eaa18b168)


