# Analysis of Britain's Railway System
### A Data Analysis Project using SQL, Visual Studio and PowerBI 
This is a report on the Assignment submitted as one of the Credit coursework for the Southern Alberta Institute of Technology SAIT’s Diploma program in Data Analytics. 

This project analyzes the British Railway system (made up of Private Franchised Train Operating Companies TOC) with a focus on Virgin Trains franchise. The detailed agenda of the analysis is divided into 11 sections, starting with the Six stage problem solving, Business modeling, SQL Tables and Data, SQL Database Diagrams, SSIS Slow Changing Dimensions, SSAS Solution Development, SSAS Solution Deployment via SSAS Browse and Analysis, SSAS Solution Deployment via Excel Export & PivotTables, Predictive Analysis Forecasting, Excel What-If Analysis Scenario Manger, and finally PowerBI Visualizations. However, the report has been summarized and presented here.

The summarized project flowchart is given below:
![Screenshot_20220926-011848_Office](https://user-images.githubusercontent.com/114383545/192220436-9bac0b47-8553-48e8-b11c-b64f6725ecdf.jpg)

## Business Understanding
As an introduction, British rail privatized the industry in 1997 and separated infrastructure from operations, did some franchising of passenger services, and sold off freight operations. Virgin trains is one of the companies that bought into the franchise of the passenger services. Virgin Trains won 2 franchise, West Coast and Cross Country, with the later franchise terminated in 2007. In my analysis, Virgin Trains and West Coast will be used interchangeably.
There exist 20 to 25 Train operating companies TOC, referred to as virgin’s competitors. 
![Screenshot_20220926-012605_Office](https://user-images.githubusercontent.com/114383545/192222080-7cea8ff9-157d-46d9-a15e-3dd98a3fdfea.jpg)

In continuation of the Business understanding, the figure below gives a snapshot of Britain’s railway regions and routes, with Virgin trains sitting under the Northwest and Central Region, as part of West Coast Mainline South route.
![Screenshot_20220926-011912_Office](https://user-images.githubusercontent.com/114383545/192222374-c6d540c4-9bf2-41b7-ae39-88f47426cd3a.jpg) 

Considering the who, what, when, where, why and how, and applying it to virgin trains, the problem / opportunity statement for the business can be easily defined.
![Screenshot_20220926-011921_Office](https://user-images.githubusercontent.com/114383545/192222651-ec19a985-5c74-4f9b-8b03-c0022cc66eda.jpg)

Based on the 5W + 1H framework defined above, I decided to examine the following 3 business questions.
![Screenshot_20220926-011928_Office](https://user-images.githubusercontent.com/114383545/192222871-972b5639-8ffd-4bda-8aa4-789bba2bffc1.jpg) 

## Data Understanding
One of the critical stages of any Data analysis project is understanding the available data, and the relationships that exists between the various business concepts. After examination of available datasets, I identified the general topics as Train operating companies, their Usage, Passenger experience, Train performance, The Finance part, and Health and safety.  The sub parts of these main concepts are given below.

Another important part of a successful project is a well-defined Data dictionary that defines core concepts. One of the core concepts is the Public Performance Measure (PPM) which is a performance indicator that measures how operators are doing service wise. The PPM is the Percentage of trains that arrive less than 10 minutes late. This is an important indicator and is one of the business questions I have decided to address in this analysis.
![Screenshot_20220926-011941_Office](https://user-images.githubusercontent.com/114383545/192223037-8916be81-5143-4c82-9b76-a22c3e858cc4.jpg) 

## Data Preparation
This stage involved Data Extraction, Transformation and Load (ETL). Steps carried here include data wrangling and manipulation, use of SQL Server Import and Export Wizard to load the dataset into SQL Server management studio (SSMS), and use of Visual studio integration services (SSIS) to create a Dimensional model with Dimensions and Facts.
![Screenshot_20220926-011954_Office](https://user-images.githubusercontent.com/114383545/192223152-b61057dc-ebc2-4865-8306-5d4682fe63f0.jpg) 

![Screenshot_20220926-012029_Office](https://user-images.githubusercontent.com/114383545/192223313-ffe3e8fa-701b-4697-9597-b33f4d11e4bf.jpg) 
In SSMS, I set the Primary key (PK) column for each Dimension table, telling the software which column to use as PK. Next, I defined the relationships between each Dimension table PK and corresponding Foreign Key in my Fact table. Afterwards the database diagram was generated.

Visual studio Analysis services (SSAS) provides a layer where table names and column names can be edited/changed to give end users names they are familiar with. For example, I edited Column name PK_Operator to become OperatorID.
![Screenshot_20220926-012327_Office](https://user-images.githubusercontent.com/114383545/192223417-f6149acc-0f2a-4d38-b7d9-32d9abb6d655.jpg) 

## Deep Dive
The First Business question askes if the number of passenger trips has grown for Virgin’s West Coast route. The results in the SSAS Browser compares the number of passenger trip for west coast looking at year 2011 and year 2019.
The number of passenger trips has increased from 30 to 37 million, a positive trend, implying an increase in the growth indicator. The insight also shows that Virgin Train achieved this increase in number of passenger trips with a smaller number of trains, which is some good efficiency on west coast part.

The second business question shows a drop of the PPM score to 80%, meaning a smaller number of trains were arriving within 10 minutes of their scheduled arrival time. This means that even though they had a smaller number of trains, there was no improvement in their PPM. This performance indicators therefore shows that virgin is not doing so well when it comes to train performance.
![Screenshot_20220926-012336_Office](https://user-images.githubusercontent.com/114383545/192223578-ea4dbecd-0b0f-4388-93ca-d924c7c8c5ca.jpg) 

For the second part of Business question 1 and 2, which seeks to compare Virgin Train (West Coast Route) to other train operators, I used Excel PivotTable and Pivot Charts to display the results.

Comparing with other TOCs in the same sector as virgin west coast, we see that number of passengers has increased for other operators in the sector as well, except for Greater Anglia that dropped from 122 million passenger trips to 84 million. That’s some significant drop for Greater Anglia even before the COVID crises of 2020.

For the PPM score, all the operators in this region, west coast included, all seem to be struggling except for Great Western Railway.
![Screenshot_20220926-012346_Office](https://user-images.githubusercontent.com/114383545/192223767-bbf235c4-6bca-4e8f-a0ba-5645fd65f31a.jpg)

For the Business question 3 which seeks to predict Virgin’s Number of Passengers and PPM score for the next 2 years, using 10-years historic data, I used Excel Forecast function for the analysis.
![Screenshot_20220926-012355_Office](https://user-images.githubusercontent.com/114383545/192223995-5ca40963-a527-4885-8033-7b29d414b190.jpg) 

## Visualizations
This section gives screenshot of the PowerBI visualizations that supports the answers to the 3 business questions
![Screenshot_20220926-012404_Office](https://user-images.githubusercontent.com/114383545/192224130-4fca95fd-4b4e-4aff-802a-85f18e0c3b8b.jpg) 

![Screenshot_20220926-012418_Office](https://user-images.githubusercontent.com/114383545/192224275-4f15ac42-d277-4706-bcb5-ed132c59d516.jpg) 

![Screenshot_20220926-012424_Office](https://user-images.githubusercontent.com/114383545/192224369-494b6350-098e-4249-ad5d-b091b57a4adb.jpg) 

![Screenshot_20220926-012429_Office](https://user-images.githubusercontent.com/114383545/192224449-dc79c50c-5e7e-47ab-8a15-0275ffaeabe0.jpg) 

## Evaluation
![Screenshot_20220926-012437_Office](https://user-images.githubusercontent.com/114383545/192224559-a841b656-c497-4ca2-bf10-55f3a35b3903.jpg) 

![Screenshot_20220926-012444_Office](https://user-images.githubusercontent.com/114383545/192224630-5c3b2bba-145a-4ec9-9b97-28571660ba4e.jpg) 

## Recommendations & Conclusion
![Screenshot_20220926-012455_Office](https://user-images.githubusercontent.com/114383545/192224837-1b2ea799-791c-40eb-8bf9-6a85a9983218.jpg)
