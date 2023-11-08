**Cloudera Data Warehouse Workshop** 

**Self Service Hands On Lab**

**Index:**

[**Business Use Case ****3**](https://docs.google.com/document/d/1wdtnOMvqEpb0fl_7iXvd5UpBZYGOFGmz4cuC4638RrM/edit#heading=h.4co8bcuxf6kb)

[**Introduction to the Lab Data ****4**](https://docs.google.com/document/d/1wdtnOMvqEpb0fl_7iXvd5UpBZYGOFGmz4cuC4638RrM/edit#heading=h.okk6r21jjeq6)

[**Lab Setup ****6**](https://docs.google.com/document/d/1wdtnOMvqEpb0fl_7iXvd5UpBZYGOFGmz4cuC4638RrM/edit#heading=h.9l8xqeur7ve8)

[**Get Started - Log into CDP ****6**](https://docs.google.com/document/d/1wdtnOMvqEpb0fl_7iXvd5UpBZYGOFGmz4cuC4638RrM/edit#heading=h.ifhhblfnxp57)

[**Lab 1 - Business Analyst: Explore Completed Dashboard ****8**](https://docs.google.com/document/d/1wdtnOMvqEpb0fl_7iXvd5UpBZYGOFGmz4cuC4638RrM/edit#heading=h.3b9y1a2qom3m)

[**Lab 2 - Business Analyst: Self Service (in CDW) ****12**](https://docs.google.com/document/d/1wdtnOMvqEpb0fl_7iXvd5UpBZYGOFGmz4cuC4638RrM/edit#heading=h.v7jbpz4a9fgo)

[**Lab 3 - Administrator: “Productionalize” the Open Data Lakehouse ****34**](https://docs.google.com/document/d/1wdtnOMvqEpb0fl_7iXvd5UpBZYGOFGmz4cuC4638RrM/edit#heading=h.7eeugrot650n)

[**(Optional Bonus Material) ****49**](https://docs.google.com/document/d/1wdtnOMvqEpb0fl_7iXvd5UpBZYGOFGmz4cuC4638RrM/edit#heading=h.zbplwu9g5mrl)

[**Optional Lab 1 - CDW Tour ****49**](https://docs.google.com/document/d/1wdtnOMvqEpb0fl_7iXvd5UpBZYGOFGmz4cuC4638RrM/edit#heading=h.747qwikq91jm)

[**Optional Lab 2 - Self Service File Upload ****50**](https://docs.google.com/document/d/1wdtnOMvqEpb0fl_7iXvd5UpBZYGOFGmz4cuC4638RrM/edit#heading=h.rt00z7rbmh9o)

[**Optional Lab 3 - Performance Optimizations (Impala VW) ****53**](https://docs.google.com/document/d/1wdtnOMvqEpb0fl_7iXvd5UpBZYGOFGmz4cuC4638RrM/edit#heading=h.cgofhkg5m9op)

[**Optional Lab 4 - Data Visualization ****57**](https://docs.google.com/document/d/1wdtnOMvqEpb0fl_7iXvd5UpBZYGOFGmz4cuC4638RrM/edit#heading=h.vq6ffohtl0n5)

[**Optional Lab 5 - Data Security & Governance ****74**](https://docs.google.com/document/d/1wdtnOMvqEpb0fl_7iXvd5UpBZYGOFGmz4cuC4638RrM/edit#heading=h.oxmyi34wrz72)

[**Optional Lab 6 - Iceberg Table Rollback ****80**](https://docs.google.com/document/d/1wdtnOMvqEpb0fl_7iXvd5UpBZYGOFGmz4cuC4638RrM/edit#heading=h.260favsmn54x)


##

##

## Business Use Case

The following Labs will take you through a Self-Service Analytics example.  We will use a fictitious company named, Special Marketing Group (SMG).  A little company background on SMG is that they are a marketing data aggregator company that is currently working closely with Duty-Free Shops in many airports throughout the U.S. and 20+ countries.  SMG is working with the Duty-Free Shop owners on an initiative to drive additional revenue into the shops.  The duty-free shop owners want to partner with specific airlines to offer discounts through the airlines to their passengers who spend more time in an international terminal than warranted for their flight.

SMG believes that it can help drive more revenue by driving more traffic to the duty-free shops.  SMG realizes that they have some questions that need to be answered, such as:

- Which airlines have the most passengers who have long layovers built into their tickets?
- Which airlines have the most passengers who have delayed international legs in their itinerary causing an extended layover in their flight itinerary?
- Which airlines have the most passengers who are displaced by a missed international connection, caused by a delay in their previous leg?

By answering these burning business questions SMG will be able to work with duty-free shop owners to develop campaigns that they can run to drive additional revenue.  Since, SMG also does quite a bit of business with many of the major airlines and believes that the analytics used to drive more revenue for duty-free shops could also help the airlines improve customer satisfaction during extended wait times, and duty-free shops can increase sales.

Our Labs today will walk through the steps to learn how SMG uses the power of Cloudera’s Data Warehouse Data Service to leverage the Self-Service capabilities to build out this new solution.  If/when the Business Analyst proves that this new data will work to solve the need, they can turn it over to the admin team to “productionalize” it.

GET STARTED

- Preparatory work for us to get ourselves oriented in CDW and ready to build out the use case
- Login to CDP
- Learn a little about Cloudera Data Warehouse (CDW) Data Service

SEE THE END RESULT (WHAT IS CREATED) (LAB 1)

- Explore the created Dashboard after it has been “productionalized”

  - Analyst first validates that the combination of data answers questions & builds initial Dashboard to start gaining insights on the data
  - Administrator picks up and formalizes the data ingestion for the new data, incorporates it into the Data Lakehouse, adds security, & completes the Dashboard

BUSINESS ANALYST - SELF SERVICE TO VALIDATE NEW DATA ANSWERS QUESTIONS (LAB 2)

- Upload new data - passenger ticket manifest

  - See if new data can help to answer questions prior to undertaking a complete project
  - See how to upload data

- Answer burning business questions to see if the new passenger data

  - Combine uploaded data with existing data warehouse
  - Start digging into the data - running a few queries to see if the new dataset can help with answering the burning questions
  - Visualize the data - modify existing Dashboard to add new content with the data just added

ADMINISTRATOR - “PRODUCTIONALIZE” INTO OPEN DATA LAKEHOUSE (LAB 3)

- See “how the sausage was made” - how to take advantage of Apache Iceberg from end to end to deliver a modern Open Data Lakehouse solution

  - Migrate existing tables to Iceberg Table Format

  - Create a new Iceberg table

  - Load data

  - Some Key Features of Iceberg

    - Partition evolution
    - Time Travel

- Monitor the Virtual Warehouses (compute) and watch as it scales up and down, suspends, etc.

- Security & Governance before launching to the masses

CONTINUE ON POST THIS WORKSHOP

_Work with your Breakout SE to go thru these Labs after we wrap up_

- Cloudera Data Warehouse (CDW) Tour

- “Make it Better” - Performance Improvements

  - Materialized Views - improve performance
  - Monitor, report, kill queries that run amuck, etc…

- Develop Rich Visualizations for Analysts & Engineers to use insights - more on Cloudera Data Viz

***


## Introduction to the Lab Data

For the following Workshop Hands On Labs, we will dive into this Scenario to show Cloudera Data Warehouse (CDW) is used to enable SMG to gain a competitive advantage - and at the same time, it highlights the performance and automation capabilities that help ensure performance is maintained while controlling costs.

The Hands On Labs will take you through how to use the Cloudera Data Warehouse service to quickly explore raw data, create curated versions of the data for simple reporting and dashboarding, and then scale up usage of the curated data by exposing it to more users.

ER - Diagram of the demo Data Lakehouse: 

- **Fact table:** flights (86M rows) 
- **Dimension tables:** airlines (1.5k rows), airports (3.3k rows) and planes (5k rows)

![](images/1.png)

Self Service data file - Passenger Ticket manifest: 

- This is a CSV file with 1,000 records
- Each record represents a unique Passenger Ticket with 2 Flight Legs
- It contains the following schema

ticketnumber BIGINT

leg1flightnum BIGINT

leg1uniquecarrier STRING

leg1origin STRING

leg1dest STRING\
leg1month BIGINT

leg1dayofmonth BIGINT

leg1dayofweek BIGINT

leg1deptime BIGINT

leg1arrtime BIGINT

leg2flightnum BIGINT

leg2uniquecarrier STRING

leg2origin STRING

leg2dest STRING

leg2month BIGINT

leg2dayofmonth BIGINT

leg2dayofweek BIGINT

leg2deptime BIGINT

leg2arrtime BIGINT


## Lab Setup

Workshop Attendees will be provided with a Login.  Please enter your details below for reference throughout these lab exercises.

- Lab Group #: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ (this will be your breakout room number)

  - You will use this to replace the “**#**” within the lab exercises with the number you enter here

- URL: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ 

  - Use Incognito Browser window

- Login: 

  - **User:** \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
  - **Password:** \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

In the labs when you see:

- ${user\_id} or \<user\_id> - this will indicate to use your User (Workload User) provided for you to login to CDP
- ${bucket} - this will indicate to use the bucket provided to you


## Get Started - Log into CDP

In this Lab you will login to CDP and complete your user setup.

1. Log in to CDP - open a browser and open the URL from the Lab Setup section

   - When prompted use the Login details from the Lab Setup section for the User/PW

2. On the HOME page of CDP you will see all of the Services available to you

![](images/2.png)

- Multi-function analytics - Data Services; today we’ll just focus on the Cloudera Data Warehouse Data Service

- There are other Data Services that usually are part of an Analytic use case 

  - Data Flow - for data ingestion needs
  - Data Engineering - for ELT/ETL, transformations, data wrangling, etc.
  - Machine Learning - for Data Science teams to collaboratively build and productionalize ML/AI applications and models for the Enterprise

- However, Cloudera provides other services such as Data Catalog, Replication Manager, Workload Manager, and Management Console provide continuity and functionality throughout the platform.

![](images/3.png)

Note: The platform removes the necessity to spend unnecessarily on integration tax, where other solutions combine various pieces together in the ability to provide continuity and functionality throughout an end-to-end use case but this is difficult because it introduces many moving parts.

***


##

## Lab 1 - Business Analyst: Explore Completed Dashboard

In this Lab you will explore the Dashboard that will be created as the result of the Self-Service Labs you will complete shortly.

3. Open Cloudera Data Visualization, which is part of the Cloudera Data Warehouse Data Service

   - First let’s open Cloudera Data Warehouse (CDW) - 

     - Click on the Cloudera Data Warehouse (CDW) tile

![](images/2.png)

- We’ll come back to this screen in Lab 2 for more details

![](images/5.png)

- Now let’s open Cloudera Data Visualization (CDV) - to explore the finished product

  - Open Cloudera Data Visualization (CDV or Data Viz)

    - On the left navigation panel click “Data Visualization” - this will open a new browser tab
    - On the row with **airlines-dataviz-#**, to the right, click the Data VIZ button

![](images/6.png)

- If you see the “What’s New” page, you can read it, or click on the GOT IT button

<!---->

- Cloudera Data Visualization (CDV) Home page

![](images/7.png)

- There are 4 areas of CDV - HOME, SQL, VISUALS, DATA - these are the tabs at the top of the screen in the black bar to the right of the Cloudera Data Visualization banner

  - HOME - this is the starting point; it shows some statistics at the top, followed by some quick access details to recent content - Queries, Connections, Datasets, and Dashboards
  - SQL - allows you to manually build queries against data to perform quick discovery against the data.  Below is an example of a query that was built and Run

![](images/8.png)

- VISUALS - an area for viewing/building/modifying visuals, dashboards, and applications

![](images/9.png)

- DATA - interface for access to datasets (aka: metadata model) image below, connections, and the Connection Explorer

![](images/10.png)

- Click on the VISUALS tab at the top of the screen (in black banner)

![](images/11.png)

- On the left side of the page make sure you have the All or Public Workspace selected

<!---->

- Click on the tile “SMG Duty Free Analysis” to open the Application (in the bottom right of the tile you will see a purple ![](images/12.png) icon  identifying an Application)

  - Click the drop-down arrow next to the “Planned Layover” prompt and change it from “All Passengers” to “30+ Minutes” - since the initial questions SMG was interested in pursuing were related to passengers with “Long” planned layovers - select “90+ Minutes”.

  - Next, click the drop-down arrow next to “Connection Airport” - Select a few of the Airports that are interested in this new business program

    - Scroll (or search) and click the checkbox next to - ATL, LGA, and ORD
    - Each time you select another query is being executed against the Open Data Lakehouse database tables - shows the performance of Apache Iceberg

  - From these filters (prompt selections) you gain considerable insights - look at the “Planned Layovers Greater than 90 Minutes by Carrier” visual and the answer to the question seems clear as to “Which Carriers should we partner?”.

![](images/13.png)

- From this you can see what Airlines (Carriers) that we could partner with due to Long Planned Layovers and see that Delta Airlines (DL) & Atlantic Southeast (EV) have combined planned layovers  for over 95% of Passengers with Planned Layovers of over 90 minutes

<!---->

- What if I wanted to see the flight details from a previous data load?  Click the drop-down arrow below “Time Travel” and select the middle value.  You will see the chart titled “Leg1 Flights by Year & Month”.

Before: ![](images/14.png)  

After (no 2008):![](images/15.png)

- You’ll see that after you make the selection, you should see the stacked bar for year 2008 is removed from the visual.  Meaning this data was not yet loaded at the selected point in time.
- You’ve just performed your first **_Time Travel_** without even knowing.  Time Travel is a key feature of Apache Iceberg.

<!---->

- Please go on to the next lab but feel free if you have time to leave this tab open and come back to explore more if you have time after completing the remaining labs.

  - You could do something like the following:

    - At the bottom of the page click on the Passenger List page - now that we’ve filtered the data to a specific target set of Passengers that can be sent an offer, I’d like to take a look at the list of passengers who would be sent an offer.

      - Filter the list of passengers based on Layover Type - select the drop-down under “Elongated Layover Type” and select “Missed Connection”

      - Click on the checkbox next to “Exclude Selected”.  This will exclude those passengers who have missed their connection.  

        - For the Duty Free owner, this may not be a good target, so you might want to exclude them from the offer.  However, for partnering with the Airline, this might be something we could use to improve customer satisfaction for these 24 passengers and auto rebook these passengers for instance.

***


## Lab 2 - Business Analyst: Self Service (in CDW)

In this Lab you will take advantage of the Self Service capabilities within CDW to upload a data file and combine it with an existing Data Lakehouse.  You will then perform analytics (SQL & Visualizations) on the combined data to ensure that the burning business questions can first be answered before “productionalizing” the new data source.

4. Navigate back to CDW Overview

   - Click on the browser tab where CDW is open - ![](images/16.png)
   - Click on Overview in the left navigation

![](images/17.png)

5. The following is a quick explanation of the CDW User Experience so that you have a basic knowledge of the data service.  The CDW Data Service allows you to create independent, self-service data warehouses and data marts that autoscale up and down to meet your varying workload demands. It provides isolated compute instances for each data warehouse/mart, has built-in automatic optimization, and ultimately enables you to meet SLAs - at the same time save costs.

![](images/18.png)

- There are 2 areas on this screen - Database Catalogs (DBC), and Virtual Warehouses (VW), for today’s lab, we will just concentrate on Virtual Warehouses or VW for short

  - Database Catalogs (DBC) - is a logical collection of table and view metadata, security permissions, and other information.  As you create databases, tables, views, etc. in the Data Warehouse, it collects the metadata.  When you activate an Environment for CDW, the CDW service will automatically create a default DBC associated with this Environment.

    - DBCs are in the middle column

![](images/19.png)

- Virtual Warehouses (VW) - is a set of compute resources running in Kubernetes to execute the queries.  This is something that can allow for Self Service capabilities or can be controlled by Administrators.  A VW binds compute and storage to execute secured queries that access tables and views of your data via the DBC.  A VW can scale automatically to ensure performance even with high concurrency, and can auto-scale down in situations of low demand.  Tools that access data via JDBC/ODBC can connect to VWs to run queries

![](images/20.png)

- See options available for a VW - click on the ![](images/21.png) button on the top right corner of tile airlines-hive-vw-# 

![](images/22.png)

The list of options will vary slightly depending on whether this is a Hive or Impala VW.  This is also where you would go to get the JDBC URL and Driver to use to connect your Business Intelligence software to this VW, and when a new version is released you could Upgrade this VW to the latest release without having to upgrade all VWs at the same time. 

- **_Click on the airlines-hive-vw-# tile_** -  this will highlight the Environment and DBCs that are associated with this VW.  In fact when you click on any tile within any column, it will do the same thing by showing you what it is related to, for easy understanding of the interdependence of these items.

  - These tiles will display information about current workload on a VW.  Below you will see items indicating when a VW is idle and has auto scaled so nothing is running for this VW; and where the VW needed to auto-scale up to handle incoming SQL requests handling concurrency

![](images/23.png)

- **_Click on the airlines-hive-vw-# tile_** - In the upper right corner click on the HUE button to enter into the SQL Editor

![](images/24.png)

6. Explore the Data Lakehouse

   - You will be using HUE for the **_airlines-hive-vw-# Virtual Warehouse_** until you get to Step 13

![](images/25.png)

- Copy & paste the following SQL into the query Editor window

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| -- Run prior to importing Passenger Tickets; to ensure correct access and that everything is good to go-- Query to find all international flights: flights where destination airport country is not the same as origin airport countrySELECT DISTINCT    flightnum,    uniquecarrier,    origin,    dest,    month,    dayofmonth,    \`dayofweek\`FROM    airlines.flights f    JOIN airlines.airports oa ON f.origin = oa.iata   JOIN airlines.airports da ON oa.country <> da.countryWHERE f.dest = da.iata ORDER BY   month ASC, dayofmonth ASC  ; |

![](images/25.png)

- Click on the ![](images/27.png)to the bottom left of the SQL window to run this SQL command to test and ensure you have access to the Data Lakehouse

  - You should see the something similar to the following in the Results tab

![](images/28.png)

- This validates that you have the correct permissions via the SDX security to access the Data Lakehouse

7. Upload Passenger Ticket data file - **_already completed_** for you and shown as part of the main presentation

   - If you’d like to give it a try this can be found in the Post Lab section - work with your Breakout Room moderator to set up time.
   - Below are some images that highlight the 3 steps to upload this file: 1) Open the Importer, 2) Pick a file & options for the file upload, 3) Name the table, specify table options, and provide the table metadata (column names, data types, etc.)

1\) ![](images/29.png)    2) ![](images/30.png)  

3\) ![](images/31.png)

- Since the data is already uploaded we will use the table **airlines.unique\_tickets\_1k** 

8. Explore the Data Lakehouse and Passenger Tickets (unique\_tickets) data to see if it can answer the burning questions.  The Data Analyst can use a SQL Editor to perform this task by executing queries against this data.

   - Delete the current query from the SQL Window
   - Copy & paste the following SQL into the SQL Editor window

<!---->

    -- Run after Uploading the Passenger Tickets data to see if we can answer the "burning questions" to support Duty Free Stores

    -- Number of passengers on the airline that have long, planned layovers for a flight (good target to send promotion to)

    SELECT 

       a.leg1uniquecarrier as carrier, 

       count(a.leg1uniquecarrier) as passengers

    FROM 

       airlines.unique_tickets_1k a

    where 

       a.leg2deptime - a.leg1arrtime > 90

    group by 

       a.leg1uniquecarrier

    ;

- Execute the Query by clicking on the ![](images/27.png) button

  - Review the output to see the number of passenger with a long planned layover (> 90 minutes) by Airline Carrier - one of the questions we wanted to answer

![](images/33.png)

- Delete the current query from the SQL Window
- Copy & paste the following SQL into the SQL Editor window

<!---->

    -- Number of passengers on airlines that have elongated layovers for a flight caused by delayed connection (potential customer satisfaction issue)

    SELECT 

       a.leg1uniquecarrier as carrier, 

       count(a.leg1uniquecarrier) as passengers 

    FROM 

       airlines.unique_tickets_1k a

       JOIN airlines.flights o

         ON a.leg1flightnum = o.flightnum

            AND a.leg1uniquecarrier = o.uniquecarrier 

            AND a.leg1origin = o.origin 

            AND a.leg1dest = o.dest 

            AND a.leg1month = o.month 

            AND a.leg1dayofmonth = o.dayofmonth

            AND a.leg1dayofweek = o.`dayofweek`

       JOIN airlines.flights d

         ON a.leg2flightnum = d.flightnum

            AND a.leg2uniquecarrier = d.uniquecarrier 

            AND a.leg2origin = d.origin 

            AND a.leg2dest = d.dest 

            AND a.leg2month = d.month 

            AND a.leg2dayofmonth = d.dayofmonth

            AND a.leg2dayofweek = d.`dayofweek` 

    WHERE o.depdelay > 60

    group by 

       a.leg1uniquecarrier

    ;

- Execute the Query by clicking on the ![](images/27.png) button

  - Review the output to see that we can answer another burning question

![](images/35.png)

- Note: this query combines both Hive table format (unique\_tickets\_1k) with Iceberg table format (flights).  Allows you to migrate to Iceberg over time

<!---->

- Now that we’ve validated that we can answer the business questions, it’s time to visualize the data to see the insights we can gain from combining this data

9. Visualize the Data Lakehouse and Passenger Ticket data to gain insights and communicate what we are trying to accomplish with the Admin team.

   - Click on the browser tab where CDV is open - ![](images/36.png)

   - To create visualization in Cloudera Data Visualization (CDV), the Business Analyst would have to do the following:

     - Create a Dataset (aka: Metadata Layer or Data Model) that will join the uploaded Passenger Tickets (unique\_tickets\_1k) table with the existing Data Lakehouse tables
     - Create Visualizations create visuals that present information so that users can gain insights to make better decisions.  A single Dashboard can have any number of visuals on it.
     - Make the Visualization available to the appropriate stakeholders - by default Dashboards will first be created and edited in the user’s “Private” Workspace.  Once the Dashboard is ready, it is move to a Workspace that the appropriate users can view and interact with the Dashboard(s)

   - Create a Dataset (Metadata Layer)

     - The first step is to create a Metadata layer that joins the Data Lakehouse tables and Passenger Tickets table (unique\_tickets\_1k).  To do this we’ll create what we call a Dataset.
     - On the top banner click on the DATA tab

![](images/37.png)

- Make sure the “Airlines Open Data Lakehouse” connection on the left navigation menu is selected

![](images/38.png)

- For today’s labs we’ll fast forward to a Dataset that has already been created to save time. 

  - **_If you’d like to go through this process, please work with your Breakout Room Moderator to schedule time to walk through the Lab in the Optional Lab section_**

- Click on “Lab 2 Self Service Open Data Lakehouse” to open the Dataset that was already created

![](images/39.png)

- Dataset Detail page - provides information about this Metadata Model, such as the connection, tables referenced, option settings, and date information (created/updated).  Where you see the pencil icon, indicates that you can make changes.

![](images/40.png)

- Clone Dataset - click the CLONE DATASET button at the top of the page

![](images/41.png)

- Click the ![](images/42.png)to the right of Dataset to Rename this Dataset

![](images/43.png)

- Replace the “Clone of” with “**\<user-id>**“ (use your user id in place of \<user-id>)

![](images/44.png)

- Click the SAVE button
- You now have created your own copy of the Dataset that can now be modified for today’s lab

<!---->

- Data Model - click on Data Model in the left navigation menu to what tables are in this Dataset

![](images/45.png)

Shows the tables, and relationships between tables in this Dataset

![](images/46.png)

Tables are dark gray and relationships (joins) are identified by the blue ![](images/47.png)

- In this Data Model you can see that the unique\_tickets table has already been joined to several other tables that are part of the Data Lakehouse (airports, airlines, flights, etc), but there is one more relationship that needs to be defined for this to be complete - we need to get the Leg2 Airline Carrier details

<!---->

- Click the EDIT DATA MODEL button at the top of this page

![](images/48.png)

- Click the “+” in the gray oval to the right of unique\_tickets - to add a table join
- Click the drop down below Database Name and select “airlines”
- Click the drop down below Table Name and select the “airlines” table

![](images/49.png)

- Click on the SELECT button to add this table

<!---->

- You will be presented with the Edit Join definition window (if not click the![](images/47.png)button between unique\_tickets & airlines\_1)

![](images/51.png)

- Click the drop down below airlines.unique\_tickets and select leg2uniquecarrier
- Click the drop down below airlines\_1 and select code

![](images/52.png)

- Click the APPLY button

<!---->

- This will create a join between the unique\_tickets table and the airlines table in your user database.

![](images/53.png)

- To view or edit the join that was created click on ![](images/47.png) between unique\_tickets and airlines (at the bottom) Source/Target column 

![](images/55.png)

This will show the join type and allow you to make changes.  You can see by default it created a Left outer join which you can change by selecting any of the other types such as Inner, Outer, or Right.  This Join is exactly what we need, so no need to make any changes

![](images/56.png)

- Click on the SHOW DATA button to see a preview of the data - this will run a query to combine the data from our Data Lakehouse with the data we uploaded to make sure that the data looks good.  Scroll to the right to look at all of the data from each table, and scroll down to see more data

![](images/57.png)

- At the top of the page click the SAVE button

<!---->

- Fields - on the left navigation menu select Fields

![](images/58.png)

- Click the EDIT FIELDS button at the top of the page

![](images/59.png)

- Under Dimensions - scroll down to the airlines\_1 header

![](images/60.png)

This is what was added from adding the airlines.airlines table to this Dataset.  From here we can apply business rules and context to this Dataset.

- Rename a Field - Description to Leg2 Airline Carrier

  - Click on the ![](images/61.png)button to the right of Description

![](images/62.png)

- In the Display Name text box change this to Leg2 Airline Carrier

![](images/63.png)

- Click the APPLY button

<!---->

- Hide a Field

  - The airlines\_1 code is the same values as the leg2uniquecarrier field, so no need to have this twice
  - Click the ![](images/64.png) and select Hide

![](images/65.png)

- Select Hide
- The airlines\_1 section should look like this

![](images/66.png)

- Click the SAVE button at the top of the page

  - There is so much more you can do with a Dataset, including adding calculated fields, assigning default aggregations, apply formatting, and strong data types to help with building visualizations quickly.

<!---->

- Create a Dashboard - click the NEW DASHBOARD button in the top right corner

![](images/67.png)

- This will automatically build a default visual for you like this

![](images/68.png)

- Let’s change this to answer one of the burning questions - which airline carrier should we partner with

  - Toward the right of the screen under VISUALS and select the Pie Chart visual (3rd row in the middle)

![](images/69.png)

- Under VISUALS click on the box under Dimensions - this is called a Shelf.  To add items to a Shelf you can drag and drop or in this case select it from the far right of the screen from the Dataset we just created

  - On the far right of the screen under DATA click on Leg1 Unique Carrier

![](images/70.png)

- This will add this to the Dimension Shelf

![](images/71.png)

- On the far right of the screen, drag & drop Record Count from under DATA > Measures > unique\_tickets to the box below Measures

![](images/72.png)

- It should look like the following screen.  This will combine data from the unique\_tickets table (file upload) and the existing Data Lakehouse to display the number of passengers by each Airline

![](images/73.png)

- Click the REFRESH VISUAL button

<!---->

- On the left of the screen the visual is updated to this

![](images/74.png)

- Add a title to the chart by clicking on “enter title…” above the chart.  Change it to “Airlines to Partner” and press enter

![](images/75.png)

- Add a title (name) for the Dashboard - at the top of the visualization click on “enter title…”

![](images/76.png)

- Type in “**\<user-id>** Self Service Dashboard“ (replace \<user-id> with your user id) and press enter

![](images/77.png)

- Press the SAVE button at the top of the Dashboard - you have now created a Dashboard combining the uploaded data and the existing Data Lakehouse
- Click on the VISUALS tab at the top of the page

![](images/78.png)

- On the right of the screen make sure you have Private selected to see the Dashboard you just created

![](images/79.png)

**_\[OPTIONAL]_**

- Add another Visual to the Dashboard you just created  using Natural Language Search

  - Instead of having to create a visual manually let’s take a look at another way to add visuals.  Using Natural Language Search to create visuals and then add them to Dashboards eliminates the step to manually configure a visual and allows users to do this in a much more simplified way
  - Click on the SEARCH button in the top right corner of the banner

![](images/80.png)

- For this I’d like to see which Airports have the highest number of flights this year and I’m interested in the visual being displayed on a Map of some sorts.  For this let’s

  - In the Search box start entering - Flights by “Origin Lat” and “Origin Lon”

![](images/81.png)

- You’ll see below will show some helpful details to help with finishing your search.  Under Flights select the entry - Flights by “Origin Lat” and “Origin Lon” as Interactive Map this year

![](images/82.png)

This visualization shows what was asked for.  From here you can continue to change what is displayed, Bookmark it to share or return to, or just continue on.

- This is displaying what I was interested in and this would be a good addition to the Dashboard.
- In the top right corner of the visual - click on the![](images/83.png)button and select Add to Dashboard 

![](images/84.png)

- Click on “**\<user-id>** Lab 2 Self Service Open Data Lakehouse” to expand this section (for \<user-id> look for your user id)

![](images/85.png)

- Click on the Dashboard you previously created

![](images/86.png)

- You should get a message indicating that this visualization was added to your dashboard

<!---->

- Click on the CLOSE button in the bottom right corner of the Search window

<!---->

- Now let’s view the updated Dashboard 

  - Click on the “\<user-id> Self Service Dashboard” tile

![](images/87.png)

- You should now see the following - we just now asked a question and created a Dashboard from it

![](images/88.png)

***


## Lab 3 - Administrator: “Productionalize” the Open Data Lakehouse 

In this Lab you will be an Administrator and will use CDW to create and build an Open Data Lakehouse and take advantage of some of the key features with this approach.

Execute the following SQL/DDL/DML statements.

10. Stay in HUE for the CDW **Hive** Virtual Warehouse - **airlines-hive-vw-#**

    - There should be an open CDW Browser tab, open the ![](images/16.png)browser tab

    - Create a user Database to store all of the tables you will create in the following lab steps

      - In the SQL Editor window create a database for the remaining lab exercises, execute the following.

        - Delete the current query from the SQL Window
        - Copy & paste the SQL below

<!---->

    CREATE DATABASE ${user_id}_airlines;

- The “${...}” notation is a hint to HUE to create a parameter.  As you copy/paste in this you will  see that HUE determined that there is a parameter that needs to be entered.
- In the “user\_id” parameter box, enter your user id (see Lab Setup section)

![](images/90.png)

- Execute the Query by clicking on the ![](images/27.png) button

<!---->

- Check to see if the Database was created

  - Delete the current query from the SQL Window
  - Copy & paste the SQL below

<!---->

    SHOW DATABASES;

- Execute the Query by clicking on the ![](images/27.png) button to see that the database was created

|                                                                                                |
| ---------------------------------------------------------------------------------------------- |
| **Results**`DATABASE_NAME``…``user001_airlines``…``<user_id>_airlines``…``user100_airlines``…` |

There may be many databases, scroll & look for the one that starts with your \<user\_id>

- Let’s simulate existing tables in our Data Lakehouse

<!---->

- Create planes table in _Hive Table Format_, stored in Parquet file format

<!---->

- Delete the current query from the SQL Window
- Copy & paste the SQL below

<!---->

    -- CREATE HIVE TABLE FORMAT STORED AS PARQUET

    drop table if exists ${user_id}_airlines.planes;

    CREATE EXTERNAL TABLE ${user_id}_airlines.planes (

      tailnum STRING, owner_type STRING, manufacturer STRING, issue_date STRING,

      model STRING, status STRING, aircraft_type STRING,  engine_type STRING, year INT 

    ) 

    STORED AS PARQUET 

    TBLPROPERTIES ('external.table.purge'='true');

    INSERT INTO ${user_id}_airlines.planes

      SELECT * FROM airlines_csv.planes_csv;

- Select all of the content in the SQL Editor
- Execute the Query by clicking on the ![](images/27.png) button

![](images/94.png)

- Switch Database to the user Database

  - On the left side of the SQL Editor, click on the < arrow next to default

![](images/95.png)

![](images/96.png)

- To the right of Databases click on the ![](images/96.png)button to refresh the list of Databases

![](images/98.png)

- Click on your \<user-id>\_airlines Database - this will allow you to track what has been created in your database through the next steps

![](images/99.png)

- Delete the current query from the SQL Window
- Copy & paste the SQL below

<!---->

    DESCRIBE FORMATTED ${user_id}_airlines.planes;

- Execute the Query by clicking on the ![](images/27.png) button

  - In the output look for the following fields - scroll down to look for the following properties: Location, Table Type, and SerDe Library (this value should reflect the ParquetHiveSerDe, indicating this is a Hive Table Format)

![](images/101.png)

11. Build the Data Lakehouse

    - Stay in HUE for the CDW Hive Virtual Warehouse - airlines-hive-vw.

    - Migrating Hive Table Format to Iceberg Table format - If you already have created a Data Warehouse using the Hive Table Format, but would like to take advantage of the features offered in the Iceberg Table Format, you have two (2) options: 1) Utilize the in-place table Migration feature; or 2) Use Create Table as Select (CTAS)

      - Option 1: Migrate the planes table in our Data Lakehouse from Hive Table Format to Iceberg Table Format using the Migration Utility.

        - Delete the current query from the SQL Window
        - Copy & paste the SQL below

<!---->

    ALTER TABLE ${user_id}_airlines.planes

    SET TBLPROPERTIES ('storage_handler'='org.apache.iceberg.mr.hive.HiveIcebergStorageHandler');

    DESCRIBE FORMATTED ${user_id}_airlines.planes;

- Select all of the content in the SQL Editor

- Execute the Query by clicking on the ![](images/27.png) button

- This migration to Iceberg happened in-place, there was **no** rewriting of data that occurred as part of this process.  It retained the File Format of Parquet for the Iceberg table as well.  There was a Metadata file that is created, which you can see when you run the DESCRIBE FORMATTED.

- In the output look for the following fields - scroll down to look for the following properties: look for the following (see image with highlighted fields) key values: Table Type, Location (location of where table data is stored), SerDe Library, and in Table Parameters look for properties MIGRATE\_TO\_ICEBERG, storage\_handler, metadata\_location, and table\_type

  - Location - Data is stored in cloud storage in this case S3 in the same location as the Hive Table Format
  - Metadata\_location - Since there is no need to regenerate data files with in-place table migration, you save time generating Iceberg tables. Only metadata is regenerated, which points to source data files.  Removes Hive Metastore as bottleneck.
  - Table\_type - indicates “ICEBERG” table format
  - Storage\_handler & SerDe Library - indicate what Serializer/Desearializer to use when reading/writing data in this case the “HiveIcebergSerDe”

![](images/103.png)

- Option 2: Create airports table in _Iceberg Table Format_, using Create Table As Select (CTAS).  Notice the syntax to create an Iceberg Table within Hive is “**_Stored by Iceberg_**”

  - Delete the current query from the SQL Window

<!---->

- Copy & paste the SQL below

<!---->

    drop table if exists ${user_id}_airlines.airports;

    CREATE EXTERNAL TABLE ${user_id}_airlines.airports

    STORED BY ICEBERG AS

      SELECT * FROM airlines_csv.airports_csv;

    DESCRIBE FORMATTED ${user_id}_airlines.airports;

- Select all of the content in the SQL Editor

- Execute the Query by clicking on the ![](images/27.png) button

  - In the output - look for the following key values (just like previously): Table Type, Location (location of where table data is stored), SerDe Library, and in Table Parameters look for properties MIGRATE\_TO\_ICEBERG, storage\_handler, metadata\_location, and table\_type
  - On the left you should see the airports table added to the list of Tables for your user Database

<!---->

- Slowly changing dimension table airlines

  - Iceberg is fully ACID compliant and can execute Insert, Update, Delete, and Merge Into statements
  - Delete the current query from the SQL Window
  - Copy & paste the SQL below

<!---->

    -- SLOWLY CHANGING DIMENSION TABLE USE ACID CAPABILTIES OF ICEBERG

    drop table if exists ${user_id}_airlines.airlines;

    CREATE EXTERNAL TABLE ${user_id}_airlines.airlines (

    code string, 

    description string

    ) 

     STORED BY ICEBERG 

     STORED AS PARQUET

     tblproperties('format-version'='2');

    -- LOAD DATA

    INSERT INTO ${user_id}_airlines.airlines

     SELECT * FROM airlines_csv.airlines_csv;

    -- Check data to see a few records

    SELECT * 

    FROM ${user_id}_airlines.airlines

    WHERE code IN ("04Q", "05Q");

- Select all of the content in the SQL Editor

- Execute the Query by clicking on the ![](images/27.png) button

  - This will create the Iceberg Table, load initial data, and display a few rows that will be modified in the next step

- Delete the current query from the SQL Window

<!---->

- Copy & paste the SQL below

<!---->

    -- SLOWLY CHANGING DIMENSION TABLE USE ACID CAPABILITIES OF ICEBERG

    MERGE INTO ${user_id}_airlines.airlines AS t

      USING airlines_csv.airlines_csv s ON t.code = s.code

    WHEN MATCHED AND t.code = "04Q" THEN DELETE

    WHEN MATCHED AND t.code = "05Q" THEN UPDATE SET description = "Comlux Aviation"

    WHEN NOT MATCHED THEN INSERT VALUES (s.code, s.description);

    -- Check data to see records were deleted or updated

    SELECT * 

    FROM ${user_id}_airlines.airlines

    WHERE code IN ("04Q", "05Q");

- Select all of the content in the SQL Editor

- Execute the Query by clicking on the ![](images/27.png) button

  - The Merge Into statement will check to see if a record needs to be Deleted (when the record key matches and the code = 04Q), when a new record needs to be Inserted (key doesn’t match), and when an Update is needed (when the key matches and the code = 05Q
  - Compare the output to see that only one record is returned with the description set to “Comlux Aviation”

<!---->

- Creating an Iceberg Table - for this step create a partitioned table, in Iceberg Table Format, stored in Parquet File Format.  Optionally, you could specify other File Formats, the supported formats for Iceberg are: Parquet, ORC, and Avro. 

  - Delete the current query from the SQL Window
  - Copy & paste the SQL below

<!---->

    drop table if exists ${user_id}_airlines.flights;

    CREATE EXTERNAL TABLE ${user_id}_airlines.flights (

     month int, dayofmonth int, 

     dayofweek int, deptime int, crsdeptime int, arrtime int, 

     crsarrtime int, uniquecarrier string, flightnum int, tailnum string, 

     actualelapsedtime int, crselapsedtime int, airtime int, arrdelay int, 

     depdelay int, origin string, dest string, distance int, taxiin int, 

     taxiout int, cancelled int, cancellationcode string, diverted string, 

     carrierdelay int, weatherdelay int, nasdelay int, securitydelay int, 

     lateaircraftdelay int

    ) 

    PARTITIONED BY (year int)

    STORED BY ICEBERG 

    STORED AS PARQUET

    tblproperties ('format-version'='2');

    SHOW CREATE TABLE ${user_id}_airlines.flights;

- Select all of the content in the SQL Editor
- Execute the Query by clicking on the ![](images/27.png) button

<!---->

- Looking at the SHOW CREATE TABLE output, scroll down and notice the output is the unformatted version of the Describe Formatted as we would expect.  The main item to pay attention to here is the PARTITIONED BY SPEC, currently we’ve partitioned by just the “year” column

![](images/108.png)

- When we insert data into this table it will write data together within the same partition (ie. all 2006 data is written to the same location, all 2005 data is written to the same location, etc.)

  - Delete the current query from the SQL Window
  - Copy & paste the SQL below

<!---->

    INSERT INTO ${user_id}_airlines.flights

     SELECT * FROM airlines_csv.flights_csv

     WHERE year <= 2006;

    SELECT year, count(*) 

    FROM ${user_id}_airlines.flights

    GROUP BY year

    ORDER BY year desc;

- Select all of the content in the SQL Editor

- Execute the Query by clicking on the ![](images/27.png) button

  - The Insert will insert data from years 1995 to 2006
  - Notice that each of the years have a range of data within a few million flights (each record in the flights table counts as a flight)

![](images/110.png)    ![](images/110.png)

12. Performance improvements 

    - Check that you created the tables for the Data Lakehouse - on the list of tables to the left of the Editor window you should see the following tables

![](images/112.png)

- Iceberg in-place Partition Evolution \[Performance Optimization]

  - One of the key features for Iceberg tables is the ability to evolve the partition that is being used over time

    - Delete the current query from the SQL Window
    - Copy & paste the SQL below

<!---->

    ALTER TABLE ${user_id}_airlines.flights

    SET PARTITION spec ( year, month );

    SHOW CREATE TABLE ${user_id}_airlines.flights;

- Select all of the content in the SQL Editor

- Execute the Query by clicking on the ![](images/27.png) button

  - This was an in-place Partition Evolution, meaning that the existing data is not rewritten as part of the ALTER TABLE execution.  What will happen is the next data that is loaded will use the new Partition definition.
  - In the output scroll to see the PARTITIONED BY SPEC to see that it is now both year and month\
    ![](images/114.png)

13. Performance Improvements - Open HUE for the CDW **Impala** Virtual Warehouse - airlines-impala-vw.  

    - There should be an open CDW Browser tab, open the ![](images/16.png)browser tab

    - Click on the airlines-impala-vw-# tile

      - In the upper right corner click on the HUE button to enter into the SQL Editor

![](images/116.png)

- Load new data into the flights table using the NEW partition definition - this will load new data to take advantage of the new partition specification.  This also shows how Iceberg also supports multiple engines by allowing both Hive & Impala to create, load, query, and or modify Iceberg tables.
- Copy & Paste the following in the SQL Editor window

<!---->

    INSERT INTO ${user_id}_airlines.flights 

    SELECT * FROM airlines_csv.flights_csv 

    WHERE year = 2007;

- Execute the Query by clicking on the ![](images/27.png) button

- Run Explain Plans against some typical analytic queries we might run to see what happens with this new Partition definition.

  - In Impala we are in another engine which is another key feature of Iceberg - multi-function (or multiple engine) analytics.  No need to copy the data or do more work to allow access to the same data.
  - Copy/paste the following in the Editor, but do not execute the query

<!---->

    SELECT year, month, count(*) 

    FROM ${user_id}_airlines.flights

    WHERE year = 2006 AND month = 12

    GROUP BY year, month

    ORDER BY year desc, month asc;

- In the “user\_id” parameter box, enter your user id (see Lab Setup section)

![](images/90.png)

- Instead select (highlight) the statement click the ![](images/119.png) button, which is right below the Execute (![](images/27.png)) button and select Explain

![](images/119.png)

- In the output notice the amount of data that needs to be scanned for this query (it would represent the volume of 1 years worth of data - about 139MB).  Up to this point the data was loaded using the Partition of just a year.

![](images/122.png)

- Copy/paste the following in the Editor, but do not execute the query

<!---->

    SELECT year, month, count(*) 

    FROM ${user_id}_airlines.flights

    WHERE year = 2007 AND month = 12

    GROUP BY year, month

    ORDER BY year desc, month asc;

- Instead select (highlight) the statement click the ![](images/119.png)button, which is right below the Execute (![](images/27.png)) button and select Explain

<!---->

- In the output notice the amount of data that needs to be scanned for this query, about 10MB, is significantly less than that of the first, 138MB.  This shows an important capability, Partition Pruning.  Meaning that much less data is being scanned for this query and only the selected month of data is being scanned vs scanning the entire year of data.  This should result in much faster query execution times.

![](images/125.png)

- Iceberg Snapshots Time Travel - in the previous steps we have been loading data into the flights Iceberg table. 

  - Each time data was changed in our Iceberg tables, a Snapshot is automatically captured.  This is important for many reasons but the main point of the Snapshot is to ensure eventual consistency and allow for multiple reads/writes concurrently (from various engines or the same engine).

  - Show snapshots

    - Delete the current query from the SQL Window
    - Copy & paste the SQL below

<!---->

    DESCRIBE HISTORY ${user_id}_airlines.flights;

- Execute the Query by clicking on the ![](images/27.png) button

In the output there should be 2 Snapshots, in the example below there are 3 snapshots as this example shows that data was also loaded vie Impala and not just Hive.  Also, keep in mind we have been reading/writing data from/to the Iceberg table from both Hive & Impala which is indicated by the () in the callouts below.  This is important aspect of Iceberg Tables is that they support multi-function analytics - ie. many engines can work with Iceberg tables (Cloudera Data Warehouse \[Hive & Impala], Cloudera Data Engineering \[Spark], Cloudera Machine Learning \[Spark], Cloudera DataFlow \[NiFi], and DataHub Clusters)

![](images/127.png)

- Get Details for Snapshots - open a text editor/notepad

![](images/128.png)

Text Editor - copy in a couple creation\_time’s and snapshot\_id’s

![](images/129.png)

- Iceberg Time Travel \[Table Maintenance] - copy/paste the following data into the Impala Editor, but do not execute.  

  - Delete the current query from the SQL Window
  - Copy & paste the SQL below

<!---->

    -- SELECT DATA USING TIMESTAMP FOR SNAPSHOT

    SELECT year, count(*) 

    FROM ${user_id}_airlines.flights

      FOR SYSTEM_TIME AS OF '${create_ts}'

    GROUP BY year

    ORDER BY year desc;

    -- SELECT DATA USING TIMESTAMP FOR SNAPSHOT

    SELECT year, count(*) 

    FROM ${user_id}_airlines.flights

      FOR SYSTEM_VERSION AS OF ${snapshot_id}

    GROUP BY year

    ORDER BY year desc;

- Once you copy this SQL into the Editor you will see 2 new parameters - create\_ts and snapshot\_id

![](images/130.png)

- The first SELECT statement will use the create\_ts

  - In the create\_ts parameter box enter a date/time (this can be relative or specific timestamp).  From your Text Editor copy the second entry under creation\_time, paste it into the create\_ts parameter.  For this Time Travel you can use relative time periods and don’t have to enter the specific timestamp for the Snapshot.
  - Highlight the first SELECT statement, and execute it

![](images/131.png)   ![](images/131.png)

- This returned the the data as it was in our initial load 

<!---->

- The second SELECT statement will use the snapshot\_id

  - From your Text Editor copy the second entry under snapshot\_id, paste it into the snapshot\_id parameter box

    - Highlight the second SELECT statement, and execute it

![](images/133.png)    ![](images/133.png)

- This returns the data for the specific Snapshot ID that was specified in the query which was the data for the initial insert for data up to year 2006 and the insert for data for year 2007

<!---->

- Security & Governance - Now that performance has been optimized, we are almost ready to release this to the users.  Before we do that we need to apply security - Security is always on and can be defined with fine grained access control.  **_To learn more about Security & Governance in CDP - work with your Breakout Room Moderator to schedule time to go thru the Optional Lab at the end of this document_**

  - A security policy has already been created.  This is how it is defined

![](images/135.png)

![](images/136.png)

- Delete the current query from the SQL Window
- Copy & paste the SQL below Select all of the content in the SQL Editor
- Execute the Query by clicking on the![](images/27.png)button

![](images/138.png)

- You will see that the “tailnum” column is masked so you are unable to see the actual plane’s tail number, instead you see the Hashed value of the tailnum

***


## (Optional Bonus Material)

## Optional Lab 1 - CDW Tour

In this Lab you will explore how to take advantage of CDW.

14. Click on the “Get Started with a Tour” at the top of the CDP Home screen

![](images/2.png)

15. \[Optional] Watch the “Test Drive” Video on the CDP Home screen (video is \~3 minutes)

![](images/140.png)

16. Click on the “Let’s go” button at the bottom of the video, you can take tours of any of the Data Services
17. Click on the Data Warehouse tour tile

![](images/141.png)

- Here you see the content you can take advantage of - there are 3 tiles where you can watch videos on an area of interest, you will see a “> Video” link on the tile if this is a video, and there is also a tour.

![](images/142.png)

- Click on the “Data Warehouse Overview” tile, this is a click through tour of CDW

  - Perform all of the actions for this click through tour (\~5 minutes)
  - Once completed click on the “X” in the top right corner to close the window 

18. On the Product Tours screen, explore the various topics to learn mover about Cloudera Data Warehouse

***


## Optional Lab 2 - Self Service File Upload

In this lab you will learn how to upload a small file to run SQL queries against where you could join to existing data in your Data Lakehouse.

19. Upload Passenger Ticket data file

    - Below highlights the 3 steps to upload this file: 1) Open the Importer, 2) Pick a file & options for the file upload, 3) Name the table, specify table options, and table metadata (column names, data types, etc.)

1\) ![](images/29.png)    2) ![](images/30.png)  3) ![](images/31.png)

- On the left navigation menu click the ![](images/146.png) button, and select Importer

![](images/29.png)

- On the “Pick Data from Local File” page

  - In the Select Type, choose “Small Local File”, it should be the default value

![](images/148.png)

- Click the![](images/149.png)button, and browse to the “passengertickets\_1k.csv” file

![](images/30.png)

Ensure that the PREVIEW looks good.  You could make changes to the CSV options or import other file types like JSON using this Importer

- Click the ![](images/151.png) button

<!---->

- On the “Move it to table \<table-name>” page

  - Under DESTINATION, change Name to **\<user-id>**\_airlines.unique\_tickets (replace \<user-id> with your user id you logged in with)

![](images/31.png)

- Under FIELDS, change data types with “bigint” to “int” for all the fields except the “ticketnumber” field, it can remain a bigint data type

![](images/153.png)

- The final fields section should look like the following:

![](images/154.png)

- Click the![](images/155.png) button - this will create a new table in your database named unique\_tickets in a Hive table format.  Later in the labs you will learn how to migrate this to an Iceberg table.  You will be taken to the Table Browser and see a status like the following screen (top right):

![](images/156.png)

- Once the table is created click on the![](images/157.png)tab of the Table Browser to see the table type and other information on this table.  The following highlighted pieces of information show that this table is a Managed Table that is in using a SerDe that shows this is an ORC File Format & in Hive Table Format

![](images/158.png)

- You can also view a sample of the data in this table by clicking on the ![](images/158.png)tab

***


## Optional Lab 3 - Performance Optimizations (Impala VW)

In this Lab we will take a look at some of the performance optimization and table maintenance tasks that can be performed to ensure the best possible TCO, while ensuring the best performance.

20. Materialized Views \[Performance Optimization] - this can be used for both Iceberg tables and Hive Tables to improve performance

    - Open HUE for the CDW **Hive** Virtual Warehouse - airlines-hive-vw.  Copy/paste the following, make sure to highlight the entire block, and execute the following

<!---->

    SET hive.query.results.cache.enabled=false;

    drop table  if exists ${user_id}_airlines.airlines;

    CREATE EXTERNAL TABLE ${user_id}_airlines.airlines (code string, description string) STORED BY ICEBERG STORED AS ORC TBLPROPERTIES ('format-version' = '2');

    INSERT INTO ${user_id}_airlines.airlines SELECT * FROM ${user_id}_airlines_raw.airlines_csv;

    SELECT airlines.code AS code,  MIN(airlines.description) AS description,

              flights.month AS month,

              sum(flights.cancelled) AS cancelled

    FROM ${user_id}_airlines.flights flights , ${user_id}_airlines.airlines airlines 

    WHERE flights.uniquecarrier = airlines.code

    group by airlines.code, flights.month;

- Hive has built in performance improvements, such as a Query Cache that stores results of queries run so that similar queries don’t have to retrieve data, they can just get the results from the cache.  In this step we are turning that off using the “SET” statement, this will ensure when we look at the query plan we will not retrieve the data from the cache.
- Note: with this query you are combining an Iceberg Table Format (flight table) with a Hive Table Format (airlines\_orc table) in the same query.

![](images/160.png)

- Let’s take a look at the Query Plan that was used to execute this query

  - On the left menu select Jobs

![](images/161.png)

- This will take you to the Jobs Browser, select the Queries tab to the right of the Job Browser header 

![](images/162.png)

- This is where an Admin will go when - a query has run amok and then figures out what to do next.  In our case for this lab we’d like to look at the query we just executed to see how it ran and the steps taken to execute the query.  Administrators would also be able to perform other monitoring and maintenance tasks for what is running (or has been run).  Monitoring and maintenance tasks could include: cancel (kill) queries, see what is running, analyze whether queries that have been executed are optimized, etc.

![](images/163.png)

- Hoover over and click on the Query we just executed (it should be the first row)

![](images/164.png)

- This is where you can analyze queries at a deep level.  For this lab let’s take a look at the Explain details, click on Visual Explain tab

![](images/165.png)

- This plan shows that this query needs to Read flights (86M rows) and airlines (1.5K rows) with hash join, group and sort.  This is a lot of data processing and if we run this query constantly it would be good to reduce the time this query takes to execute.

![](images/166.png)

- Click on the \</> button on the left menu, and click Editor, to return the Editor Window

![](images/167.png)

- Create Materialized View (MV) - queries will transparently be rewritten, when possible, to use the MV instead of the base tables.  Copy/paste the following, highlight the entire block, and execute

<!---->

    DROP MATERIALIZED VIEW IF EXISTS ${user_id}_airlines.traffic_cancel_airlines;

    CREATE MATERIALIZED VIEW ${user_id}_airlines.traffic_cancel_airlines

    as SELECT airlines.code AS code,  MIN(airlines.description) AS description,

              flights.month AS month,

              sum(flights.cancelled) AS cancelled,

              count(flights.diverted) AS diverted

    FROM ${user_id}_airlines.flights flights JOIN ${user_id}_airlines.airlines airlines ON (flights.uniquecarrier = airlines.code)

    group by airlines.code, flights.month;

    -- show MV

    SHOW MATERIALIZED VIEWS in ${user_id}_airlines;

- The Materialized View traffic\_cancel\_airlines will be displayed in Results and in the left table/view list with a ![](images/168.png)(View) icon to the left of the MV

![](images/169.png)

- Run Dashboard Query again to see usage of the MV - Copy/paste the following, make sure to highlight the entire block, and execute the following.  This time an Order By was added to make this query have to do more work.

<!---->

    SET hive.query.results.cache.enabled=false;

    SELECT airlines.code AS code,  MIN(airlines.description) AS description,

              flights.month AS month,

              sum(flights.cancelled) AS cancelled

    FROM ${user_id}_airlines.flights flights , ${user_id}_airlines.airlines airlines 

    WHERE flights.uniquecarrier = airlines.code

    group by airlines.code, flights.month

    order by airlines.code;

- Let’s take a look at the Query Plan that was used to execute this query

  - On the left menu select Jobs
  - On the Jobs Browser - select the Queries tab to the right of the Job Browser header
  - Hoover over & click on the Query just executed (should be the first row)
  - Click on Visual Explain tab - With query rewrite the **materialized view** is used and the new plan just reads the MV and sorts the data vs. reading flights (86M rows) and airlines (1.5K rows) with hash join, group and sorts.  This results in significant reduction in run time for this query.

![](images/170.png)

- Materialized views also support incremental refreshes when the data from the tables used for the MVs is updated.  Please visit the CDW documentation for more information.

<!---->

- Return to Query Editor - click on the \</> button on the left menu, and click Editor, to return the Editor Window

***


## Optional Lab 4 - Data Visualization

In this lab you will build a Logistics Dashboard using Cloudera Data Visualization.  The Dashboard will include details about flight delays and cancellations.  This will be a completely new use case independent of the SMG Use Case, the analysis could be a catalyst to lead to a Data Science application to predict the probability of a flight being canceled or not.

21. Open Cloudera Data Visualization (CDV or Data Viz)

    - Go to browser tab with CDW open
    - On the left navigation panel click “Data Visualization”
    - On the row with airlines-cdv, click the Data VIZ button

![](images/171.png)

- If you see the “What’s New” page, you can read it, or click on the GOT IT button

22. Home page

![](images/172.png)

- There are 4 areas of CDV - HOME, SQL, VISUALS, DATA - these are the tabs at the top of the screen in the black bar to the right of the Cloudera Data Visualization banner

  - Home - this is the starting point; it shows some statistics at the top, followed by some quick access details to recent content - Queries, Connections, Datasets, and Dashboards
  - SQL - allows you to manually build queries against data to perform quick discovery against the data.  Below is an example of a query that was built and Run

![](images/173.png)

- Visuals - an area for viewing/building/modifying visuals, dashboards, and applications

![](images/174.png)

- Data - interface for access to datasets, connections, and the Connection Explorer

23. Build a Dataset (aka. Metadata Layer or Data Model) - click on DATA in the top banner.  A Dataset is a Semantic Layer where you can create a business view on top of the data - data is not copied; this is just a logical layer

![](images/175.png)

- Create a connection - click on the NEW CONNECTION button on the left menu

![](images/176.png)

- Connection type - select CDW Impala
- Name - **\<user\_id>**-airlines-lakehouse
- CDW Warehouse - select drop down and pick the airlines-impala-vw
- For this lab each participant will create their own connection in the same Data Viz instance, this would not be normal, you would only have to create a single connection to the same Virtual Warehouse
- Click on the Advanced tab  in the middle of the screen, you can see that the details are already populated, there is nothing more to do.  If certain settings were required you could change them here.
- Click CONNECT button, to create the Connection
- You will see your connection in the list of connections on the left menu

![](images/177.png)

- On the right side of the screen you will see Datasets and the Connection Explorer

![](images/178.png)

- Create a new Dataset (aka. Metadata Layer or Data Model)

  - Click on NEW DATASET button

![](images/179.png)

- Dataset title - **airline\_logistics**
- Dataset Source - select From Table (however, you could choose to directly enter a SQL statement instead)
- Select Database - **\<user\_id>**\_airlines
- Select Table - flights
- Click CREATE

![](images/180.png)

- Edit the Dataset - click on airline\_logistics on the right of the screen.  This will open the details page, showing you information about the Dataset, such as connection details, and options that are set

![](images/181.png)

- On the left menu click on Fields - let’s quickly see what was created by adding the flights table to the Dataset.  When this table was added it took the table’s metadata and add the columns as Fields.  (we’ll come back to this later)

![](images/182.png)     ![](images/183.png)

- Click on Data Model - for our Dataset we need to join additional data to the flights table including the planes, airlines, and airports tables
- Click on EDIT DATA MODEL button

![](images/184.png)

- Join planes - click the “+” button next to flights

![](images/185.png)

Database Name - **\<user\_id>**\_airlines

Table Name - planes

Click SELECT button

![](images/186.png)

Click the ![](images/187.png) (JOIN) between flights and planes to see the join that was created

Click EDIT JOIN to modify the join as there is an extra join of year=year

Click on the - to the right of the year=year join and click the APPLY button

![](images/188.png) should be >>> ![](images/189.png)

- Join airlines - click the “+” button next to flights

![](images/190.png)

Database Name - **\<user\_id>**\_airlines

Table Name - airlines

Click SELECT button

![](images/191.png) >>> ![](images/192.png)

Click the ![](images/187.png) (JOIN) between flights and airlines to see the join that was created

Click EDIT JOIN to modify the join

Click on uniquecarrier under flights & code under airlines and click the APPLY button

- Join airports (origin airport) - click the “+” button next to flights

![](images/194.png)

Database Name - **\<user\_id>**\_airlines

Table Name - airports

Click SELECT button

![](images/195.png)

Click the ![](images/187.png) (JOIN) between flights and airports to see the join that was created

Click EDIT JOIN to modify the join

Click on origin under flights & iata under airports and click the APPLY button

- Join airports (destination airport) - click the “+” button next to flights

![](images/197.png)

Database Name - **\<user\_id>**\_airlines

Table Name - airports

Click SELECT button

![](images/198.png)

Click the ![](images/187.png) (JOIN) between flights and airports\_1 to see the join that was created

Click EDIT JOIN to modify the join

Click on the dest under flights & iata under airports and click the APPLY button

- The final Data Model will look like the following…

![](images/200.png)

- Click on the SHOW DATA button to preview the data that will be returned by the model created so far

![](images/201.png)

- Click on the SAVE button

<!---->

- Modify Fields - click on Fields in the left menu

![](images/202.png)

- Click on the EDIT FIELDS button; you will see this new tool bar

![](images/203.png)

- Click on the TITLE CASE button to format the display names of the fields
- Under the Measures section, click on the Mes button next to month.  This changes this to a Dimension.

![](images/204.png)

- Each Field is assigned a Category (Measure or Dimension) - this is important because the type is used when creating visuals.  CDV will use the data type to determine this Category.  Make sure that Fields fall into the correct Category.  This is important because this is used when creating visuals.  The way to look at choosing the Category is to use this simple method - if you need to Aggregate (sum, average, etc.) then the Field should be a Measure.  The quickest way to change the Category is to use the toggle

<!---->

- Under the Measures section, click on the Mes button next to the following Fields:

  - Under Measures > flights

    - Dayofmonth
    - Dayofweek
    - Deptime
    - Crsdeptime
    - Arrtime
    - Crsarrtime
    - Flightnum
    - Year

  - All Fields under Measures > planes

  - All Fields under Measures > airports

  - All Fields under Measures > airports\_1

- **Note:** Normally, we would make sure that all Fields fall into the correct Category, instead let’s move ahead

- Edit a Field

  - Click the pencil next to Depdelay under the Measures section to edit the field

<!---->

- Change the Display Name to Dep Delay & change the Default Aggregation to Average

![](images/205.png)

- Click on the Display Format tab

  - Select Category of Integer and click on Use 1000 separator

![](images/206.png)

- Click APPLY button to save the changes

<!---->

- Add a new Field

  - Clone the Origin Field - click the down arrow next to Origin, select Clone

![](images/207.png)

- Click the pencil next to Clone of Origin to edit the field
- Change Display Name to Route
- Click on the Expression tab - enter the following into the Expression window

<!---->

    concat([Origin], '-', [Dest])

![](images/208.png)

- Click APPLY - since the “Save expression only after validation succeeds” is checked the Field will first be validated to ensure there are no errors then if it is valid will be saved

<!---->

- Click the SAVE button

24. Create Dashboard - in the top right corner click on the NEW DASHBOARD button

![](images/209.png)

New Dashboard

- Quick Overview the the interface

  - On the right side of the screen there will be a VISUALS menu.  At the top of this menu, there is a series of Visual Types to choose from.  There will be 30+ various visuals to choose from.  Below the Visual Types you will see what are called Shelves.  The Shelves that are present depend on the Visual Type that is selected.  Shelves with a “\*” are required, all other Shelves are optional.  On the far right of the page there is a DATA menu, which identifies the Connection & Dataset used for this visual.  Underneath that is the Fields from the Dataset broken down by Dimensions and Measures.  With each of these Categories you can see that it is subdivided by each Table in the Dataset.

|                                                                                                                                                                                                                   |                                                                                                                                                                                                              |                                                                                                                                                                                                                                                                                                                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| **Visual Types**![](images/210.png) | **Shelves**![](images/211.png) | **DATA**![](images/212.png) ![](images/213.png) |

- 1st Visual - Top 25 Routes by Avg Departure Delay; are there certain Routes with excessive Delays

  - CDV will add a Table visual displaying a sample of the data from the Dataset as the default visualization when you create a new Dashboard or new Visuals on the Dashboard (see New Dashboard screen above).  The next step is to modify (Edit) the default visualization to suit your needs.  
  - Pick the Visual Type - select the Stacked Bar chart visual

![](images/214.png)

- Edit the Shelves (two (2) ways to add items to a Shelf, you will use both here; for the remainder of this lab you can pick & choose which you use)

![](images/215.png)

![](images/216.png)

- Option 1: Add Route to the X Axis

  - Click in the X Axis Shelf to select it
  - In the DATA menu find Route under Dimensions > fights

- Option 2: Add Dep Delay to the Y Axis

  - In the DATA menu find Dep Delay under Measures > flights, Drag & Drop this Field in the Y Axis Shelf

- So the two (2) options for adding items to Shelves is 1) select Shelf and click to add Field; or 2) Drag & Drop Field to Shelf

<!---->

- Modify Properties for Dep Delay - click on the > in the Y Axis Shelf to the right of avg(Dep Delay) to access the Properties for this Shelf

![](images/217.png)

- Click on the down arrow to the left of Aggregates - in CDV you have control over any behavior, in the Dataset we set the default aggregation for this Field to be Average, however, on any visual you can override this by changing it here.  For now, leave this alone.

![](images/218.png)

- Click the down arrow to the left of Order and Top K - to show the 25 Routes with the highest Average Dep Delay enter 25 into the box for “Top K”

![](images/219.png)

- Click the down arrow to the left of Alias - to change the display name for this Field.  In the box enter Avg Dep Delay

![](images/220.png)

- The finished Y Axis Shelf should look like this

![](images/221.png)

- Click the ![](images/222.png) button to update the Visual

![](images/223.png)

- Change the Title & Subtitle for this Visual

  - Click in the enter Title above the chart and enter - Routes with Highest Avg Departure Delays, hit enter
  - Click in the Subtitle and enter - In Minutes, hit enter

![](images/224.png)

-

<!---->

- Add Title & Subtitle for the Dashboard

  - Click in the enter Title right below the banner and enter - **\<user\_id>** Logistics Dashboard
  - Click in the Subtitle and enter - CDW Workshop

![](images/225.png)

- Click on the SAVE button to save this Dashboard, this Dashboard is now named **\<user\_id>** Logistics Dashboard

<!---->

- 2nd Visual - Relationship between flight Cancellation reason and Carrier; are there Carriers or Reasons that need to be addressed?

  - Click on +Visuals - on the far right of the screen you will see the DASH. menu.  This menu allows you to add new visuals and change settings for the Dashboard or Visual such as formatting, style, and anything related to the presentation of the data.

![](images/226.png)

- Under ADD VISUALS - leave the ![](images/227.png) (Connection) as \<user\_id>-airlines-lakehouse and ![](images/227.png) (Dataset) as airlines\_logistics.  However, a Dashboard can have any number of connections and Datasets for various visuals on a Dashboard.

![](images/229.png)

- This will add a default visual to the canvas
- Click on the ![](images/230.png) button, next to the Table ![](images/231.png).  Instead of manually building this visual, we will use the Visual helper

![](images/232.png)

- Select Uniquecarrier and Cancellationcode under Dimensions; select Cancelled under Measures.  As you select items from the Fields you will see the Possible Visuals change - helping you quickly select the visual based on what you have selected.

![](images/233.png)

- Click on SEE ALL VISUALS> button - to preview the Possible Visuals with actual data plotted
- Click on the Correlation flow visual - Scroll thru until you see the Correlation flow visual tile

<!---->

- Drag & Drop Cancelled from DATA menu under Measures > flights to the Filter Shelf - There are several ways to apply filters to visuals within the Dashboard, this is one

  - When the dialog box comes up

![](images/234.png)

- This will filter this chart to only return flights that have been cancelled, and will not return any other data
- Click the REFRESH VISUAL button

![](images/235.png)

- **NOTICE**: Since there is a security policy still in effect, you will only see “UA” showing up in this visual.  To see all of the Carriers, you could disable the security Policy and Refresh the Visual.

<!---->

- Click ![](images/236.png)in the bottom right corner of the Correlation flow visual and drag it down to resize this chart (make it a bit larger to your liking)

![](images/237.png)

- Click the enter Title and enter Cancellation Correlation, and hit enter
- Click the SAVE button to save the Dashboard

<!---->

- Add prompts - allow dashboard to be sliced & diced; this is another way to filter on multiple charts at the same time in your Dashboard

  - On the DASH. menu (far right) click on +Filters button

![](images/238.png)

- Click on Engine Type under Dimensions > planes, to add this Field as a filter; you continue to select other Fields that you want to create Filters for and these will also be added

![](images/227.png)

- Click the drop down arrow next to Engine Type and select any value - the filter(s) are added to the Filter shelf for the Dashboard which is between the Dashboard Title and the Visuals you have been creating.  When you are selecting values from this Filter, the visuals will change to reflect information for just flights where this Engine Type was in the plane for the flight

![](images/240.png)

![](images/241.png)

- Click the SAVE button to save the Dashboard

<!---->

- \[optional] View Dashboard from Visuals page

  - Click Visuals in the top banner
  - Dashboards can be shared with other users - use Workspaces to organize and secure content that is created
  - Create Applications - combine multiple Dashboards to produce an application that allows users to make better decisions

-

***


## Optional Lab 5 - Data Security & Governance 

In this lab you will experience the combination of what the Data Warehouse and the Shared Data Experience (SDX) offers.  SDX enables you to provide Security and Governance tooling to ensure that you will be able to manage what is in the CDP Platform without having to stitch together multiple tools.

Robust Data Catalog (Governance) capability that:

- Enables you to understand, manage, secure, and govern data assets across

- Provides a 360 degree view of Assets - Lineage, Metadata, Security Policy applied to the asset

  - There are many assets - everything created in CDP is captured as an Asset
  - For this Workshop we have been working with Assets, like - databases, views, tables, etc. 

Powerful Security features like:

- Rule-based masking columns based on a user’s role 
- Group association or rule-based row filters
- Attribute-Based Access Control a.k.a. Tag-based security policies

25. Data Catalog - Governance (Lineage, Metadata, etc.)

    - On the left navigation menu click the ![](images/242.png)next to Data Warehouse

![](images/242.png) ![](images/244.png)

- Right click on the Data Catalog and select “Open Link in New Tab” option

                      ![](images/245.png)

- Open browser tab that just opened, should have Data Catalog in the tab title

![](images/246.png)

- To the left, under Data Lakes, ensure the Data Lake provided in Lab Setup radio button is selected

![](images/247.png)

- Filter for Assets we created - below the Data Lakes on the left of the screen under Filters, select TYPE of Hive Table.  The right side of the screen will update to reflect this selection

![](images/248.png)

- Under DATABASE, click +Add new Value.  In the box that appears start typing your **\<user\_id>** when you see the **\<user\_id>**\_airlines database pop up select it

![](images/249.png)                          ![](images/250.png)

- You should now see the tables and materialized views that have been created in the **\<user\_id>**\_airlines database.  Click on flights in the Name column to view more details on the flights table.

![](images/251.png)

- This page shows information about the flights table such as the table owner, when the table was created, when it was last accessed, and other properties.  Below the summary details is the Overview tab which shows the lineage - hoover over the flights click on the “i” icon that appears to see more detail on this table

![](images/252.png)

- The lineage shows 

  - \[blue box] flights data file residing in an s3 folder
  - \[purple box] is showing how the flights\_csv Hive table is created, this table was created and points to the data location of flights’ (blue box) s3 folder 
  - \[orange box] is showing the flights Iceberg table and how it is created, it uses data from flights\_csv Hive table (CTAS) 
  - Traffic\_cancel\_airlines is a Materialized View that uses data from the flights Iceberg table.

![](images/253.png)

- Click on the Schema Tab to see Metadata on this table.  The Metadata includes basic information from the table such as: column names and data types for the columns.  You can also run Profilers that  come as part of CDP:

  - Hive Table Profiler - allows you to gather additional information from the table including Min/Max values in the column, # records with Null Values in a column, etc.
  - Sensitivity Profiler - identifies columns that may contain sensitive information such as PII data, SSN, credit card numbers, ID numbers, etc.  These items will be “Tagged” in the Classification column of the Schema page.

![](images/254.png)

- Click on the Policy tab to see what security policies have been applied on this table.  There are 2 policies that have been defined to allow some users & groups access via policy “all - database, table, column” and another policy “all - database, table” access.

  - The Access Audits tab allows Administrators to be able to see who, when, where, why either accessed this table or was denied access to this table.  Feel free to switch to this tab to take a look and switch back to the Policy tab.

![](images/255.png)

- Click on the ![](images/256.png) next to the “all - database, table” - to modify this policy or create a new policy

![](images/256.png)

26. Security (Ranger) - modify and create security policies for the various CDP Data Services.

    - View the Policy details and click the CANCEL button at the bottom.
    - For this portion of the Lab let’s restrict your access to a subset of data available in the “flights” table.

![](images/258.png)

- Click on the Hadoop SQL link in the upper left corner - to view the security policies in place for CDW.  For this Workshop we will stick to the CDW related security features

![](images/259.png)

- This screen shows the general Access related security policies - who has access to which Data Lakehouse databases, tables, views, etc.  Click on the “Row Level Filter” tab to see the policies to restrict access to portions of data

![](images/260.png)

- There are currently no policies defined.  Click on the Add New Policy button

![](images/261.png)

- Fill out the form as follows.  For this policy let’s say you are an Gate Agent for United Airlines and should not be able to see data for any other Airline.  To setup the policy we need to apply a filter that is applied to any query that is run for your **\<user\_id>** so you only see rows for flights run by United Airlines.

  - Policy Name: **\<user\_id>** Workshop Row Level Filter

  - Hive Database: **\<user\_id>**\_airlines (start typing, once you see this database in the list, select it)

  - Hive Table: flights (start typing, once you see this table in the list, select it)

  - Row Level Filtering Conditions

    - Select User - **\<user\_id>** (start typing, once you see this user in the list, select it)
    - Row Level Filter - **uniquecarrier="UA"**
    - For this you could have any number of filter conditions (for this Lab we will only create 1) with many different filter configurations

  - Click ![](images/262.png) button to accept this Policy

![](images/263.png)

- The new policy is added to the “Row Level Filter” policies (as below)

![](images/264.png)

- Test the policy is working - Open HUE for the CDW **Impala** Virtual Warehouse - airlines-impala-vw and execute the following query

<!---->

    SELECT uniquecarrier, count(*)

    FROM ${user_id}_airlines.flights

    GROUP BY uniquecarrier;

You should now only see 1 row returned for this query - after the policy was applied you will only be able to access uniquecarrier = “UA” and no other carriers:

![](images/265.png)

***


## Optional Lab 6 - Iceberg Table Rollback 

This lab will shows you how to do a Rollback to a specific Snapshot.  This is a key feature of Iceberg tables.  There are other Maintenance Tasks that you can perform on Iceberg tables.

27. Iceberg Rollback \[Table Maintenance] - sometimes data can be loaded incorrectly, due to many common issues - missing fields, only part of the data was loaded, bad data, etc.  In situations like this data would need to be removed, corrected and reloaded.  Iceberg can help with the Rollback command to remove the “unwanted” data.  This leverages Snapshot IDs to perform this action by using a simple ALTER TABLE command as follows.  We **_will not_** run this command in this lab

<!---->

    -- ALTER TABLE ${user_id}_airlines.flights EXECUTE ROLLBACK(${snapshot_id});

28. Iceberg Expire Snapshots \[Table Maintenance] - as time passes it might make sense to expire old Snapshots, instead of the Snapshot ID you use the Timestamp to expire old Snapshots.  You can do this manually by running a simple ALTER TABLE command as follows.  We **_will not_** run this command in this lab

<!---->

    -- Expire Snapshots up to the specified timestamp 

    -- BE CAREFUL: Once you run this you will not be able to Time Travel for any Snapshots that you Expire ALTER TABLE ${user_id}_airlines.flights 

    -- ALTER TABLE ${user_id}_airlines_maint.flights EXECUTE expire_snapshots('${create_ts}');

***
