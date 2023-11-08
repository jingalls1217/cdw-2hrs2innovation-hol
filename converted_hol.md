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

![](https://lh7-us.googleusercontent.com/iFo5t722WpITxm0L6aLVlQ8aXiXE7_Vvp_5Zkv5xYM8qk-N5DmTVWvHLY8BmnK2GiEQcZEU97ZyXDu47AcU_kLgojmlf3D3jNUd3mRwKabmNqPtCbBiOj0cB6-wDHWls-bMxd15A7e8KEzmuzjL4bYs)

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

![](https://lh7-us.googleusercontent.com/eV-p09JvPP2KRhdeEOKqIrC5fX8CEDgAmM1CoeHWD1CsZXYN6d2VfUoNuoAypUV9-j9vYieja7Ydloz-GAYB1Oa8Dr8iVbCC6IN-OaDs_8wjaHGjfIxQE2Bd2ePoJsHrYpcRQK4GPD-I3MjjdVRKA5E)

- Multi-function analytics - Data Services; today we’ll just focus on the Cloudera Data Warehouse Data Service

- There are other Data Services that usually are part of an Analytic use case 

  - Data Flow - for data ingestion needs
  - Data Engineering - for ELT/ETL, transformations, data wrangling, etc.
  - Machine Learning - for Data Science teams to collaboratively build and productionalize ML/AI applications and models for the Enterprise

- However, Cloudera provides other services such as Data Catalog, Replication Manager, Workload Manager, and Management Console provide continuity and functionality throughout the platform.

![](https://lh7-us.googleusercontent.com/3Tn0lxTif3CdZD5gATHgN0AT7sLSXlxFGDxapkc_saqNY0_XAaYatzqY2l12WZLtOkN1CNEV8XomLt1xkGu4378I7rfDZ74OnYc0PVWhQKUZpNoWCDF-Dy6pIGWy_jEXimJcpjkOYjpsq4bVDAVlpPE)

Note: The platform removes the necessity to spend unnecessarily on integration tax, where other solutions combine various pieces together in the ability to provide continuity and functionality throughout an end-to-end use case but this is difficult because it introduces many moving parts.

***


##

## Lab 1 - Business Analyst: Explore Completed Dashboard

In this Lab you will explore the Dashboard that will be created as the result of the Self-Service Labs you will complete shortly.

3. Open Cloudera Data Visualization, which is part of the Cloudera Data Warehouse Data Service

   - First let’s open Cloudera Data Warehouse (CDW) - 

     - Click on the Cloudera Data Warehouse (CDW) tile

![](https://lh7-us.googleusercontent.com/eV-p09JvPP2KRhdeEOKqIrC5fX8CEDgAmM1CoeHWD1CsZXYN6d2VfUoNuoAypUV9-j9vYieja7Ydloz-GAYB1Oa8Dr8iVbCC6IN-OaDs_8wjaHGjfIxQE2Bd2ePoJsHrYpcRQK4GPD-I3MjjdVRKA5E)

- We’ll come back to this screen in Lab 2 for more details

![](https://lh7-us.googleusercontent.com/p_Rw3a75otA_R0Ju6nLQlZpW4qCrOwLPlG0u93tT0RP8xfjKm9Qnxac13r-390kKxYNBK5XWUh7CHdkDV12kPXe0q2fj1rFZaT7PpnSPzsokjgH5V3Lajvhr-Qi7SFiMipIVSElDPXseU_NYdGYutjw)

- Now let’s open Cloudera Data Visualization (CDV) - to explore the finished product

  - Open Cloudera Data Visualization (CDV or Data Viz)

    - On the left navigation panel click “Data Visualization” - this will open a new browser tab
    - On the row with **airlines-dataviz-#**, to the right, click the Data VIZ button

![](https://lh7-us.googleusercontent.com/RNxh8sBpej2qX_5gZplM7-nNzu0ups_C2ox1reO8EjRRLpj6g6LD43uq8DX5x0HvUV6mROMNkae6VSc-l5B8OTBY6rI6iCU8wKcUhZ0GM50UFgEywCuwXR8nyHQ4c5Pr-Fw9-52ynuauOJJTJATri8U)

- If you see the “What’s New” page, you can read it, or click on the GOT IT button

<!---->

- Cloudera Data Visualization (CDV) Home page

![](https://lh7-us.googleusercontent.com/4EQyKH71WByHvwgNO4pvQw3gUtK3FFMTJDX7Yif6KK-H3m_Ph8efQDX5Z5gFn5QKZLlGE2qoOJerkUy_ikjgxMMSiDy8XRbKfRjiXr-1CnsnabghIiAl91lKfeJqfoLdptlo2CGEblIG3fxSfDwp7yI)

- There are 4 areas of CDV - HOME, SQL, VISUALS, DATA - these are the tabs at the top of the screen in the black bar to the right of the Cloudera Data Visualization banner

  - HOME - this is the starting point; it shows some statistics at the top, followed by some quick access details to recent content - Queries, Connections, Datasets, and Dashboards
  - SQL - allows you to manually build queries against data to perform quick discovery against the data.  Below is an example of a query that was built and Run

![](https://lh7-us.googleusercontent.com/b4Qt8dwXR92LqamwPeHxLnY5wKt76YZgS2R1q47EnZ0j4J9ZdXYY0SENAnQgO7GmeToZ1BmHE8iMsUD5GHmiTmioSUzfIS-VGL_P_anG_TlBNoGN8bBPniTec0tXaaLetvFQnuTA9BR3plAXoUVl7eI)

- VISUALS - an area for viewing/building/modifying visuals, dashboards, and applications

![](https://lh7-us.googleusercontent.com/83J5vormF9MjZq91HGZgW-CNM5V_mXEAfRhCLuIp8C8lUP4WgRe6-WvYr0u8PjbkiBXRgA03iRJjKmW1ZRzdY_YmSwiasNbO0gimE_oMzDGeLQ49eBlKt6ybQafI9nrtS0_sVF5cTn_nXubtYSoFWG0)

- DATA - interface for access to datasets (aka: metadata model) image below, connections, and the Connection Explorer

![](https://lh7-us.googleusercontent.com/XyK9VGthOOWtRsYqP4fzVvvRoyM0Tb96_YacZurGt4ad3_TcvAuOwDACihba7A44hbvq_78GfRgUmtRQA7VZkwK5YDAmdTqVQ3tIBM0Bfkn-rT5NHzTZPOjaMRRkeyUCdpxvcPRwipqIfilf8wA_H7Y)

- Click on the VISUALS tab at the top of the screen (in black banner)

![](https://lh7-us.googleusercontent.com/fMQEa8xKk0WIZl9Du_faGH7gHMsCaEypb5kReTLNXM50grSkoL2o_skP4LLpNSCLWpj3hS7etXHmhbfMZ6u1N5g3aofl8nJBgkX8wfUskUcyfEw9njgnsa6vsJu6e1AViwhZ4buDjBz34IQ4g41qNhc)

- On the left side of the page make sure you have the All or Public Workspace selected

<!---->

- Click on the tile “SMG Duty Free Analysis” to open the Application (in the bottom right of the tile you will see a purple ![](https://lh7-us.googleusercontent.com/XSaDR0iUae4SHxqiD6-dQmB621TndzqDZKIV-HinhNOKhRPzAHn9fmDXHs1GHoK27SZpiTm0CrqlDHJAVHsaaZUl91FU_HJAy8bxWhn8WijdSlK8sClPu5P8yj2fQN0jdSyHqImJ-S-dT9lPwB5VyFs) icon  identifying an Application)

  - Click the drop-down arrow next to the “Planned Layover” prompt and change it from “All Passengers” to “30+ Minutes” - since the initial questions SMG was interested in pursuing were related to passengers with “Long” planned layovers - select “90+ Minutes”.

  - Next, click the drop-down arrow next to “Connection Airport” - Select a few of the Airports that are interested in this new business program

    - Scroll (or search) and click the checkbox next to - ATL, LGA, and ORD
    - Each time you select another query is being executed against the Open Data Lakehouse database tables - shows the performance of Apache Iceberg

  - From these filters (prompt selections) you gain considerable insights - look at the “Planned Layovers Greater than 90 Minutes by Carrier” visual and the answer to the question seems clear as to “Which Carriers should we partner?”.

![](https://lh7-us.googleusercontent.com/pYyf5JTMDXpDdSRCRjG9X0wuA75I101Ab_sTsSumMOXkZdgAsQ-VqAEHwn6hw7vPS24pfKRqdAIW5UeJUo9d6wZZVBGbx-8uNUTWa7WjobI3oBtg41T5qoXGdROfOvIV-IuFEdIYY1nHZATLRJyPj3Q)

- From this you can see what Airlines (Carriers) that we could partner with due to Long Planned Layovers and see that Delta Airlines (DL) & Atlantic Southeast (EV) have combined planned layovers  for over 95% of Passengers with Planned Layovers of over 90 minutes

<!---->

- What if I wanted to see the flight details from a previous data load?  Click the drop-down arrow below “Time Travel” and select the middle value.  You will see the chart titled “Leg1 Flights by Year & Month”.

Before: ![](https://lh7-us.googleusercontent.com/KZyUKz9ndr0Cu-GDtY0nfjxtox6jToeNefVrHM2MoocpAbl2l48R2HrciTeIw8bYx9wBY3ilOoi3KBjbC2Q7PALcwNoLJaQuYhQHAKKPFuY_JRMJws1IoV1YkCV3KOYWOHHPHS5YMzgFPfAlErQYoI8)  

After (no 2008):![](https://lh7-us.googleusercontent.com/sbg-viQ4CUokB7U9Pb6mMm1xtIx_JBI_uZbg0Ng-96uayq9QreJSxPYF2qJ5UkBFcUA87IQt1tivaVRyitzNUWQ8ayyhrL6Hc1DS4Pv0ygODo_fLAd0-Ew2NCDuZuFcbesob_uKULQId1x3Hc3awHkk)

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

   - Click on the browser tab where CDW is open - ![](https://lh7-us.googleusercontent.com/y023yXD5jigd_deSkJYLwWac9zjt_hiMVBAPyjtEKRh-XOPUhJtIW5Drr3FP4rIPKfQuHjSgCuXcV8D0hLUR1SI0LSeiqq1CJu8eS1ug3IalrFedAyJwgtck5EIk93UHSMTIk2Lxq9nySOP-U2YG5aQ)
   - Click on Overview in the left navigation

![](https://lh7-us.googleusercontent.com/w_T7COlmN9WS45uP1nlKl4rLAYQpIDxjvD5z6r3StlVoy2DFbJazNL5qJi6kZp1Z3QFuFzd52CgKE_j-aI1Mmf6uTtWPIGnHZzK59D-iFLo4EX3mCL0k4IDSfDLiye1XLmx-IRjvrFuzSRPj8fXXSqI)

5. The following is a quick explanation of the CDW User Experience so that you have a basic knowledge of the data service.  The CDW Data Service allows you to create independent, self-service data warehouses and data marts that autoscale up and down to meet your varying workload demands. It provides isolated compute instances for each data warehouse/mart, has built-in automatic optimization, and ultimately enables you to meet SLAs - at the same time save costs.

![](https://lh7-us.googleusercontent.com/UjGhSsPNiSd-mfjQhJGmkGrM1v9ut1JX6_uniXPh8wKSUF3LGu1XjJtCFXLrX4109i1nMIOi5grDYD3Wd3dvb_W-r_IWAuk1eVzi_gE1OipJlGrJtrOmhPoNMHtNhAzoZU-I6KFGch9QezTyv1mwjW8)

- There are 2 areas on this screen - Database Catalogs (DBC), and Virtual Warehouses (VW), for today’s lab, we will just concentrate on Virtual Warehouses or VW for short

  - Database Catalogs (DBC) - is a logical collection of table and view metadata, security permissions, and other information.  As you create databases, tables, views, etc. in the Data Warehouse, it collects the metadata.  When you activate an Environment for CDW, the CDW service will automatically create a default DBC associated with this Environment.

    - DBCs are in the middle column

![](https://lh7-us.googleusercontent.com/HauFGdwnAJKBF4SILscGqS4UNPJ4BJGc1E1oBWCMvGUCdqkMM4ZRpdr4CQpNTk__8Kiyy7ooFHFwNI4I-zlL1UeyV5EhiKAEHM0-am5ONQo97n2nDDbSyt7lTNeVIERUmJe3UdhgwbzgxORb_hh8ylw)

- Virtual Warehouses (VW) - is a set of compute resources running in Kubernetes to execute the queries.  This is something that can allow for Self Service capabilities or can be controlled by Administrators.  A VW binds compute and storage to execute secured queries that access tables and views of your data via the DBC.  A VW can scale automatically to ensure performance even with high concurrency, and can auto-scale down in situations of low demand.  Tools that access data via JDBC/ODBC can connect to VWs to run queries

![](https://lh7-us.googleusercontent.com/ZPpVdj8nYJ8PQDgMAKWrAUL4V3X0eyVTH0Bz00x7U_RdHlEMrm6eFFbEinuERTInVZoWQC8u9zy4lHVr9CHpPDZNmlb6y_2xJ33IXD36t71Uq1SaeWSUXw-inFV-oGxAvqLBUiASTFskro5ywEeaXbI)

- See options available for a VW - click on the ![](https://lh7-us.googleusercontent.com/aaxD0qureu13eAE7jGJ4c8eZYp-SbqSX3e22iI69xEbXpc2zPt2b-COyxC5j2U8mHi6aQ0km92bJaHumVh63Fr5Xevk6hpDCmClsLEWo6Y-4lVj02hZm21q14Ym6P0Ns1uu-offT3HEdEhLwc5zP15k) button on the top right corner of tile airlines-hive-vw-# 

![](https://lh7-us.googleusercontent.com/XK50e0bNVZbeX24k8NbXmvodyIlYo4EWx7T1bXCuzu-9E_XaDLZ6xl2_3hI7Lp5Grc3dxU11_mA9WOsJr-deIfNK-fwukV0MAu6l5fiyjHzvhXCL-c-X7XlzSBlQg1kKsgi4uxejF2hUkvexw67ryJw)

The list of options will vary slightly depending on whether this is a Hive or Impala VW.  This is also where you would go to get the JDBC URL and Driver to use to connect your Business Intelligence software to this VW, and when a new version is released you could Upgrade this VW to the latest release without having to upgrade all VWs at the same time. 

- **_Click on the airlines-hive-vw-# tile_** -  this will highlight the Environment and DBCs that are associated with this VW.  In fact when you click on any tile within any column, it will do the same thing by showing you what it is related to, for easy understanding of the interdependence of these items.

  - These tiles will display information about current workload on a VW.  Below you will see items indicating when a VW is idle and has auto scaled so nothing is running for this VW; and where the VW needed to auto-scale up to handle incoming SQL requests handling concurrency

![](https://lh7-us.googleusercontent.com/k3r2lVWYpoNLtsONtb_HiXHOpNypKYk9RHJW8XCFgrYLk1y3DxugLV_Yurkri-xWD7N0JzoLJQIEgBBOAw9O7XOEt_Cng3NMfIyDRNQOXpIGZx5YOzuv9DP6wI3_Hh9DNyuySFq2QDU71Mk1e_kSWFE)

- **_Click on the airlines-hive-vw-# tile_** - In the upper right corner click on the HUE button to enter into the SQL Editor

![](https://lh7-us.googleusercontent.com/k4z_97RTcCoJrH_d5ZBrcbmkpU8w4s7_J51T-GBqnejSUYqVdkS98ns3okPNUz8UEOq_aGF-heuHimjgeTofXEC3imH-Uq5RDkNp5EsIKh-W0eAZz3mnoY4jO0pD-mnpoQOcGw1qOXGmHPM4avDz-nI)

6. Explore the Data Lakehouse

   - You will be using HUE for the **_airlines-hive-vw-# Virtual Warehouse_** until you get to Step 13

![](https://lh7-us.googleusercontent.com/3uzLGCry2wZSgFaCP1qleFOsDDqm0R91ud5Kp-ephsRsrh8U3nFzG5De8pw2i_uESfirjWeBsQHHTy59137iSzqd9sed0LNsJvI0nFXpHNV9bDCj-LaYVwLJQWxj4bFvrX2gmx-eEa9p8nKpigM1TV0)

- Copy & paste the following SQL into the query Editor window

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| -- Run prior to importing Passenger Tickets; to ensure correct access and that everything is good to go-- Query to find all international flights: flights where destination airport country is not the same as origin airport countrySELECT DISTINCT    flightnum,    uniquecarrier,    origin,    dest,    month,    dayofmonth,    \`dayofweek\`FROM    airlines.flights f    JOIN airlines.airports oa ON f.origin = oa.iata   JOIN airlines.airports da ON oa.country <> da.countryWHERE f.dest = da.iata ORDER BY   month ASC, dayofmonth ASC  ; |

![](https://lh7-us.googleusercontent.com/3uzLGCry2wZSgFaCP1qleFOsDDqm0R91ud5Kp-ephsRsrh8U3nFzG5De8pw2i_uESfirjWeBsQHHTy59137iSzqd9sed0LNsJvI0nFXpHNV9bDCj-LaYVwLJQWxj4bFvrX2gmx-eEa9p8nKpigM1TV0)

- Click on the ![](https://lh7-us.googleusercontent.com/F7sPz-OLgqcZ0YmYH0kaoXTcNm1JIwaPEd968UiswMXz5WR2LgKYaeIEJBZhIElPNum_ANoEepPxymbwZcfTOTe48HTWnN9sCDQ58TwVcxqR9usErFsnIQh_09Bd8gsakkqIw4Nomux89w6wAoARIhk)to the bottom left of the SQL window to run this SQL command to test and ensure you have access to the Data Lakehouse

  - You should see the something similar to the following in the Results tab

![](https://lh7-us.googleusercontent.com/qYk4WJLCt1yoGY4kyTtJmZs_E3n9e8M_Am-Z_OBW6-dOnZM-w-gvMAPrR61Bspq9MrB_HmGQxkn4WfkHA3TYmtwJ5bdE7WlPb-olOHXunumbUZUvvlkY8Z8OR8r3nXXhKjSavizO2-Egih2tkX6cNIk)

- This validates that you have the correct permissions via the SDX security to access the Data Lakehouse

7. Upload Passenger Ticket data file - **_already completed_** for you and shown as part of the main presentation

   - If you’d like to give it a try this can be found in the Post Lab section - work with your Breakout Room moderator to set up time.
   - Below are some images that highlight the 3 steps to upload this file: 1) Open the Importer, 2) Pick a file & options for the file upload, 3) Name the table, specify table options, and provide the table metadata (column names, data types, etc.)

1\) ![](https://lh7-us.googleusercontent.com/NzrxrXBz8hN20vE-XDZ_Cc3Y4JyKM5l7tjJtZakRXX09gSy5ZAn2OIYtJVWwHCNSLvI0v8AksZ_6eEWtl4UtG2oXyjd9LkfAqntW8lViLpK2Gwyvter_0n2iTWJK-6zVdm5glCYDFNX_DrzOMoWRfhU)    2) ![](https://lh7-us.googleusercontent.com/EI7MJyqNc6WlwfPYW5LErtyWBT4HdVPTcUk4qUOrXL4W_NVkNAHUQ0usqFdinNANvSW3_BF2avnmMCoB5hYDpwB38BXlCWWFdpjl_bnuK5xM4ak_eWevqf2s98oGLM5-RizStFSjYL9Z7sYqFYG__To)  

3\) ![](https://lh7-us.googleusercontent.com/eJ2Y_KRiCDKLWNCWVt4YjrymXpSS-2FpQDA6iHvQxjjCKBaJP6O7snmTBWR6v42VmEXcI4L-P_gn-kG-NBZqmrM_VlcTxWfitt-zcDCK9v5r_foABk7RGmMQLGUZLkKpSPdz_GLu6GJggkn7fvotx5Y)

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

- Execute the Query by clicking on the ![](https://lh7-us.googleusercontent.com/F7sPz-OLgqcZ0YmYH0kaoXTcNm1JIwaPEd968UiswMXz5WR2LgKYaeIEJBZhIElPNum_ANoEepPxymbwZcfTOTe48HTWnN9sCDQ58TwVcxqR9usErFsnIQh_09Bd8gsakkqIw4Nomux89w6wAoARIhk) button

  - Review the output to see the number of passenger with a long planned layover (> 90 minutes) by Airline Carrier - one of the questions we wanted to answer

![](https://lh7-us.googleusercontent.com/G6aEJbXWSFOxnYGHnWpvs3kOxRjT1YKGaQQJ5d1iFLJgGDCR1K23pLvjUO5SAVTElOyWyUtL_OFk9O-lNoMI1r_FDTnx-IJfbU6puRjq4qUNgJq7Ju-EnGGoULaWmISO8brE_U1bVnol8KrMZWk-PQA)

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

- Execute the Query by clicking on the ![](https://lh7-us.googleusercontent.com/F7sPz-OLgqcZ0YmYH0kaoXTcNm1JIwaPEd968UiswMXz5WR2LgKYaeIEJBZhIElPNum_ANoEepPxymbwZcfTOTe48HTWnN9sCDQ58TwVcxqR9usErFsnIQh_09Bd8gsakkqIw4Nomux89w6wAoARIhk) button

  - Review the output to see that we can answer another burning question

![](https://lh7-us.googleusercontent.com/hMNwPKNymVAdCtEsdN37Cn84wx5cr5E11aVn8OvzK4O4MEPj74UnUi_fZFi1NE8WcyTUBgTrSkfukRYsdQq4UsJYsjVb42CSyx6y3dj0maIJmDa5zvjtaxdfesAD_Kkbz0cfOoyHSyHtIwcRuEMICKI)

- Note: this query combines both Hive table format (unique\_tickets\_1k) with Iceberg table format (flights).  Allows you to migrate to Iceberg over time

<!---->

- Now that we’ve validated that we can answer the business questions, it’s time to visualize the data to see the insights we can gain from combining this data

9. Visualize the Data Lakehouse and Passenger Ticket data to gain insights and communicate what we are trying to accomplish with the Admin team.

   - Click on the browser tab where CDV is open - ![](https://lh7-us.googleusercontent.com/lZK2TzgpBkunLHTofA13DpIX8rM7rYZpH4b-vfWj5TR44YzKfqhDnpCjFV9L3GVMUsqjpCyrV2Z_q8fcWx6cCC9T-xhKm5wgw48HTCf5yxzFgdvn-rECA7GYj5FfFhoNu52Rel1_Q1SZPWqFAyRJpkg)

   - To create visualization in Cloudera Data Visualization (CDV), the Business Analyst would have to do the following:

     - Create a Dataset (aka: Metadata Layer or Data Model) that will join the uploaded Passenger Tickets (unique\_tickets\_1k) table with the existing Data Lakehouse tables
     - Create Visualizations create visuals that present information so that users can gain insights to make better decisions.  A single Dashboard can have any number of visuals on it.
     - Make the Visualization available to the appropriate stakeholders - by default Dashboards will first be created and edited in the user’s “Private” Workspace.  Once the Dashboard is ready, it is move to a Workspace that the appropriate users can view and interact with the Dashboard(s)

   - Create a Dataset (Metadata Layer)

     - The first step is to create a Metadata layer that joins the Data Lakehouse tables and Passenger Tickets table (unique\_tickets\_1k).  To do this we’ll create what we call a Dataset.
     - On the top banner click on the DATA tab

![](https://lh7-us.googleusercontent.com/O1xAtF0uPi2JRszsVRKt9jYFzQJAqdgoU5traib6WsTxBbMQtCIvOLCCveis8CT9kpADOTDbNBrppJZAga39OLLzXrDlzSqSr_v2sEKTe1ppcoI3jP97Y7FbYVTZs5TuMxreELp6sHczV_gj-OMtLY8)

- Make sure the “Airlines Open Data Lakehouse” connection on the left navigation menu is selected

![](https://lh7-us.googleusercontent.com/Kk_Uo4z9oNsR_2uywY_AE8x6_2E2IYlDdn4qo5Kl4Zf3TSj293qLLuzObAu7_N_9_6GO5GaPAoMu_zmGD3LVZ81qbtmIoD5sTRopZRFeHPAFiVKVDNyiCxqLSdPcRTh6Eje5_61q3QkfCMq3_pXA8uQ)

- For today’s labs we’ll fast forward to a Dataset that has already been created to save time. 

  - **_If you’d like to go through this process, please work with your Breakout Room Moderator to schedule time to walk through the Lab in the Optional Lab section_**

- Click on “Lab 2 Self Service Open Data Lakehouse” to open the Dataset that was already created

![](https://lh7-us.googleusercontent.com/Cx8kmD9s21_G7d_D2tYaYsA41OcW_XxFxwHM2ccU9q7U4wbGxKnYhWjikJlf-NLJ24Ph8HT9uNd63fVfj5DK-uCja_q0yKGrfX4QnNBrYj1k5ApgMyWXA0uE0s4ciJmw8q0nJx4SVDYtAzS-mesfCBw)

- Dataset Detail page - provides information about this Metadata Model, such as the connection, tables referenced, option settings, and date information (created/updated).  Where you see the pencil icon, indicates that you can make changes.

![](https://lh7-us.googleusercontent.com/pP7Xm128iG_3hRtFc52qpwKCMXzSD-5q8A9P09WiXhX-z4x_OpJ6EDz99489XQSMGQ7BWt-OLBzvzB9uBH3nDB3VlyWBpEtPLM_88L9VsdYxx-x_BQrjBdA2lAdVq_KLoJNNXmaBYF0SD7zU8CdrgA0)

- Clone Dataset - click the CLONE DATASET button at the top of the page

![](https://lh7-us.googleusercontent.com/HDs2RRyqfLCJ2pQRbzDaRy0Wmd-Gv-31uMvn1hS_IVFITTZYM7UEOiiRX5QNJ_bSwLX9VilpBOgZLWzXrenb7qB60NxY5Badr3PcWe9JiwvNen7bc0D1_WOxyNSZxdw3zyaQygR3jXMc7G5b1PZanEk)

- Click the ![](https://lh7-us.googleusercontent.com/_09Qe4ewlmhswMqDijU4qNCA0lPIBVPHH4-jk4MDmeCUCxtVMZY9wACcX82XUyztJhNb71ferZib6JowRNYj1i6vcneIL137OS6kIsSwSaK4L5YzafrE3djyUcEHMQlwlpnnMYApqwB1iRHeQW-wVow)to the right of Dataset to Rename this Dataset

![](https://lh7-us.googleusercontent.com/oU0P1JbjpyJa5oyXsTpgz8T_Wxm_UpEqvBtWkM-J8a5OXXi3zCypmzjMKAyaAKXCRmTc25nl-tN_yvVaP8U9zItdm0atsCLrUgDLJrn3bzwunU-YbDY-_anoR5R0Z6FwuV2LjeUJ8xhwgfcCc6AUXJs)

- Replace the “Clone of” with “**\<user-id>**“ (use your user id in place of \<user-id>)

![](https://lh7-us.googleusercontent.com/0wb7B7RPQHFSqFVpY_jrdKAuxhNGnj_ngx7V6HKUSOrlnMp_HU1BtBC0VGzv9tnWEsls9LJkM5aNlOqsKBvGxntsphDGmuFJ3UrebNSXi6CFwm9NdnB0Vq_PY1t82szOsgXN9R4CfqcrV4GqH66aBWM)

- Click the SAVE button
- You now have created your own copy of the Dataset that can now be modified for today’s lab

<!---->

- Data Model - click on Data Model in the left navigation menu to what tables are in this Dataset

![](https://lh7-us.googleusercontent.com/KU-o7itHXEwqPKnibakQqnQfYkR5K8pPJNV4nXCPwJ9CfsTVzHubwGosixWnxWYzOmp-C4bYLv4mIs1tUUhePAZKqNO-ZwoMFrtJii94G-m2RdD23IC--53kmPbMygBSQo9A9R6J-7uzJRj2tbyBtzQ)

Shows the tables, and relationships between tables in this Dataset

![](https://lh7-us.googleusercontent.com/u00EcW3nITxYsdTiOac9DW2HpKVQtmfj64EqhhAALbTqajQgIcFH2ZTWol0UbqDqNclBTy8D4dUj9H2JL4JoYxQFp6Gvni23XCxvHyoKqEGa7BRzXnJh4P8kwsTfahUTrb60kHTnqxdQlz89FxgegmM)

Tables are dark gray and relationships (joins) are identified by the blue ![](https://lh7-us.googleusercontent.com/1uc-yLHlHXjMsihvIk3NlFn9L9IqHBl1jc5Gl0fJRBco63Nd1s_ynykSVOKQ9CD3ws6rlFaQXszOMTH74ZUYTgkujjOfa9vHA4UqMZ-U8bjjcGSP7iv4kTtmIoQTfXtXabOgAr0e3E0Mo94QUUnk6ps)

- In this Data Model you can see that the unique\_tickets table has already been joined to several other tables that are part of the Data Lakehouse (airports, airlines, flights, etc), but there is one more relationship that needs to be defined for this to be complete - we need to get the Leg2 Airline Carrier details

<!---->

- Click the EDIT DATA MODEL button at the top of this page

![](https://lh7-us.googleusercontent.com/74EfemhRIpxIMs3zObo4XE-VQ3uy80wUZ91VeegC_cVnWnDD-NuHylAa45yoQAOKLGjFou5kCsfIzgoi_lF4dpa04IOcflH9IyojcrC4qFuSmPZJOq-BAXsqAIIsWPdtrNCjLQIpufwdOGobaJ2EBSk)

- Click the “+” in the gray oval to the right of unique\_tickets - to add a table join
- Click the drop down below Database Name and select “airlines”
- Click the drop down below Table Name and select the “airlines” table

![](https://lh7-us.googleusercontent.com/tjN1YxKRyz_qkuCrUgZMTz9LZoPOBDlYdX8AJJ3CzNtd_8pXUYE2cGf6Lh8vNmM4A9J764x3wGrjf0zE0VhVlx6HLbmOOnLrWR2vjukujbX-ehHpL-uUqghfxlVU4UUSAMF5kiBDhisO01NPtiJesSw)

- Click on the SELECT button to add this table

<!---->

- You will be presented with the Edit Join definition window (if not click the![](https://lh7-us.googleusercontent.com/1uc-yLHlHXjMsihvIk3NlFn9L9IqHBl1jc5Gl0fJRBco63Nd1s_ynykSVOKQ9CD3ws6rlFaQXszOMTH74ZUYTgkujjOfa9vHA4UqMZ-U8bjjcGSP7iv4kTtmIoQTfXtXabOgAr0e3E0Mo94QUUnk6ps)button between unique\_tickets & airlines\_1)

![](https://lh7-us.googleusercontent.com/40R4yk07pduoOx-VbK0l3boIEtXtOeGj5Uexz3udLqQC1l9P0jEqLNALNTdh9DyqZugrWEpE6MCXqfC5ef8WNAtQorRDF5ovaXUczKRyYPPA78wQJ-Qr8NgxUhaQaSULVaHuRhCrgGbT4oSaAH7dUdw)

- Click the drop down below airlines.unique\_tickets and select leg2uniquecarrier
- Click the drop down below airlines\_1 and select code

![](https://lh7-us.googleusercontent.com/FFLl-KqWKkkpkM_i9kZSbiWjod5mMbSd2B7op3RQnCDnErLN67ZPIpuF5xHSl68Vkwq1fh_nXJsOZgRdml3cdBt7OzOOZtVRmri_xp7i66CEyOLCIHrf7fbFSt9vHAlV2mDPbcbG93EO_v14fT4eom0)

- Click the APPLY button

<!---->

- This will create a join between the unique\_tickets table and the airlines table in your user database.

![](https://lh7-us.googleusercontent.com/KLnRBvFc0nFhq3JT1Npjx1xh2Th8CL6fyBIs9b_f3zUZVxJElXsYQ85NSo-UdjKA2Sf4B7nUw_tw74rUagTqipan_xE-FxBJ0hllC0fhXLIJQD8jk544EMYHJIvEqaHHsuFG2l_b1rw2S46XQvMVnz0)

- To view or edit the join that was created click on ![](https://lh7-us.googleusercontent.com/1uc-yLHlHXjMsihvIk3NlFn9L9IqHBl1jc5Gl0fJRBco63Nd1s_ynykSVOKQ9CD3ws6rlFaQXszOMTH74ZUYTgkujjOfa9vHA4UqMZ-U8bjjcGSP7iv4kTtmIoQTfXtXabOgAr0e3E0Mo94QUUnk6ps) between unique\_tickets and airlines (at the bottom) Source/Target column 

![](https://lh7-us.googleusercontent.com/nMH4vUZWqXTkSci6nnFknY-IORqeCagQaChqzwv0qXdwiKw3i_Q91C-ylj1dbzmakZuwNU1-1WzllexdQqJ6bnwW4lFTlVeQlGpEuBGyVybBrbvu8tzKzjviltLuC7kkZ3Gi0r8nHLqlXNAAfVHRoPE)

This will show the join type and allow you to make changes.  You can see by default it created a Left outer join which you can change by selecting any of the other types such as Inner, Outer, or Right.  This Join is exactly what we need, so no need to make any changes

![](https://lh7-us.googleusercontent.com/14nWhEKTzpaCF_HrxAE2FWFthzAHwWUPP-BiN2KjZyUfFfTWw7GuHVEM9lKimDvw6AG8GwLu_nFSUEfDRQytITZe6EFXMmXxOtmP8MJDt0bi0npqnO5dIF9lVzmBchT8KVkOvJ_6qOKJpOG6SRH3GsI)

- Click on the SHOW DATA button to see a preview of the data - this will run a query to combine the data from our Data Lakehouse with the data we uploaded to make sure that the data looks good.  Scroll to the right to look at all of the data from each table, and scroll down to see more data

![](https://lh7-us.googleusercontent.com/lpF7d8eCW3svrbPggkyxyKJAu-P25Qt-U86XuCeGryLlCK1jct4p4GKio9TRjEHsr70rPlHR2YqbdHhRCF7jrxPytinu6aiC_Lk1G-J-akJIZMoXrbSD9PzpNqKekyn4YykLvQSfWpQWkupIjHDWUz0)

- At the top of the page click the SAVE button

<!---->

- Fields - on the left navigation menu select Fields

![](https://lh7-us.googleusercontent.com/kcGvKKlhXKDSbsXbgKM6pVp06ev3ueSUuMcx21N77NIOwB2bQjmW1-ntcjo-CRjbOGHr2v0AzvGpUiftkfLg7klF9Hbmn4T_YuceLVOriq5rJywonVoWnZLDkCkgSTaKa2R1lJzZwIepgH096ciDsZw)

- Click the EDIT FIELDS button at the top of the page

![](https://lh7-us.googleusercontent.com/jr2fqkYp6jyYT2HT4KrjXPTk_nPKivt7YDtrlKm0zmjspux7cU8SL8kC5clMmf0OayPbjEwAgQdAqTtToJl83fL41L_s3zCKn3lkRL_LIVWqAxYuEXOo7uMVdJYsF6MhsQBB4kq-Ass7gNlM60kpjCw)

- Under Dimensions - scroll down to the airlines\_1 header

![](https://lh7-us.googleusercontent.com/NaEpzOJM_S-sWGfWswxbY-ny0TpvBwPPJKpPmAyBHHm-z_mz2h43Am7hG34s3suv7uX3k1Zlp9rkRpFj_-FNrE83eZ2-vb17A5MDqadUklmM7e2hGUdQzdguvIpeDX3NDvsm6Ttl7Zedo5SqXkzK9t8)

This is what was added from adding the airlines.airlines table to this Dataset.  From here we can apply business rules and context to this Dataset.

- Rename a Field - Description to Leg2 Airline Carrier

  - Click on the ![](https://lh7-us.googleusercontent.com/Gvhl8SZ5H64Q5zKTViByHeTB_MyUi6pf2lVH80ZcTApFntYy4d_aVTApQSFW-DSWzJP6ftJZCP7DHbdX0bljjkQx42Fbh5RlbZkS_V0DNaqADve52ZzpUK0dY_johtkmrVEKeduTls02rd-mYDoDurI)button to the right of Description

![](https://lh7-us.googleusercontent.com/3AE-ITBiKYOQ5M3Z8xFw32ELj3GESMjPd72NE6LHAZqEIfzfRA471hbStU1k73PFhodjBAAkcYZ5FB9Q4_3M7TBbWd8XZSbjkhWYe8veFzIDdhYvxvzuVp-TmmC_AlpqvEjf0CQ96wZGQG6XT91aB-E)

- In the Display Name text box change this to Leg2 Airline Carrier

![](https://lh7-us.googleusercontent.com/4tOkddtELlWS4tmw7MPpJl0dp6TSV6vEyvN-LgncgSovBDS1t5DP6lvcLir0JX7uVjnI1Kj05r0mQAP2v4yA0ZsDYhQz5a7dygtVo1c1pFRNfigyIbnFqP7qmPvXKPskagMLCePbURm548sOZPbgYAA)

- Click the APPLY button

<!---->

- Hide a Field

  - The airlines\_1 code is the same values as the leg2uniquecarrier field, so no need to have this twice
  - Click the ![](https://lh7-us.googleusercontent.com/B82sPNCon9gpO_0YwujbqOgujtPglsYndpm5tyGbWeb40ZUvHzy5703_zHPkeKnjygqVwWGQpM9hxohv9wZE28mBn-5TUz7KcsjXVSnO8sAII6gHaMjqwqD79vX7nDI0pVa0ky-53H1cbTeYGK6CbUE) and select Hide

![](https://lh7-us.googleusercontent.com/tkiSpnKKWwI80A4jNvyoEXFt33iCmKwc2g7E12jNJDqD7eEaekDpQZYr5BhyzACudE5DXP9Jht8oNO0Sq9K0mXPu6Uivrm8lZx1kRzpX92DgWYsQZmhySIg73LrFxKP9zBWwGCW98J0KskbtrxbRdSU)

- Select Hide
- The airlines\_1 section should look like this

![](https://lh7-us.googleusercontent.com/haiYinEgBhm_-50FBe1sok0iL8NXV_Q33pDqBYsXT5srGBZd6Rai5NZzQoTMXeP2dDohqog7gRiEt-KXhOHyrwOonusQ-2GBAmRjoY5OAJVStK-T6tjmeJ64_BuBfzha-yH7y4VHSbegYzttOEALVAE)

- Click the SAVE button at the top of the page

  - There is so much more you can do with a Dataset, including adding calculated fields, assigning default aggregations, apply formatting, and strong data types to help with building visualizations quickly.

<!---->

- Create a Dashboard - click the NEW DASHBOARD button in the top right corner

![](https://lh7-us.googleusercontent.com/F8UEZPCuPU-aQH6wogcPfzF4n6FCrWoJonCvN6pGgZA3A9d-WvF3KHMH_092AYv9dGWft0BNxTKpEMJaNYc7opxTDRhwPcIDowtAfpQ7EcpVVXltFz-z26UAQpmkEU-KofoDqW7x0viONVen0HihIbw)

- This will automatically build a default visual for you like this

![](https://lh7-us.googleusercontent.com/DGOTu0GuGNECpHAc6bR1ZRFO7WAPSNtq5hrSHBFIRlHPFZoEDBPl_9V0EE9RI0dlYhtYUCk4aUG1BZnFRQRXU9AiLJ9oXOa1ZWlKhwl5DlnJRgSJB2Qg2t0ouo4rR-ygLH2YZWYwhuzrCIEx_87lwIg)

- Let’s change this to answer one of the burning questions - which airline carrier should we partner with

  - Toward the right of the screen under VISUALS and select the Pie Chart visual (3rd row in the middle)

![](https://lh7-us.googleusercontent.com/M6ZhzSK15O11lOP0Fg8TohaaFEIjVWFvHcFxXvo3i_3gwDvokTEPtEHkFItcxmtUoDjSVG8ibe_c1QlLI2fAKnK2QAYczn00TNR4a-FdOrImEQ_WHrRMylUZvBzLoOWdYFJPv2Nr5pdjUsSL9V-hcPo)

- Under VISUALS click on the box under Dimensions - this is called a Shelf.  To add items to a Shelf you can drag and drop or in this case select it from the far right of the screen from the Dataset we just created

  - On the far right of the screen under DATA click on Leg1 Unique Carrier

![](https://lh7-us.googleusercontent.com/v8jPkW5waUQBL6xiGIPJUYb_DFhJsu8s0NdHo2J9_aSc77szzFMZnAdhPu50W30mM7pDGSUS_9tw52bbwAJc5ndN1eqHtFzxdRJNAM6LnXHkkp5C0q2sT88zFrKWRrH6QpuruRd6tmNKGLOlP7Pqy4g)

- This will add this to the Dimension Shelf

![](https://lh7-us.googleusercontent.com/bs3z2dl2zlwS8bmCmTsXdK23cYMah4aenIzBTBfe0NB32VcKyTvWx5tTHDgJ-zvdp2dl6ciCQUR3RfuhojrmhrLB3P0r9XTJ-R104F1jj4o5qecC6whFvRA1ymT6RxvE82shHAK6bETaqRuYpw0p_sE)

- On the far right of the screen, drag & drop Record Count from under DATA > Measures > unique\_tickets to the box below Measures

![](https://lh7-us.googleusercontent.com/K0JQfWMmpkbsygIH81tvS7FY3Itn_F4eQ6nT3dSKWxyFO-No0Qo-Op4AkXBqcks0IbFTC2sqNLSkB5vkaZl7M9IzAtP5TR8WFN-h2bWUQbWC-sP0-KdmvPkt-MKuNZTt4rKcFQfGJE0xcFT_XUx221I)

- It should look like the following screen.  This will combine data from the unique\_tickets table (file upload) and the existing Data Lakehouse to display the number of passengers by each Airline

![](https://lh7-us.googleusercontent.com/JR69Fk9qjqK6fNrVkrw4YnquG8-r4YUR2E-B0-L3GCqlg8NYfbsXsK8hvAihZ3606RKu3IZSNXSPefDYgpelR9ROobAcfIirVjr6vGRLuT-PCagBRzb9aoToTX5Jz6HZEnYJpqtdSw6n6Rdxh5CXhME)

- Click the REFRESH VISUAL button

<!---->

- On the left of the screen the visual is updated to this

![](https://lh7-us.googleusercontent.com/b6bzQpsD8vPRWM5BQduAYCi_7hSDrNW_wj62FKqKLiOMKyA81rjpZimiScm7KXDVZ9rBXNXAx9kD_Xu0xNrYBu5yt2-881recseoqMlz66bwVbWC3c3iBi3mTa2dmnkrsKr0V34Zb_AEZ03rHhKUYcU)

- Add a title to the chart by clicking on “enter title…” above the chart.  Change it to “Airlines to Partner” and press enter

![](https://lh7-us.googleusercontent.com/WcQUmJGCYbs42ewAzVAokdBhMtv9D2Je0dJXYc8UxYUXwYgRVydHP6Ve9WY5WJKmL_9oE9QqyZwuKVx5bMb-0iu4u9r-tX5yPl7HK1vX0vZb88zAbJmochbqGXfAYJHVoF1SnutZu9r17Y9Xg2SmjwQ)

- Add a title (name) for the Dashboard - at the top of the visualization click on “enter title…”

![](https://lh7-us.googleusercontent.com/wGWQvJecTe78XiyKI3DpIxvNO83Osbh3izk7W14ZMQAtyfzuUQdSZLAwY3z9Pjy9lqzydJ98JhPHU690pVyCJrF175J81FJu3BGnfvmTiyIZqGhj251nUyCz6OdJiRH-E5Ju2N-psvbFx1ozYPoXTzM)

- Type in “**\<user-id>** Self Service Dashboard“ (replace \<user-id> with your user id) and press enter

![](https://lh7-us.googleusercontent.com/Od7M7GRRx9_1YxhdoumkwcTROH6clw-peadGN0EKzzhHNRprgpOJU6LXpMGQjslkKjsc9Zb_tO5J0cLPDn4dYCf-JpHIKfgyjEqockES4ni_koVh0xGelWNzzjwUCtuvF9ajzk0iM04Vzxv5Td-j294)

- Press the SAVE button at the top of the Dashboard - you have now created a Dashboard combining the uploaded data and the existing Data Lakehouse
- Click on the VISUALS tab at the top of the page

![](https://lh7-us.googleusercontent.com/gCGJM5wOWrArHV8wZ2FFPuNWQ5r0BsxFoiXR4UHbztFHkbSJEjk7fHGBEJZMUuM6qRTX1TEbzXen44HKPCpQ1iqlkiwdNAemq_yLVcf496pvhRTn6sA0nxcHbW8j78n0zkRtMOPtDSt-10MueshtoKs)

- On the right of the screen make sure you have Private selected to see the Dashboard you just created

![](https://lh7-us.googleusercontent.com/eCDRSlte25OAahiIMUhznyu5MYFAR09I6jqGGXm8K32LTo3wkFHg_2SIlBKAVHZ-lZqTPv94f7Cw0zVo1w2czg1Z-cP6DXQDvDpvXY3ur62_u-YqhNNOUoyqhLXUgyS8Ddphy7jFznC5U8oNxv7nbG8)

**_\[OPTIONAL]_**

- Add another Visual to the Dashboard you just created  using Natural Language Search

  - Instead of having to create a visual manually let’s take a look at another way to add visuals.  Using Natural Language Search to create visuals and then add them to Dashboards eliminates the step to manually configure a visual and allows users to do this in a much more simplified way
  - Click on the SEARCH button in the top right corner of the banner

![](https://lh7-us.googleusercontent.com/p3VpnmolZMww7YS-8IFMxzpI3rf5caUleBLo668SE3Mec7RanOm_x4YXGezYwAlYFJrj_0eTbgiQ57Zw8AXNSIq4p9HScvAzCOJW742q25nhuO7DbaGUW1QE8JJiQwmkOX8cSLwYBjVwlPI7hgqr60U)

- For this I’d like to see which Airports have the highest number of flights this year and I’m interested in the visual being displayed on a Map of some sorts.  For this let’s

  - In the Search box start entering - Flights by “Origin Lat” and “Origin Lon”

![](https://lh7-us.googleusercontent.com/Y4JKiToqZnFsFApMFWqQpgY1Vk8SqbZn2d28FJO96VNJCQp3fKtIrPugeIUTj8oBkMEGCMmVXyopBYeMr8l1vaL43316FBPDJXx8grpKqMmCCIJXDueSxqin-dpC1bx_yEmt42e0nA7FqG6dXekbrKA)

- You’ll see below will show some helpful details to help with finishing your search.  Under Flights select the entry - Flights by “Origin Lat” and “Origin Lon” as Interactive Map this year

![](https://lh7-us.googleusercontent.com/C4CEUetdD7fED_R4AyuAdzptW5vGJuQqjtEizzSEHss_CPTEP5hy_DdCZZKBBWW98xQvjLRCAI7wAckJLBB7y5JcEoW23CknZmFEUpmWtxzIAykNP28YC9uc-04g8KYesbK_6paCKNKOqZl5eipF3TY)

This visualization shows what was asked for.  From here you can continue to change what is displayed, Bookmark it to share or return to, or just continue on.

- This is displaying what I was interested in and this would be a good addition to the Dashboard.
- In the top right corner of the visual - click on the![](https://lh7-us.googleusercontent.com/_zG0XS8h5zbx3m8u1dViGbGVU9rccOeO5v64VkJxYtUJDstu2pVer20jLfkWNpcLnxG6U3GtwTEiqL3y5Jvuc05rk-5HAje9Pys2DEjU7cSjFZY4_MYGwounvTRfwBu7pojdyrGLdoEuJLvc7NRFxvQ)button and select Add to Dashboard 

![](https://lh7-us.googleusercontent.com/pGjzvLs6qXMaAZfqdsUs7TtF4HmhPpqu658BPaC9R21Gm6YjYqZSdMY9XrHzGRrqgZ1-85o9R8l1wgBIqVcOXOW8DJHKNqKkiegl8h91ovW-2Gss9PQvDrtnCAVr4tg1VWK1rYjD3PbD5abkYd-joWI)

- Click on “**\<user-id>** Lab 2 Self Service Open Data Lakehouse” to expand this section (for \<user-id> look for your user id)

![](https://lh7-us.googleusercontent.com/cqGUWtNhfqq1Eap690-H2kGVF47i61n0HQPYRKO2_7iIFCmMb3oukL7FgbO7XuGqsDgzqEHEogzRvP6cwTrX27aw9523gZ741UPPrvFR-DDpt-GcKMDwCxorZvcjJYOA07zQAt5y7H3Od-rkKYefvM0)

- Click on the Dashboard you previously created

![](https://lh7-us.googleusercontent.com/6bG_9YJaB9viu8rs2KZp5WxF1ArqalmOALS0avzDJkix8cq2AF4AAZ8g38lqHeHA-whhwnP_pU7mN3PhQfW1xKpEUAr4oMOdzp-h4njCoXStdjWDXZH7MK49a4k7p-3cY602wC0IRM_TkspnX35738k)

- You should get a message indicating that this visualization was added to your dashboard

<!---->

- Click on the CLOSE button in the bottom right corner of the Search window

<!---->

- Now let’s view the updated Dashboard 

  - Click on the “\<user-id> Self Service Dashboard” tile

![](https://lh7-us.googleusercontent.com/46JkViClde1gLlVkMtC21IcKIosyC80lExbQh4CSCGnCMO1b8sdUCbwleAtNvVhjCk7mne8LaO1n3sZ7bNLh1PAaI2pzWgiqsYJakjtNoRrG_AkyGx5LwXa-aLek-VLR0MIzinDm5ybb1XpvRq8P1zc)

- You should now see the following - we just now asked a question and created a Dashboard from it

![](https://lh7-us.googleusercontent.com/H-npdVkPN3wXVRHpxKyne4hXFqMA-DIm4uVEA1e05PHzikLHziwzjiihAtLU0HLX5FIZmKWUB7IKgbx5K-wM0p_otuY_vYePdGHuTrrD4u9u0uN0mbSK5Igev33fAU7llINiXMLFZx2pNvYMdtEDOmg)

***


## Lab 3 - Administrator: “Productionalize” the Open Data Lakehouse 

In this Lab you will be an Administrator and will use CDW to create and build an Open Data Lakehouse and take advantage of some of the key features with this approach.

Execute the following SQL/DDL/DML statements.

10. Stay in HUE for the CDW **Hive** Virtual Warehouse - **airlines-hive-vw-#**

    - There should be an open CDW Browser tab, open the ![](https://lh7-us.googleusercontent.com/y023yXD5jigd_deSkJYLwWac9zjt_hiMVBAPyjtEKRh-XOPUhJtIW5Drr3FP4rIPKfQuHjSgCuXcV8D0hLUR1SI0LSeiqq1CJu8eS1ug3IalrFedAyJwgtck5EIk93UHSMTIk2Lxq9nySOP-U2YG5aQ)browser tab

    - Create a user Database to store all of the tables you will create in the following lab steps

      - In the SQL Editor window create a database for the remaining lab exercises, execute the following.

        - Delete the current query from the SQL Window
        - Copy & paste the SQL below

<!---->

    CREATE DATABASE ${user_id}_airlines;

- The “${...}” notation is a hint to HUE to create a parameter.  As you copy/paste in this you will  see that HUE determined that there is a parameter that needs to be entered.
- In the “user\_id” parameter box, enter your user id (see Lab Setup section)

![](https://lh7-us.googleusercontent.com/vlHIFz105afZ5aAFk6IecZP8CGtjTInLVSEunEraNrzeXbsPu-wj_uRWh4eiCE4G2yKiRpDCSvENrrSvj8pMjej68HQCu-_gbkUJ46XJP0-gFHA22mevHHfLUwCugG-gx1_dhRcAEpsHNBUcDhwF4No)

- Execute the Query by clicking on the ![](https://lh7-us.googleusercontent.com/F7sPz-OLgqcZ0YmYH0kaoXTcNm1JIwaPEd968UiswMXz5WR2LgKYaeIEJBZhIElPNum_ANoEepPxymbwZcfTOTe48HTWnN9sCDQ58TwVcxqR9usErFsnIQh_09Bd8gsakkqIw4Nomux89w6wAoARIhk) button

<!---->

- Check to see if the Database was created

  - Delete the current query from the SQL Window
  - Copy & paste the SQL below

<!---->

    SHOW DATABASES;

- Execute the Query by clicking on the ![](https://lh7-us.googleusercontent.com/F7sPz-OLgqcZ0YmYH0kaoXTcNm1JIwaPEd968UiswMXz5WR2LgKYaeIEJBZhIElPNum_ANoEepPxymbwZcfTOTe48HTWnN9sCDQ58TwVcxqR9usErFsnIQh_09Bd8gsakkqIw4Nomux89w6wAoARIhk) button to see that the database was created

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
- Execute the Query by clicking on the ![](https://lh7-us.googleusercontent.com/F7sPz-OLgqcZ0YmYH0kaoXTcNm1JIwaPEd968UiswMXz5WR2LgKYaeIEJBZhIElPNum_ANoEepPxymbwZcfTOTe48HTWnN9sCDQ58TwVcxqR9usErFsnIQh_09Bd8gsakkqIw4Nomux89w6wAoARIhk) button

![](https://lh7-us.googleusercontent.com/npMAO4DuRQ-PH2P_XLRf40sEyMVx125xgjqZxcoV65EVXnQa2RRUxR-ddUoGulLl4s209eAl6oDvY6OUClLNEjuNYHhWWxbSgrRie-KtrMucbeuXxxUPCpD5OoFinZeF1h5eY0qcTYac3VtQfn3RAJs)

- Switch Database to the user Database

  - On the left side of the SQL Editor, click on the < arrow next to default

![](https://lh7-us.googleusercontent.com/xkR6Ig3hQ6ER7KIV1QOLwRM0J2N4vdoc4e3sJHGNRo0z2JRrJfGPV-v0s2TFoXERPtGZOk-fR0KNSjTojB6bQ4gcnt242Ip1_lks1GA1WqJfOWqgaY9C9MOtPEafZ9AZu-BjT-V_gUaK45ANoy407YE)

![](https://lh7-us.googleusercontent.com/ASqgi3JLXknMoczU3V8LvbKGL543Lng86ZHxB2GM0OUpQjhdmCcp5hPH--qtJTfRWHqLP0oKdhH_kPypEL5IZF3bd4Ravu80bjbZuD7TwI7_Fi8nL76kV08RJhsWDZldSMF5DYZ9elPwPITu3yfl0qI)

- To the right of Databases click on the ![](https://lh7-us.googleusercontent.com/ASqgi3JLXknMoczU3V8LvbKGL543Lng86ZHxB2GM0OUpQjhdmCcp5hPH--qtJTfRWHqLP0oKdhH_kPypEL5IZF3bd4Ravu80bjbZuD7TwI7_Fi8nL76kV08RJhsWDZldSMF5DYZ9elPwPITu3yfl0qI)button to refresh the list of Databases

![](https://lh7-us.googleusercontent.com/wrwgaWcKdB1H4lR1EH8g7tkoESt1LvPbZHFqyCKz1sdVSbhVfKVn5MStNwGd31gyHu9H5Ots_J-cDfMFIf2nAZ6YurtkwhI97ELqk-XU1m_3DVKAeEDK-cN0-OnU_sACF7X-8T3GMKKbdF67_18Qq6c)

- Click on your \<user-id>\_airlines Database - this will allow you to track what has been created in your database through the next steps

![](https://lh7-us.googleusercontent.com/SahS6qmzQpwq44K7w3ZUfN1EOdqTA5Wy8o6zot6ieQaY3L6wdAOwD8xMIguBq9rs75mjnN2IHiuarOXN_C7qcn9zDAsLm6Fth8gkrMmViDa8H_DiXxPN1hJS4IU6RhH9QhEyXjxZaNtBhhR56D4-gf0)

- Delete the current query from the SQL Window
- Copy & paste the SQL below

<!---->

    DESCRIBE FORMATTED ${user_id}_airlines.planes;

- Execute the Query by clicking on the ![](https://lh7-us.googleusercontent.com/F7sPz-OLgqcZ0YmYH0kaoXTcNm1JIwaPEd968UiswMXz5WR2LgKYaeIEJBZhIElPNum_ANoEepPxymbwZcfTOTe48HTWnN9sCDQ58TwVcxqR9usErFsnIQh_09Bd8gsakkqIw4Nomux89w6wAoARIhk) button

  - In the output look for the following fields - scroll down to look for the following properties: Location, Table Type, and SerDe Library (this value should reflect the ParquetHiveSerDe, indicating this is a Hive Table Format)

![](https://lh7-us.googleusercontent.com/INx62CpqTwTLCNtmtlASe8SeL9gkJWW1vcK_oAngWozhufDbbybRPn5tsgzGKZs4-xl9BSCMBcrzZ8029zEurKGCnxe-IGt-PUYkLJYO5TiX-sV9Zjxb08Gn3On3e_Q9dDi_kICV96AHrCNvqfNV8U8)

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

- Execute the Query by clicking on the ![](https://lh7-us.googleusercontent.com/F7sPz-OLgqcZ0YmYH0kaoXTcNm1JIwaPEd968UiswMXz5WR2LgKYaeIEJBZhIElPNum_ANoEepPxymbwZcfTOTe48HTWnN9sCDQ58TwVcxqR9usErFsnIQh_09Bd8gsakkqIw4Nomux89w6wAoARIhk) button

- This migration to Iceberg happened in-place, there was **no** rewriting of data that occurred as part of this process.  It retained the File Format of Parquet for the Iceberg table as well.  There was a Metadata file that is created, which you can see when you run the DESCRIBE FORMATTED.

- In the output look for the following fields - scroll down to look for the following properties: look for the following (see image with highlighted fields) key values: Table Type, Location (location of where table data is stored), SerDe Library, and in Table Parameters look for properties MIGRATE\_TO\_ICEBERG, storage\_handler, metadata\_location, and table\_type

  - Location - Data is stored in cloud storage in this case S3 in the same location as the Hive Table Format
  - Metadata\_location - Since there is no need to regenerate data files with in-place table migration, you save time generating Iceberg tables. Only metadata is regenerated, which points to source data files.  Removes Hive Metastore as bottleneck.
  - Table\_type - indicates “ICEBERG” table format
  - Storage\_handler & SerDe Library - indicate what Serializer/Desearializer to use when reading/writing data in this case the “HiveIcebergSerDe”

![](https://lh7-us.googleusercontent.com/kjTQthkI00r8TEtTWoIRwn_4bac2nTIdcLfvUtehfLUikP1upaQEF71tlfQLFviWBiJt7Ia6fSjrZNbqnd2j09SLDCpIfvA6bL9tEsN1cvpUe_etLVbT4zFUQz2nXvOlT9yPulqZwqQvP33eMXQBrCA)

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

- Execute the Query by clicking on the ![](https://lh7-us.googleusercontent.com/F7sPz-OLgqcZ0YmYH0kaoXTcNm1JIwaPEd968UiswMXz5WR2LgKYaeIEJBZhIElPNum_ANoEepPxymbwZcfTOTe48HTWnN9sCDQ58TwVcxqR9usErFsnIQh_09Bd8gsakkqIw4Nomux89w6wAoARIhk) button

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

- Execute the Query by clicking on the ![](https://lh7-us.googleusercontent.com/F7sPz-OLgqcZ0YmYH0kaoXTcNm1JIwaPEd968UiswMXz5WR2LgKYaeIEJBZhIElPNum_ANoEepPxymbwZcfTOTe48HTWnN9sCDQ58TwVcxqR9usErFsnIQh_09Bd8gsakkqIw4Nomux89w6wAoARIhk) button

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

- Execute the Query by clicking on the ![](https://lh7-us.googleusercontent.com/F7sPz-OLgqcZ0YmYH0kaoXTcNm1JIwaPEd968UiswMXz5WR2LgKYaeIEJBZhIElPNum_ANoEepPxymbwZcfTOTe48HTWnN9sCDQ58TwVcxqR9usErFsnIQh_09Bd8gsakkqIw4Nomux89w6wAoARIhk) button

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
- Execute the Query by clicking on the ![](https://lh7-us.googleusercontent.com/F7sPz-OLgqcZ0YmYH0kaoXTcNm1JIwaPEd968UiswMXz5WR2LgKYaeIEJBZhIElPNum_ANoEepPxymbwZcfTOTe48HTWnN9sCDQ58TwVcxqR9usErFsnIQh_09Bd8gsakkqIw4Nomux89w6wAoARIhk) button

<!---->

- Looking at the SHOW CREATE TABLE output, scroll down and notice the output is the unformatted version of the Describe Formatted as we would expect.  The main item to pay attention to here is the PARTITIONED BY SPEC, currently we’ve partitioned by just the “year” column

![](https://lh7-us.googleusercontent.com/ni13740xItwqFVSbR436-zPWYQUBvWAYYxvREt1GB97-3b7nEZd7PrB7ac7RDvkVwefXekYbDQ3_4WrmE9OPZ_5bLQPpCASzQhU5JCUo21gbi1ZTfkdwMTI4gwzvxcr37tqm5nKi-T8p-ulLLAdK9aY)

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

- Execute the Query by clicking on the ![](https://lh7-us.googleusercontent.com/F7sPz-OLgqcZ0YmYH0kaoXTcNm1JIwaPEd968UiswMXz5WR2LgKYaeIEJBZhIElPNum_ANoEepPxymbwZcfTOTe48HTWnN9sCDQ58TwVcxqR9usErFsnIQh_09Bd8gsakkqIw4Nomux89w6wAoARIhk) button

  - The Insert will insert data from years 1995 to 2006
  - Notice that each of the years have a range of data within a few million flights (each record in the flights table counts as a flight)

![](https://lh7-us.googleusercontent.com/3nDUlOW5GwbJiL9pRYlSlxM8JuvBuOSSh7sahfMDDr8ixDaYxIa62I-em7l7JJKttO2F1nOrJjE9-OAxkYyhd2YihL_jlYWhUr1RY2OsTpHzk-Z8wLB-U5us7E29r1_49RO6_P7lnbYq2tevpdwGeCs)    ![](https://lh7-us.googleusercontent.com/3nDUlOW5GwbJiL9pRYlSlxM8JuvBuOSSh7sahfMDDr8ixDaYxIa62I-em7l7JJKttO2F1nOrJjE9-OAxkYyhd2YihL_jlYWhUr1RY2OsTpHzk-Z8wLB-U5us7E29r1_49RO6_P7lnbYq2tevpdwGeCs)

12. Performance improvements 

    - Check that you created the tables for the Data Lakehouse - on the list of tables to the left of the Editor window you should see the following tables

![](https://lh7-us.googleusercontent.com/oeDaL0fptZJflV4-JGkO4ivCMIWeJ5PFYnTDJhR21DBNwRhKuaZ9lTUzreqLK_-yupF8sFTFPhWjRU5NXEnzbil9t7zrRKMdW-lazRAIpToB7eLLQpG7hhARN43PahBAxLbK2L4SfJ78r6lEPzo6lHc)

- Iceberg in-place Partition Evolution \[Performance Optimization]

  - One of the key features for Iceberg tables is the ability to evolve the partition that is being used over time

    - Delete the current query from the SQL Window
    - Copy & paste the SQL below

<!---->

    ALTER TABLE ${user_id}_airlines.flights

    SET PARTITION spec ( year, month );

    SHOW CREATE TABLE ${user_id}_airlines.flights;

- Select all of the content in the SQL Editor

- Execute the Query by clicking on the ![](https://lh7-us.googleusercontent.com/F7sPz-OLgqcZ0YmYH0kaoXTcNm1JIwaPEd968UiswMXz5WR2LgKYaeIEJBZhIElPNum_ANoEepPxymbwZcfTOTe48HTWnN9sCDQ58TwVcxqR9usErFsnIQh_09Bd8gsakkqIw4Nomux89w6wAoARIhk) button

  - This was an in-place Partition Evolution, meaning that the existing data is not rewritten as part of the ALTER TABLE execution.  What will happen is the next data that is loaded will use the new Partition definition.
  - In the output scroll to see the PARTITIONED BY SPEC to see that it is now both year and month\
    ![](https://lh7-us.googleusercontent.com/HKPWMHJ6D-wsbxQ62tZ_EpMQk8dndsyRtCzCQHSHwsYHiDoYCgSign-ur4C1emlK3xoqUl0_28aSOFR8VC3JovrRhdsrplukuE_5mgwNC89CbDZVS9JJhw0LiipyhP3NbsFSKyP51pCMkpdae1NmLGY)

13. Performance Improvements - Open HUE for the CDW **Impala** Virtual Warehouse - airlines-impala-vw.  

    - There should be an open CDW Browser tab, open the ![](https://lh7-us.googleusercontent.com/y023yXD5jigd_deSkJYLwWac9zjt_hiMVBAPyjtEKRh-XOPUhJtIW5Drr3FP4rIPKfQuHjSgCuXcV8D0hLUR1SI0LSeiqq1CJu8eS1ug3IalrFedAyJwgtck5EIk93UHSMTIk2Lxq9nySOP-U2YG5aQ)browser tab

    - Click on the airlines-impala-vw-# tile

      - In the upper right corner click on the HUE button to enter into the SQL Editor

![](https://lh7-us.googleusercontent.com/XvF1PF1PswP5Kw5A_WrCSlhMIX1MZCqeGZqKVQXb_UiMiT_ZWS_aEpwhJkyUgiGzx7VVml7a1mQtElKlH2hp0hBRe6u4aheBWe3ginPNYdmiZaHjvuBaTOKTA1M-_xuOwiIeOn0_2s6o-2HrmeKrEoI)

- Load new data into the flights table using the NEW partition definition - this will load new data to take advantage of the new partition specification.  This also shows how Iceberg also supports multiple engines by allowing both Hive & Impala to create, load, query, and or modify Iceberg tables.
- Copy & Paste the following in the SQL Editor window

<!---->

    INSERT INTO ${user_id}_airlines.flights 

    SELECT * FROM airlines_csv.flights_csv 

    WHERE year = 2007;

- Execute the Query by clicking on the ![](https://lh7-us.googleusercontent.com/F7sPz-OLgqcZ0YmYH0kaoXTcNm1JIwaPEd968UiswMXz5WR2LgKYaeIEJBZhIElPNum_ANoEepPxymbwZcfTOTe48HTWnN9sCDQ58TwVcxqR9usErFsnIQh_09Bd8gsakkqIw4Nomux89w6wAoARIhk) button

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

![](https://lh7-us.googleusercontent.com/vlHIFz105afZ5aAFk6IecZP8CGtjTInLVSEunEraNrzeXbsPu-wj_uRWh4eiCE4G2yKiRpDCSvENrrSvj8pMjej68HQCu-_gbkUJ46XJP0-gFHA22mevHHfLUwCugG-gx1_dhRcAEpsHNBUcDhwF4No)

- Instead select (highlight) the statement click the ![](https://lh7-us.googleusercontent.com/EHA4EaC8oLxHQCl1_ZcYY-kUUovP00AMDw1_M6PLUJT6FDgYIdwj3CRj2iBJIub4MH09778SBCv2SRX9SSZquJCvSvpnsGNdtK9au_838YG5t5_0H_6lKfHhxa0ReiO9rZS_stfVrq7IPswm9Uoamis) button, which is right below the Execute (![](https://lh7-us.googleusercontent.com/F7sPz-OLgqcZ0YmYH0kaoXTcNm1JIwaPEd968UiswMXz5WR2LgKYaeIEJBZhIElPNum_ANoEepPxymbwZcfTOTe48HTWnN9sCDQ58TwVcxqR9usErFsnIQh_09Bd8gsakkqIw4Nomux89w6wAoARIhk)) button and select Explain

![](https://lh7-us.googleusercontent.com/EHA4EaC8oLxHQCl1_ZcYY-kUUovP00AMDw1_M6PLUJT6FDgYIdwj3CRj2iBJIub4MH09778SBCv2SRX9SSZquJCvSvpnsGNdtK9au_838YG5t5_0H_6lKfHhxa0ReiO9rZS_stfVrq7IPswm9Uoamis)

- In the output notice the amount of data that needs to be scanned for this query (it would represent the volume of 1 years worth of data - about 139MB).  Up to this point the data was loaded using the Partition of just a year.

![](https://lh7-us.googleusercontent.com/QWlXq1Z80_eYqwPVxrij1KgxiulTaL0vgiRJzxVFtX4sRPtdKmGnU2u0sFVwtUtmZPB00_QnlmLit0zB6fJL8qsfEJrNV6Z0J3owDakX1Abkhym1nAI_8zKkxRCN3Fsv5JgWr8QNQYe8YebSx4Uw2Us)

- Copy/paste the following in the Editor, but do not execute the query

<!---->

    SELECT year, month, count(*) 

    FROM ${user_id}_airlines.flights

    WHERE year = 2007 AND month = 12

    GROUP BY year, month

    ORDER BY year desc, month asc;

- Instead select (highlight) the statement click the ![](https://lh7-us.googleusercontent.com/EHA4EaC8oLxHQCl1_ZcYY-kUUovP00AMDw1_M6PLUJT6FDgYIdwj3CRj2iBJIub4MH09778SBCv2SRX9SSZquJCvSvpnsGNdtK9au_838YG5t5_0H_6lKfHhxa0ReiO9rZS_stfVrq7IPswm9Uoamis)button, which is right below the Execute (![](https://lh7-us.googleusercontent.com/F7sPz-OLgqcZ0YmYH0kaoXTcNm1JIwaPEd968UiswMXz5WR2LgKYaeIEJBZhIElPNum_ANoEepPxymbwZcfTOTe48HTWnN9sCDQ58TwVcxqR9usErFsnIQh_09Bd8gsakkqIw4Nomux89w6wAoARIhk)) button and select Explain

<!---->

- In the output notice the amount of data that needs to be scanned for this query, about 10MB, is significantly less than that of the first, 138MB.  This shows an important capability, Partition Pruning.  Meaning that much less data is being scanned for this query and only the selected month of data is being scanned vs scanning the entire year of data.  This should result in much faster query execution times.

![](https://lh7-us.googleusercontent.com/dQKhFIvhbSeDUQ1k_Es3rsyFtQAeGUbz3c0aPfoLEwclvV8jGanowuZVnN6BtdUtSD1BlPFUTQ67t3-GKHX0X5fyPlRTJvcWWuKdB3Crf6rr2Q9r3bdSoa7F79CEFp9utZ0p6wWcl7qFDcgA6RNnI1A)

- Iceberg Snapshots Time Travel - in the previous steps we have been loading data into the flights Iceberg table. 

  - Each time data was changed in our Iceberg tables, a Snapshot is automatically captured.  This is important for many reasons but the main point of the Snapshot is to ensure eventual consistency and allow for multiple reads/writes concurrently (from various engines or the same engine).

  - Show snapshots

    - Delete the current query from the SQL Window
    - Copy & paste the SQL below

<!---->

    DESCRIBE HISTORY ${user_id}_airlines.flights;

- Execute the Query by clicking on the ![](https://lh7-us.googleusercontent.com/F7sPz-OLgqcZ0YmYH0kaoXTcNm1JIwaPEd968UiswMXz5WR2LgKYaeIEJBZhIElPNum_ANoEepPxymbwZcfTOTe48HTWnN9sCDQ58TwVcxqR9usErFsnIQh_09Bd8gsakkqIw4Nomux89w6wAoARIhk) button

In the output there should be 2 Snapshots, in the example below there are 3 snapshots as this example shows that data was also loaded vie Impala and not just Hive.  Also, keep in mind we have been reading/writing data from/to the Iceberg table from both Hive & Impala which is indicated by the () in the callouts below.  This is important aspect of Iceberg Tables is that they support multi-function analytics - ie. many engines can work with Iceberg tables (Cloudera Data Warehouse \[Hive & Impala], Cloudera Data Engineering \[Spark], Cloudera Machine Learning \[Spark], Cloudera DataFlow \[NiFi], and DataHub Clusters)

![](https://lh7-us.googleusercontent.com/wp-DRurqPVwaCkN0wk1nmxpcJp3-gnJi4_ozg_SohcihYwWO0r_8py3YnzoshnL9cTPZp1NMSwdwUSCvmqPVMmIiQdSpN8llZpXdi8KTL8ws9YTZN6VZYT3_Ar9NLNxUmz2KPsFs3CXjgiZvxOfztdQ)

- Get Details for Snapshots - open a text editor/notepad

![](https://lh7-us.googleusercontent.com/KFkLAUfBELDyQyat3Ihctcow07AHgS7BYDzH8IQOttjJ5XsKBC-rpwMPJFdQ4vuVMYA6ysJyVVpCmsaNW6-EKFAzsQFcVkZ0NhsSeCR2CNqwMvzhM1Qb5nKjkU1BiO10yiBL3MJWCZ05Ge1zXj9PQGU)

Text Editor - copy in a couple creation\_time’s and snapshot\_id’s

![](https://lh7-us.googleusercontent.com/1lCRGNRqrGUSCHeAG5LZvDvUO2mihd0i-CKM6R519yTpqJdkGFwe07H3Q3ZzqqCoXvK2P-TowMiOXv8tbSNxS-p4imrljhJ-AT7Tg9VlxmSGC1Zgy0Cp6xr50XF-3qlbNUr8q8NvlVkoSiaCng8SECs)

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

![](https://lh7-us.googleusercontent.com/bZujbI8a89RoH5wrWCc87NhRbz6931l4_VO9N58_HQNqNOtWRhwG-dk_eT_gIqr_bdjVijx6NVNwobYsL__Qd2KzWq0nXVH1X6Cse1UeqNp0XLV0yDMqniV6zcQ_uPm1C2ptdCGFKs0ozou_ebgsb84)

- The first SELECT statement will use the create\_ts

  - In the create\_ts parameter box enter a date/time (this can be relative or specific timestamp).  From your Text Editor copy the second entry under creation\_time, paste it into the create\_ts parameter.  For this Time Travel you can use relative time periods and don’t have to enter the specific timestamp for the Snapshot.
  - Highlight the first SELECT statement, and execute it

![](https://lh7-us.googleusercontent.com/uAIHF891bDv-FN8HwP9vKIsfhi3O-oIYzwuw_ZG4HG2d7x128p1VxDIbyendYkZ1B3HaxrH7SsReZTt6mRI7Zz49KQLzhGvFp2KrRYbzBsEkwX-XNx8AnfGdTD6KXlw95iEeOYAjWtQMvkapL-wvoiQ)   ![](https://lh7-us.googleusercontent.com/uAIHF891bDv-FN8HwP9vKIsfhi3O-oIYzwuw_ZG4HG2d7x128p1VxDIbyendYkZ1B3HaxrH7SsReZTt6mRI7Zz49KQLzhGvFp2KrRYbzBsEkwX-XNx8AnfGdTD6KXlw95iEeOYAjWtQMvkapL-wvoiQ)

- This returned the the data as it was in our initial load 

<!---->

- The second SELECT statement will use the snapshot\_id

  - From your Text Editor copy the second entry under snapshot\_id, paste it into the snapshot\_id parameter box

    - Highlight the second SELECT statement, and execute it

![](https://lh7-us.googleusercontent.com/b-agGFOGZ13LTsJq_iSBTNPlhwPueibHGrXkaexZzFbaJ3rCPxewAHAepputNZyqWUS9ALTf5BGKX8M3fCHy8n6XPfvC7QI-LIvIcUQfNXUKUlJMgHPod1WkseZI-J0anwL2x--H6I7ncXqKVSF9BGA)    ![](https://lh7-us.googleusercontent.com/b-agGFOGZ13LTsJq_iSBTNPlhwPueibHGrXkaexZzFbaJ3rCPxewAHAepputNZyqWUS9ALTf5BGKX8M3fCHy8n6XPfvC7QI-LIvIcUQfNXUKUlJMgHPod1WkseZI-J0anwL2x--H6I7ncXqKVSF9BGA)

- This returns the data for the specific Snapshot ID that was specified in the query which was the data for the initial insert for data up to year 2006 and the insert for data for year 2007

<!---->

- Security & Governance - Now that performance has been optimized, we are almost ready to release this to the users.  Before we do that we need to apply security - Security is always on and can be defined with fine grained access control.  **_To learn more about Security & Governance in CDP - work with your Breakout Room Moderator to schedule time to go thru the Optional Lab at the end of this document_**

  - A security policy has already been created.  This is how it is defined

![](https://lh7-us.googleusercontent.com/7tlyPHkFP8Ze3T0rMrZ5FXh4b-X-_mTiFLZm3d_ZcTpG5GPZ0GAicM15IdpDLreYKZ12QH7hPwt1BJFOSLOjJfSXv_EWjVq_JEzJJ2Vz6sD3jkUYpy0nPFSdGHoCQ-4TqlbLMPVKRDNeD0ASThcF9dw)

![](https://lh7-us.googleusercontent.com/EP3OvwExeFfBWLYYERBeKNulNgfMeyC_y_DuMAeBoE7FNJ7F5mqnAelqfEzWwu-Pu7GhBzOcqGokzX1EesMCcBiGSoZqDFXBdWO318g46lpnp26nkafL0zk25xgUQZqKCCfAZn2612omufAafnOYsdA)

- Delete the current query from the SQL Window
- Copy & paste the SQL below Select all of the content in the SQL Editor
- Execute the Query by clicking on the![](https://lh7-us.googleusercontent.com/F7sPz-OLgqcZ0YmYH0kaoXTcNm1JIwaPEd968UiswMXz5WR2LgKYaeIEJBZhIElPNum_ANoEepPxymbwZcfTOTe48HTWnN9sCDQ58TwVcxqR9usErFsnIQh_09Bd8gsakkqIw4Nomux89w6wAoARIhk)button

![](https://lh7-us.googleusercontent.com/Fg227jUjKYT-r7-sd34K217t44Cy-ButeYywJyHEwOVp2T_-R61l1duFo8uQJip50luSNH_9JPcsVasJpXtDPaiwi1he6z1LXXER_jJQ8EbcKQtlEbTrQ4uz6mcVVg-9v00knjjaaqL0UlRyoCIAo20)

- You will see that the “tailnum” column is masked so you are unable to see the actual plane’s tail number, instead you see the Hashed value of the tailnum

***


## (Optional Bonus Material)

## Optional Lab 1 - CDW Tour

In this Lab you will explore how to take advantage of CDW.

14. Click on the “Get Started with a Tour” at the top of the CDP Home screen

![](https://lh7-us.googleusercontent.com/eV-p09JvPP2KRhdeEOKqIrC5fX8CEDgAmM1CoeHWD1CsZXYN6d2VfUoNuoAypUV9-j9vYieja7Ydloz-GAYB1Oa8Dr8iVbCC6IN-OaDs_8wjaHGjfIxQE2Bd2ePoJsHrYpcRQK4GPD-I3MjjdVRKA5E)

15. \[Optional] Watch the “Test Drive” Video on the CDP Home screen (video is \~3 minutes)

![](https://lh7-us.googleusercontent.com/y_ezSkAEXbdZTjZTxYi757EhtjeCTUJh3B-b954pHB3wSApV8NAdUtfjs4MMj0To6SUoxtW7Q8EA7HYJiGzgmlKPEikMHUtdnGaOfUbG95uQ7P32bd--Ir52ykugajo5LZ0cRlJ_ktFa1KfgiBEEyzE)

16. Click on the “Let’s go” button at the bottom of the video, you can take tours of any of the Data Services
17. Click on the Data Warehouse tour tile

![](https://lh7-us.googleusercontent.com/fOyE5DHBw_OXtNQTtVkEs5F6suK7QBCorpN8eQrP9pAIKbzh7IE_vcrzZWA0RH7cgYeaypwUwAzotVldsITAwarb_UtRuqjlxCsj_UZna0FuUjM5pBOWB550QAKRzgfqnLAw9rDSWthj32wTjC4e0DM)

- Here you see the content you can take advantage of - there are 3 tiles where you can watch videos on an area of interest, you will see a “> Video” link on the tile if this is a video, and there is also a tour.

![](https://lh7-us.googleusercontent.com/h7V5yuSEeA8KUW7vWg6c0iW0gKKTBmR15VZO5ZljYYP6GCFho6iDAahnTdry_oPQFXz9gJX-vPI4fc2d87xFuZPJpfBSUbypW9paJ0M43wuLQ0f6PsjSljOh6PSWmWzRdLK3mflKaSZPKtCzCYml2Vg)

- Click on the “Data Warehouse Overview” tile, this is a click through tour of CDW

  - Perform all of the actions for this click through tour (\~5 minutes)
  - Once completed click on the “X” in the top right corner to close the window 

18. On the Product Tours screen, explore the various topics to learn mover about Cloudera Data Warehouse

***


## Optional Lab 2 - Self Service File Upload

In this lab you will learn how to upload a small file to run SQL queries against where you could join to existing data in your Data Lakehouse.

19. Upload Passenger Ticket data file

    - Below highlights the 3 steps to upload this file: 1) Open the Importer, 2) Pick a file & options for the file upload, 3) Name the table, specify table options, and table metadata (column names, data types, etc.)

1\) ![](https://lh7-us.googleusercontent.com/NzrxrXBz8hN20vE-XDZ_Cc3Y4JyKM5l7tjJtZakRXX09gSy5ZAn2OIYtJVWwHCNSLvI0v8AksZ_6eEWtl4UtG2oXyjd9LkfAqntW8lViLpK2Gwyvter_0n2iTWJK-6zVdm5glCYDFNX_DrzOMoWRfhU)    2) ![](https://lh7-us.googleusercontent.com/EI7MJyqNc6WlwfPYW5LErtyWBT4HdVPTcUk4qUOrXL4W_NVkNAHUQ0usqFdinNANvSW3_BF2avnmMCoB5hYDpwB38BXlCWWFdpjl_bnuK5xM4ak_eWevqf2s98oGLM5-RizStFSjYL9Z7sYqFYG__To)  3) ![](https://lh7-us.googleusercontent.com/eJ2Y_KRiCDKLWNCWVt4YjrymXpSS-2FpQDA6iHvQxjjCKBaJP6O7snmTBWR6v42VmEXcI4L-P_gn-kG-NBZqmrM_VlcTxWfitt-zcDCK9v5r_foABk7RGmMQLGUZLkKpSPdz_GLu6GJggkn7fvotx5Y)

- On the left navigation menu click the ![](https://lh7-us.googleusercontent.com/BDnxzsQyGDZpeqgDIrWEHMyHIoZYfN12wxfjGAx7jgHqQlH7XVeP4CG7AOG8FhhFUs8y0oYzvZRUrf51Y2uzAsiKrB2VYuM7H1hbp-_F151VAmJqZx7KC-vGoexKduPbyBhvxxaMmW--quNF5tMYipY) button, and select Importer

![](https://lh7-us.googleusercontent.com/NzrxrXBz8hN20vE-XDZ_Cc3Y4JyKM5l7tjJtZakRXX09gSy5ZAn2OIYtJVWwHCNSLvI0v8AksZ_6eEWtl4UtG2oXyjd9LkfAqntW8lViLpK2Gwyvter_0n2iTWJK-6zVdm5glCYDFNX_DrzOMoWRfhU)

- On the “Pick Data from Local File” page

  - In the Select Type, choose “Small Local File”, it should be the default value

![](https://lh7-us.googleusercontent.com/cLdtP1q-bfpz8OvQ8tBDPeLUbCaivwAbeP-0dbYESICOLIM_JjrxhcC3qOzKiKaouOKKNjgx54aCcXW8WGH8S8nD3oE8TkHiOlMAX3io_KF3z8v_3x4YlxcsP08WWDtjccl9mFF8BfSMffSPrkQI618)

- Click the![](https://lh7-us.googleusercontent.com/p-GrwqkBUZs2miT-IkVLRQ3aA5sWZHCP9ztx8AE0arg1m38RnGcXZhVVW32Mw0VDxLb-pEdosCvEUvPhAOsjXrNVAcHmtbOIXOEpCFjp86EbvLx0GDZ7v1s1MNpKoArnKnxuvCvv_2NxlAUP_T8AgTc)button, and browse to the “passengertickets\_1k.csv” file

![](https://lh7-us.googleusercontent.com/EI7MJyqNc6WlwfPYW5LErtyWBT4HdVPTcUk4qUOrXL4W_NVkNAHUQ0usqFdinNANvSW3_BF2avnmMCoB5hYDpwB38BXlCWWFdpjl_bnuK5xM4ak_eWevqf2s98oGLM5-RizStFSjYL9Z7sYqFYG__To)

Ensure that the PREVIEW looks good.  You could make changes to the CSV options or import other file types like JSON using this Importer

- Click the ![](https://lh7-us.googleusercontent.com/cNF_9VS4z1iA5lgPK3bDjQyhxVIoKu_v_jj1OOy6zvM0oyoaU5tlOqb-kx104EBS0tGf8Kt-63_xK0OLn7vIM5MpzTbih4YBlSmeiSpn_Yq7oGltGvBGE_mfG3bm4XmQvyJ9d5mVrokuTZ8xlstShVM) button

<!---->

- On the “Move it to table \<table-name>” page

  - Under DESTINATION, change Name to **\<user-id>**\_airlines.unique\_tickets (replace \<user-id> with your user id you logged in with)

![](https://lh7-us.googleusercontent.com/eJ2Y_KRiCDKLWNCWVt4YjrymXpSS-2FpQDA6iHvQxjjCKBaJP6O7snmTBWR6v42VmEXcI4L-P_gn-kG-NBZqmrM_VlcTxWfitt-zcDCK9v5r_foABk7RGmMQLGUZLkKpSPdz_GLu6GJggkn7fvotx5Y)

- Under FIELDS, change data types with “bigint” to “int” for all the fields except the “ticketnumber” field, it can remain a bigint data type

![](https://lh7-us.googleusercontent.com/Fuxh_qEso0TZCJa-nSb0OAFtbKRg5rvVF0c9gBxwdybLHpRzGB2Qmaut6SfPTxY3FxXu-IaPlHN1PFsJri4CSrl_qcf-oCHkb_SL6bPakbplxIh8WbQmdYn31N8S8trD6B-KHDmIMQZd20DYxpraHao)

- The final fields section should look like the following:

![](https://lh7-us.googleusercontent.com/6FZo9Yk9pw_gEe16P_kWjHwrIlukV2hYPl1AsVirzBVlsYkgrJ5hJCdPJgMVlS7iNWkU86stva733KyCeHiL0mdoy1f5LD6ag2SFcDuOKkyPUVQzKMVJoaSiaGx7qjEZHLK9PFD46oCwGKuc-g9GrGc)

- Click the![](https://lh7-us.googleusercontent.com/Ke1PgrUu_64OWo-PuBL8BibkzxvlbEJg3xyjvPQVA5vWlW0bcXCkZNL3edwmFYwDPfiyx1RKiVDzANNHsfvmLfR5HaVfcr4VvB6u5M1YHFQxsGURmhghWU2PNbgsKyj1J81P2ATej9jV9TQpo8dcvQk) button - this will create a new table in your database named unique\_tickets in a Hive table format.  Later in the labs you will learn how to migrate this to an Iceberg table.  You will be taken to the Table Browser and see a status like the following screen (top right):

![](https://lh7-us.googleusercontent.com/LYwsQSTU1P1KFeitfqEEvZFY9EuLTARj-fy_f-kchNVZvN5Cd0ZzJbq6yyVn4fRgTVdGUL-Tkb0iDDpKfQDiHv-FWVBkTboLN1lXHO0wmxDSD0wpH3quHUoQnRltEsfp_vWdpdlXxFIX-lgth5AikqE)

- Once the table is created click on the![](https://lh7-us.googleusercontent.com/1PVPpABt8cPAzwGodTh_dvBFaQTY-Shvm5nHUtnZwXa7M57I88OTBXlPQT6-UezxoSLY7FAFmJ8jR17zYHJfGSleL0Fg7Guxg3KC5jrI-JHntxjCUW67iLMzGMxGg8zK4dQnYKICv4SVaByxGoDUK0U)tab of the Table Browser to see the table type and other information on this table.  The following highlighted pieces of information show that this table is a Managed Table that is in using a SerDe that shows this is an ORC File Format & in Hive Table Format

![](https://lh7-us.googleusercontent.com/UyTbF5I1f_YS4dZls9WZnHAjsHo_OD6V6aAcjJfYNjGvzJs17A41CrZrbIi6_46XN4tBrMLvg_4epK0Voz57ZbKzY_5QOnXseTXqe746Nzf0r1LHU2EaHG-lJdwTJL38D_AEHweg9dlIdmJGf7czOG0)

- You can also view a sample of the data in this table by clicking on the ![](https://lh7-us.googleusercontent.com/UyTbF5I1f_YS4dZls9WZnHAjsHo_OD6V6aAcjJfYNjGvzJs17A41CrZrbIi6_46XN4tBrMLvg_4epK0Voz57ZbKzY_5QOnXseTXqe746Nzf0r1LHU2EaHG-lJdwTJL38D_AEHweg9dlIdmJGf7czOG0)tab

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

![](https://lh7-us.googleusercontent.com/reewaK4DgV88EFYUTA9xrTS_nHeB8vjZxktTOB6dvrJCa8AV1UNGFbhqUY_M8fK3jfwhGFLBDSUAYbae_vdx6N9V1b1IP3YUZa0BkhwYStdJlYT3ZZ2Sntisbs30lhQe5Q0-GRMO5YNgEp4_xFzKXx4)

- Let’s take a look at the Query Plan that was used to execute this query

  - On the left menu select Jobs

![](https://lh7-us.googleusercontent.com/v3fASrTt4rgXWMxaOR114og5wDgYUUCHmlj1Glo-03ZkJOUr2Z_L-XKIZWp0Zgz40X0IgYmSWEMSohnYQeugN6ynBxlFlmyQkxsQuk-46HcbwjYYXPI9MypGYQV0UZw2GK1Rpq3Swf9-aohgY4MtPCs)

- This will take you to the Jobs Browser, select the Queries tab to the right of the Job Browser header 

![](https://lh7-us.googleusercontent.com/xRwgws_Jz9ihPdOSvOoMQdEUUwHutEkOcevdMlgy46d-jY0xQ5Akr7CQPSMIP42cCeuNzb4F4rxSR0IVPzVZuR815bN9y-z8Jq1nASxGZMbuGVmZr7pDYEm-fXx8PlupUVgzbFOz-WXQUahwqKVkvLU)

- This is where an Admin will go when - a query has run amok and then figures out what to do next.  In our case for this lab we’d like to look at the query we just executed to see how it ran and the steps taken to execute the query.  Administrators would also be able to perform other monitoring and maintenance tasks for what is running (or has been run).  Monitoring and maintenance tasks could include: cancel (kill) queries, see what is running, analyze whether queries that have been executed are optimized, etc.

![](https://lh7-us.googleusercontent.com/_-kuMHDq3-bKF9OCDlmSrzxXXW4aXjSbpcZ1b-AHt9185O7FFdcYp7X6Ol3DGyh0MtOV1whHFFQASwdSnQQfLrMFEgxmqv8bO7z3mroTEqsm6Y1scOI0ybKFTx_auEPCwHYzjvXnEspKVPPgn0Ej7cU)

- Hoover over and click on the Query we just executed (it should be the first row)

![](https://lh7-us.googleusercontent.com/SjFBw140BJ5C2O8KxR3GjxTdSQMDBYsNBpfm7z6sK0hlP-bHLGf3-YLp_KtRByycrBTKN8rs2UL4is_NkrCtyn0Tto_pvjQhGr1PLcRkE98OyAs9f9_9YivU3fDokuzslvuzOT5S5lelzMOoJTK2khg)

- This is where you can analyze queries at a deep level.  For this lab let’s take a look at the Explain details, click on Visual Explain tab

![](https://lh7-us.googleusercontent.com/wUoXkVHpv5jPb3ntai2RWrH0F9VB7_HlrIIJJL2O1ZyoToX58LYC3TbjC03Jy4QYAMySYhCdLtWjmIRt3ladLGwxX7YLRvWyC0ZaesO3wHy8ltxUGNmHyNoVHJYh6HpxP6NfQML34dUoeqqp93TVwBg)

- This plan shows that this query needs to Read flights (86M rows) and airlines (1.5K rows) with hash join, group and sort.  This is a lot of data processing and if we run this query constantly it would be good to reduce the time this query takes to execute.

![](https://lh7-us.googleusercontent.com/c9mCWEreKGm3E4Q9vSbisTloYqp7OhqV9HIBIL9fvBCnKpcD4keTkKRFqS8_sxYH7DYYoqVu4aBlIT-k-b2QoO0yP0Uh_sm76g3QGRVUQBIJtLtJCc9Ne7pljVY4F-55Zg47v0TeEMiJJh3pOGgF7kg)

- Click on the \</> button on the left menu, and click Editor, to return the Editor Window

![](https://lh7-us.googleusercontent.com/Kcyxsc-bApMzN2955HxYMDT4X3ZrTuYEMiABK0g1-X_Lmni1HW1bAsRkoczn8ZSR0zdLqbo3mYnjA8Oe66hCc5yXkUt3FyPns6yc5_F-FmlfQxKnG0EneXSJfjNxPWqdT1yYIoyYKUfmZOaqGvH_Rr0)

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

- The Materialized View traffic\_cancel\_airlines will be displayed in Results and in the left table/view list with a ![](https://lh7-us.googleusercontent.com/3sn86Co-FDL7d2Cf2BIm0EfhDAh-9soQgVXLzep3IPM08XGU9vwDK4qAAomn1jOokxeywnzFIgU5pBeXMgP3l54rua2XfCZrEd5upzU3REUul3aJNY6XIwK0eXLgudTHHtpefxW3Yq0b_QXR_KrB2Eg)(View) icon to the left of the MV

![](https://lh7-us.googleusercontent.com/YEWwXkiTy8Eq9drphpwwWBEdXpYbyJvRUJ5q3ddS6fXrUnv1HV_By_lSK69drwHyccWhrDR7QA7YQq7yizgzlto5PPIYo0p3neaapIMQA1XBR0rYSWQvsO50ky9T0-hJk4GKM4tkmt-eJxYtoXYC2XM)

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

![](https://lh7-us.googleusercontent.com/BtahVrqx0jgULKwuEXIn0sbwXnbEcLXV3eIqWCO_mesoTvpJKiTVvjBUcpO6LZJWaLx0SkXsQdK97raK1VK_tx5ScAuiZUcUR5DE96BoQlLavdvSPhfq5gN0q3deDp_x70BcGrEfHnk0LfCDt6WiDKA)

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

![](https://lh7-us.googleusercontent.com/vnYIZNRGUOB6Ci8vuqOGETSFL3b-M6Z1sotomsraEVN0JuWJhKtnfd-McXc0ZEe0KYh3qEnX24moxStpoz0I9mhrCiwM4_ebtmV2G-ntE5C3gjd7knUjgGyL0JSxfke4RAQFeNDqiqtYQoXmZY1Dk44)

- If you see the “What’s New” page, you can read it, or click on the GOT IT button

22. Home page

![](https://lh7-us.googleusercontent.com/R6Aynn26kQDvpGK7fS_FpWWSaqnoGNnGL6BF4t9ZBE3SOicUgkExTObWwOATEGoubmQ6bcuUfFVdgr-UYrmhlC2hI2fUeKJ9lbhKI3tC2w2Ydm4VeltSjm9OreqHU_uSB_XFQ5PJvzLSiZWQ6wzSUI8)

- There are 4 areas of CDV - HOME, SQL, VISUALS, DATA - these are the tabs at the top of the screen in the black bar to the right of the Cloudera Data Visualization banner

  - Home - this is the starting point; it shows some statistics at the top, followed by some quick access details to recent content - Queries, Connections, Datasets, and Dashboards
  - SQL - allows you to manually build queries against data to perform quick discovery against the data.  Below is an example of a query that was built and Run

![](https://lh7-us.googleusercontent.com/Be16nvD2BMfxRxkjhNL0AcR4f7Ehyb582lKA88rU02HV8i9RZXUPOe1VeqKfs0gMGJBb86H3bH0yJOHXBt9rmB6WS4bYS4g69UYm4LoSzc7OA5SOuuTAh0icpDyXl2ZCH2F2ueROUMIIH-QagbqL00s)

- Visuals - an area for viewing/building/modifying visuals, dashboards, and applications

![](https://lh7-us.googleusercontent.com/UuGIg59VJvgZX42d_ixuEJ-LE1in9ZwjH6ed_1NEHPVgchmDv-lZyFDRN9BjGpTlG6CR-zNKnV_HwLjyW9XzsuPzR9EAUYnq7kyqUYgyKjukhqzSpJaN8JvT6WXk9woiFB3DTWFH9Jcd1Y4zpRR5gEk)

- Data - interface for access to datasets, connections, and the Connection Explorer

23. Build a Dataset (aka. Metadata Layer or Data Model) - click on DATA in the top banner.  A Dataset is a Semantic Layer where you can create a business view on top of the data - data is not copied; this is just a logical layer

![](https://lh7-us.googleusercontent.com/QDTMWKtUdBttNGuOLtbV5RspCz664QwjIpYaboz6mekihdgB69eY6VZ_VXH6IzIRwkpJU-5vZcsFwlZuqev2yJcDEdjXdkGRRUOr4tZpSICzA7p5K_4WB72lQSOXLx-bBrOLdctzeoiSwVV80m0S7_c)

- Create a connection - click on the NEW CONNECTION button on the left menu

![](https://lh7-us.googleusercontent.com/9AthitSFEsTJ-N_djaA9qYfQw0goGO0rje1wjcWzZ8inHZBx6BYvTVUhTkK8Vx-50Sq9y_5sd-NkgiGVACneao488cVZwQ1_WceFqZXP_0poOnA98dSiituPSR1CggO4ZI0u1htc76LN5Xj9RPIZDpk)

- Connection type - select CDW Impala
- Name - **\<user\_id>**-airlines-lakehouse
- CDW Warehouse - select drop down and pick the airlines-impala-vw
- For this lab each participant will create their own connection in the same Data Viz instance, this would not be normal, you would only have to create a single connection to the same Virtual Warehouse
- Click on the Advanced tab  in the middle of the screen, you can see that the details are already populated, there is nothing more to do.  If certain settings were required you could change them here.
- Click CONNECT button, to create the Connection
- You will see your connection in the list of connections on the left menu

![](https://lh7-us.googleusercontent.com/mo5kMy7dZVDNObJAfd0xp3ONAJptixEE_tL7B8mrdbpKUrFrVj53fYY3Qvn_Zl4QsDwAaOKT6EiF2y-9bIvlyUqv7IAvo-mcH7_UwKvr2mCrAz3kgeS4VlXTJ-VkOzBxtExGcBHPr_ZBmsvx2S7VGQ0)

- On the right side of the screen you will see Datasets and the Connection Explorer

![](https://lh7-us.googleusercontent.com/zr3_FFstffaLWghUJmDfZhUxwVLiEmfgxuyHsRYx1u8xarCzRU8QFRKoDLfo-2P4Uow9Sj947F0xDDRqDKJXozaBdVZ58hKn7kinLlbuhmtc6trFYCV6Fsl3cPqRG4e6qxQ3HUeSWPTYVrPvDHkvUaE)

- Create a new Dataset (aka. Metadata Layer or Data Model)

  - Click on NEW DATASET button

![](https://lh7-us.googleusercontent.com/pOxcuXdqEuTV06j7HLOhHtk8cHuESImthlw8QVyePuNqgv7UnVF0CgETJer631VpNWMsuEg7q32xe2WjC8-yjbPPLJCqCHq5QOw4HuJcmixy8GfIF-m9gFgl_BNSfD2UqqhXs_u-nn6aXYiHbkVmzj0)

- Dataset title - **airline\_logistics**
- Dataset Source - select From Table (however, you could choose to directly enter a SQL statement instead)
- Select Database - **\<user\_id>**\_airlines
- Select Table - flights
- Click CREATE

![](https://lh7-us.googleusercontent.com/t71fxFMHPRZHL0b15Qht41nrnd1Sc2lSyV_CHr-8SoUsbUVyiUJGoXlXgCh7pOYlFGOOtk32Nbnz2yR_Urmv3gIArEOx7pJJeGqKmnuwHvEHLVYXMJuS1Pl0iloxvvxeMjLZwkB0p2iavwJ3MwSVG7A)

- Edit the Dataset - click on airline\_logistics on the right of the screen.  This will open the details page, showing you information about the Dataset, such as connection details, and options that are set

![](https://lh7-us.googleusercontent.com/i60PaSw091QRIO3H3PGTAigLc3T6fzMmWVHDMnInnhqpxLKVEdhnKku5iP2tlJ8VMUyjU6CN4y7z2p-tfO44NfCjrqFqksAVgt0BZoducbasoB4g0C01w9vV-mCb--LC9WxbNGmZU6ctPjM_LmNFhZ0)

- On the left menu click on Fields - let’s quickly see what was created by adding the flights table to the Dataset.  When this table was added it took the table’s metadata and add the columns as Fields.  (we’ll come back to this later)

![](https://lh7-us.googleusercontent.com/gb6QAWWltjsIJQcyNWzo5qOzzMK3MjayB7wFlUr45GyMPP2ibiQUi6eFdMELvSci-PIcDUHsOn8zM57gymmlqWCL2m1B-aKvUvhat5Y0gsJYiUXdtGY5cHQgDp534HFShyejqhqdHBosVuuH1xJbP74)     ![](https://lh7-us.googleusercontent.com/wpFTVKMwRwFCEcf4ae7kNYZkrW2kVu_5Hz3D6HcjP2H5IufUGs9bNHu5N70yjmslx4xwKXNG3hW7e1ilJAoBQ_yf0KobO6eaXEnBNG17TbuMzUIqt6SVyaqbuJzVWstTmbweALEgJ87BqnIsOLhwqnU)

- Click on Data Model - for our Dataset we need to join additional data to the flights table including the planes, airlines, and airports tables
- Click on EDIT DATA MODEL button

![](https://lh7-us.googleusercontent.com/eVvoIUG5N-aCl4GkE0UMzG9COmg6t46ukXDHIamyJrGP4Eqb3hZTGhWE8MojZJvh5DQXtJkTs-HFfXj-2tbA68MZdLd0BUg7EbYAw5fU0bo0kZ9ALNknwNpTTQhzBf3VQDGoZ5aJhdMEw2G0HWnOh7o)

- Join planes - click the “+” button next to flights

![](https://lh7-us.googleusercontent.com/gi65qg7SCUoUNQqAi5Ic0GVneNrdhVoqwpPb3e5CJvH83eBgRjS2_11JjPu37C5qDJSZoJJLJsgdW3JIf18ijZbs0qobz33RJydEiMUOrq1lK45uLPbv8L5KROaZOGD3uCr662TLj6arRNVhBM5y5O0)

Database Name - **\<user\_id>**\_airlines

Table Name - planes

Click SELECT button

![](https://lh7-us.googleusercontent.com/AuSaNFwfjXQqzy0TbSrZcuvHhLpR8IST4LyUjjU4Dqm6zMG0G2gA8f7de45htDaGgBi5XtoaGJIv-Wx2g1aro0VLCENG3bRp9-U1O9tFS_E3IPgSoz8pWE1HgcTjiP4vToGqFarVyl_taWgCdPq1Aw0)

Click the ![](https://lh7-us.googleusercontent.com/mwQJfn0UwwMwjGkWxLwkJjrprydHvTCJD2XDdj302v4d0U_QLbqMZKrmOLsNCarv9VYrFNhdXP5rX_1lvunRrU_K03kFzw8jLsSbCShOHCV1updpWUumGwPwsHq_BIHTji55_1H36hF7bUjPicatpUU) (JOIN) between flights and planes to see the join that was created

Click EDIT JOIN to modify the join as there is an extra join of year=year

Click on the - to the right of the year=year join and click the APPLY button

![](https://lh7-us.googleusercontent.com/7jwpg8SgpS2YDBJItZd7v5Arg178CVNNRc9DAjHLQwZDeaFQ-vq2KBt6QZGPbdnKxFgmuHAndLktQLU93qLpsR4Y1ckmweH4mweA-KP7TszfmQ9X1LaAsAP0OpxcUSBWqL8q9MRSAJnI6W9RTEyEX0k) should be >>> ![](https://lh7-us.googleusercontent.com/MkYHWd0LEgmCg2-Cy4dTla0ViHfP37hzpHvfn6xSSRP_SpJAbCZVG5u38clb8yD6R8ufGdYixGc6_g2FGEUptEUHiSSig6hob2eiBTd083F44D1neOccGX6ULCRwhC0lyTcIz3RzYMFg_u4CzLB7KlI)

- Join airlines - click the “+” button next to flights

![](https://lh7-us.googleusercontent.com/E6VA88lJnpXU0KwBaW7HxxVAJ1iQIz7o2ZBf1jWBmIu-1GDXBaV3-qfCL6W_bAXIbbj5d_fNZqfmJEM2APndjUGtlovMd34y-0riorl7giF8vDeYp7iDzHe13Pnfy8m0z7aBqYRTJrgdQDXTHh9-R4I)

Database Name - **\<user\_id>**\_airlines

Table Name - airlines

Click SELECT button

![](https://lh7-us.googleusercontent.com/l-dlulZhdGuq-jNElArAKbJACT2-Rz-3xNU1nPbQgnOXI3w1YXhuAtnDfaJwQ0y9jaRHz-7DDmzZ-EL6nopurLfOcCQHwEuCzij43BujrtbBEeNjYoTKCNMs3_IFqmsO7OfTgz6_iHvM5xBeJiTXfn4) >>> ![](https://lh7-us.googleusercontent.com/A3DRUQ3U8UPCGD7z4gI0mYQGKTCLb47BqXetEYhexTBdvPe_rNrrOKzPubieKK56F5VADPvU2umVt25ciERErKRUVX08iV8YoIvo8DVg6lOR7NQeMeRbHFjEo2fPM9-h94X6owvmB0TuIrWKbf9IJ58)

Click the ![](https://lh7-us.googleusercontent.com/mwQJfn0UwwMwjGkWxLwkJjrprydHvTCJD2XDdj302v4d0U_QLbqMZKrmOLsNCarv9VYrFNhdXP5rX_1lvunRrU_K03kFzw8jLsSbCShOHCV1updpWUumGwPwsHq_BIHTji55_1H36hF7bUjPicatpUU) (JOIN) between flights and airlines to see the join that was created

Click EDIT JOIN to modify the join

Click on uniquecarrier under flights & code under airlines and click the APPLY button

- Join airports (origin airport) - click the “+” button next to flights

![](https://lh7-us.googleusercontent.com/3d82wGlLrTb_t6CCUynzm1Qg7BhtPUKw0d37yVsBOE2yoZglZWYcsZ-UqX0_YsEAO3DtFs7jCtO-w_DTE6ArRW-kNEp_eg0G74fT6Nv72-oHtq47SuknY5Zyhnag7bhl7x_07GFnM5YHfp2nQnxof6g)

Database Name - **\<user\_id>**\_airlines

Table Name - airports

Click SELECT button

![](https://lh7-us.googleusercontent.com/R-JoDUURfdcDFzBD9sPw0_8d7WrWVUCxSGZqLHnWq9tbE_RpHo6ejd-HWv-cJqsv-_P6Tf4zwY-zHqVBcILRt2QCn9wtpKY7DL-u2jBYbbi-86g1toV4-nrVkUzPYAZNtTo0PjSEU6Wj5NJJ1ZHvcEY)

Click the ![](https://lh7-us.googleusercontent.com/mwQJfn0UwwMwjGkWxLwkJjrprydHvTCJD2XDdj302v4d0U_QLbqMZKrmOLsNCarv9VYrFNhdXP5rX_1lvunRrU_K03kFzw8jLsSbCShOHCV1updpWUumGwPwsHq_BIHTji55_1H36hF7bUjPicatpUU) (JOIN) between flights and airports to see the join that was created

Click EDIT JOIN to modify the join

Click on origin under flights & iata under airports and click the APPLY button

- Join airports (destination airport) - click the “+” button next to flights

![](https://lh7-us.googleusercontent.com/hzDBQuAaj7C0MM2_8mGiNOsrhMdRY0TZSK-xL5t_73BsJrKOt19x_2Scpzbn7wMgtq7uQv01NdN7pKq52_e_1_T7o9aAllQU5StpAJ9YpoI7hP3J6q6tFVnCJwejN-h7XCgzXUChiwgNoiqyGIMUa4U)

Database Name - **\<user\_id>**\_airlines

Table Name - airports

Click SELECT button

![](https://lh7-us.googleusercontent.com/KNUAspJnmbHAWQQf6_nQ5Lof9BOL9KQoWuxYl6LFYb7FE3QzMmWCbZsdPZ3cRzc_6oer56lNCjOisrTc3bGd-vEJxC8EEf3_YN1OcMAEbeJV-1Tq1IvL0OvwtizFGfz0gVWFt4EUPrN-AHG20XvOcPQ)

Click the ![](https://lh7-us.googleusercontent.com/mwQJfn0UwwMwjGkWxLwkJjrprydHvTCJD2XDdj302v4d0U_QLbqMZKrmOLsNCarv9VYrFNhdXP5rX_1lvunRrU_K03kFzw8jLsSbCShOHCV1updpWUumGwPwsHq_BIHTji55_1H36hF7bUjPicatpUU) (JOIN) between flights and airports\_1 to see the join that was created

Click EDIT JOIN to modify the join

Click on the dest under flights & iata under airports and click the APPLY button

- The final Data Model will look like the following…

![](https://lh7-us.googleusercontent.com/LJEmPSfl-98xZ7KKXDMx78Zk0HXJ4LQswSRD2hi3xBst2YbvwbasFwwRFfC7vdADqjB_cYOnaasONm18YAYJImvZn_dT8FCVgcpefcxj78PGLmITzSVrbRSMlFLGdrlEIWMpgWOgFyk5lcEdqQHuzZk)

- Click on the SHOW DATA button to preview the data that will be returned by the model created so far

![](https://lh7-us.googleusercontent.com/V6WAldsaGF2GcOd2AhLw_sRY0pcCtGdKvlY8nMDb9O4WnOeCEqMHmg6_f-ZKg8Ff2m9AR56hv09SvKP3-QNvZFVMy2MAn9yrPfATQIylstqNG9cCTmO3E9F77KRJfbBg8CoPemMA315DxkvL9556JuQ)

- Click on the SAVE button

<!---->

- Modify Fields - click on Fields in the left menu

![](https://lh7-us.googleusercontent.com/4lkWx7Ma1hq--CWBHcO9Jp4TRGkPRIxDPRrccSbbMf2nDkrUuRparhEG_MAqzKQhGHPEge9H1QZasv56YCsGlq1xY0As6R5SZvjNTtAZOLnAFceBKeGGptA5FMDRgF-ylMK90DRVm4RYd-2ZbVX03yA)

- Click on the EDIT FIELDS button; you will see this new tool bar

![](https://lh7-us.googleusercontent.com/jpVbIAA14o3wdBY2gl0IA3xNXH9Ls4NUmfusqMEuq-CN9dLW7cPJ2XkHDfRMOcxeyYlC7tJWKzuiTf_qQbiMfsyb0jvGlZBnbPnPPnNlmKYVVTUuxu3K_BGthuubR2tQzltEWCYTJjv66gFR9EeTEkw)

- Click on the TITLE CASE button to format the display names of the fields
- Under the Measures section, click on the Mes button next to month.  This changes this to a Dimension.

![](https://lh7-us.googleusercontent.com/F6tcoS_6D1kG8j_beSBSQVb0aD2UdZOoIXqgNa8OsyGDohRCHDptc0ImifCypnknOSTZIPyFXb-iMfDzya15x9lRhGdk7DGQotvgciZJ0aI_0WCtBsxRpAms89rXNZxUmXyi8u4DRdUMgj1j2ayB24M)

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

![](https://lh7-us.googleusercontent.com/z3-T2H4j6osMCvTu5tPrHLY195iStatiPPCNXiaHVb03cUOK3KZl8PlYN_6PUXLZ5SfS9WPNfU6J0csZ6U3VKp2vOaq71OMMb8gSLqvtnb0dV_yICTQccNbJjvsrTiSKI1U1iwL56tbud__vS2pSctU)

- Click on the Display Format tab

  - Select Category of Integer and click on Use 1000 separator

![](https://lh7-us.googleusercontent.com/j6V_lEGYg0F3q65ezxXxPJUcsFuSv0qOe_B2qD9m0CSPiuAP0Jydf_024FwlJCJ9mITBTyC6hkvJO83oPIuG5r30MVfOLRMzK7wbO5KO_5ryBdJEcw8d5wbDt-JKYk0vAoiOePZYnDGGkQRKYrIH9kc)

- Click APPLY button to save the changes

<!---->

- Add a new Field

  - Clone the Origin Field - click the down arrow next to Origin, select Clone

![](https://lh7-us.googleusercontent.com/kvGhMduFllSeTa54eeLLzyZo0Ef58ZawGu-lUh-q_38W6LChjl5zVQ12HVQgF68aj8DK38fCuoKGvSfkvHBgV5BSW09t8WRSBxpARSvkOSLxOpi4AAfNP_uBEFD7tG5IeQQqamOJElDbZ3XmT-FBKwU)

- Click the pencil next to Clone of Origin to edit the field
- Change Display Name to Route
- Click on the Expression tab - enter the following into the Expression window

<!---->

    concat([Origin], '-', [Dest])

![](https://lh7-us.googleusercontent.com/Uft5mCiFgMnORZkjLg0i07Rw7-tFm-3hg4RpvwKKy8CEx2fjnw8VWyxjoVEZvl9lOONZejkfjOxfAyNxt5_Laen8H0PIptsSyQvEuMAZ_5asfq-GD2wicouigOnZudB4M7pqDFzkFk7iA36LpDT-G3w)

- Click APPLY - since the “Save expression only after validation succeeds” is checked the Field will first be validated to ensure there are no errors then if it is valid will be saved

<!---->

- Click the SAVE button

24. Create Dashboard - in the top right corner click on the NEW DASHBOARD button

![](https://lh7-us.googleusercontent.com/UCJ1HpWDWP6Uh35Y1uplRo44ZKDupds7tSIghA5o3NFuFq7oRmHpvdaCZ7dkwMTJzYzVz7hQbd2gDlQDGos-9Sj4WUV5THr6MBLR7P_aW_iNICApLxDF_yg9y-de_oJ2lgGyf3OGxEDnQWbN72zbIr8)

New Dashboard

- Quick Overview the the interface

  - On the right side of the screen there will be a VISUALS menu.  At the top of this menu, there is a series of Visual Types to choose from.  There will be 30+ various visuals to choose from.  Below the Visual Types you will see what are called Shelves.  The Shelves that are present depend on the Visual Type that is selected.  Shelves with a “\*” are required, all other Shelves are optional.  On the far right of the page there is a DATA menu, which identifies the Connection & Dataset used for this visual.  Underneath that is the Fields from the Dataset broken down by Dimensions and Measures.  With each of these Categories you can see that it is subdivided by each Table in the Dataset.

|                                                                                                                                                                                                                   |                                                                                                                                                                                                              |                                                                                                                                                                                                                                                                                                                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| **Visual Types**![](https://lh7-us.googleusercontent.com/tdatYnAH_FI7FIjEFnhx7LsnZoNmrtB9j9OOKRFdY14R8vad0z3b0xD9yAhc6m0bfOwnJ8vCv7ULG8jC8W0rIrGsvLOnwn5iUkpg_luy89YB4u0yDvfMJZOVx3e9tkRHqei_s3Yb21tIPObNweJGBSA) | **Shelves**![](https://lh7-us.googleusercontent.com/wkvFsfIiTd9PX9KJyCLVoHzrN7oU5r7i2e_uHZcgDAd2iAlznJ76UVdg0EuK9x-SHuGgF9LV_JFUPpknFknGanw0mUuJNb3Y8bw5LgU5NqBXgsm8vR_h9XnYCj6u6czzCVZ5wSA0E0dSN3qPQbXt7vk) | **DATA**![](https://lh7-us.googleusercontent.com/rZQCYN8dcQFaQINptPaxnc1fEuE78IxLw6D0YSNxxdVn8UvB5-mXNvHKt-G6E-ULgKoPq2oEsp2N1DNubGbqEEc2_PhdbIMzIyubU4YKs5rUnN2NG8ZOuctPhDPczUJVF8EpabXav0v9szAtQcwMijk) ![](https://lh7-us.googleusercontent.com/4FZhQghZ_iMNPwXkThWjVVM_HXMNH56_kT2SnyKmBfaPAfwYCJMUSQnOBf962fOuhZdnRWlWGvsf9gbqhqAvhx5FX1DODqWEPdv2m2hwZh3g6ROFpplvunib2_T5afKfcv-d736Wj7Rr9dABFDZyGEc) |

- 1st Visual - Top 25 Routes by Avg Departure Delay; are there certain Routes with excessive Delays

  - CDV will add a Table visual displaying a sample of the data from the Dataset as the default visualization when you create a new Dashboard or new Visuals on the Dashboard (see New Dashboard screen above).  The next step is to modify (Edit) the default visualization to suit your needs.  
  - Pick the Visual Type - select the Stacked Bar chart visual

![](https://lh7-us.googleusercontent.com/u9q69XsH307aIesSeVp7mJVGXonsTYSJY0pxaF7qfANWYK5c6olhQWJ3KuqoOG35TZssV1x4RIV8VLAY8qLLiiaXvALOyqXnt9mCtC3P15kzfZHdbJoM_gkFTyyB0JzQCemHvLrjlIMDfrqcqxozlyU)

- Edit the Shelves (two (2) ways to add items to a Shelf, you will use both here; for the remainder of this lab you can pick & choose which you use)

![](https://lh7-us.googleusercontent.com/Rltc2AMxmL9vckq5lSlmcY-XJMnfwR2e_7lHsyUyZNOe1fYqtkBKPGrBIikxKID4Hg1i2aZV617l6wno3h1bYnjN8l7O88hqkW87lEOrlXF-YisCacSbXwWpaNq2XvlelBEtEVOl0mZvedXhtRO8YgI)

![](https://lh7-us.googleusercontent.com/phWzBj_PwSsJ7OPwBBTVM7-TpCUKOyzj9xmMb79mpoMWTc5fN5WqB653lOhtyf-DvCyGtoSV49hQP5e6QTAX85w-tql4fa2J6Etq9tJ1EL0h4jIkRHgjc9EaRpE8PHaM6MUGWHYUBMEOITrofrw8x0I)

- Option 1: Add Route to the X Axis

  - Click in the X Axis Shelf to select it
  - In the DATA menu find Route under Dimensions > fights

- Option 2: Add Dep Delay to the Y Axis

  - In the DATA menu find Dep Delay under Measures > flights, Drag & Drop this Field in the Y Axis Shelf

- So the two (2) options for adding items to Shelves is 1) select Shelf and click to add Field; or 2) Drag & Drop Field to Shelf

<!---->

- Modify Properties for Dep Delay - click on the > in the Y Axis Shelf to the right of avg(Dep Delay) to access the Properties for this Shelf

![](https://lh7-us.googleusercontent.com/UBZa3uVADn5gyLI2u5T7yZdsnzZIJL5MTOllFLdef0WRIXNp6lBh3jrjBL9rdza-T-hX2UVTkWjg_r3XlUV3t2z9S0oeOkqtjzPh2kNpiexRpY_IOKxlumC7rkrs5_r--OmzhmFd0T_RuSkAwXWWmkY)

- Click on the down arrow to the left of Aggregates - in CDV you have control over any behavior, in the Dataset we set the default aggregation for this Field to be Average, however, on any visual you can override this by changing it here.  For now, leave this alone.

![](https://lh7-us.googleusercontent.com/58hfsZ4Ly_WjKjkBm9XiXFXwqITwuMsa0fXzS2SadXKkxxlsgGebFh-pYyyecCBrtgDxkS6crgW6ZLVnrEsTv8lJLIfCfIXN4PwRCWzSkzHi9iSYpJhJ2VADrz-xI8fCXjTwVm6WF1AB8MHD0v5_ArA)

- Click the down arrow to the left of Order and Top K - to show the 25 Routes with the highest Average Dep Delay enter 25 into the box for “Top K”

![](https://lh7-us.googleusercontent.com/BTKRxVCYb1NBFaHpTcN0-cZkjBTMnVfnE3XVzsXFPdmN1xiRJTBK05hQu6V1aAKN1vPXFqIzWF0Upub7vdeHhX8Nj6Yp9_lkBpRojL1M7IfgAga0oqurLjNPpre34FBEpHClRTKTB-5Dje4KAAY_JFY)

- Click the down arrow to the left of Alias - to change the display name for this Field.  In the box enter Avg Dep Delay

![](https://lh7-us.googleusercontent.com/3yq13YOorAdXszQJsfjMN7D1Xvfc6b1BJjusaIMQhaT0ywFANR4lNYIBlBUwo4_kuRkWnmXsLx6leacO3E-1dLVNB5_fnjCbbFrK32deBrc3qqnE1tDC2g-NoW_S7Ta9w-nOVFyFM7AnGxp6v_IcmqI)

- The finished Y Axis Shelf should look like this

![](https://lh7-us.googleusercontent.com/bxHXjTvU35AJUSnar-2af6_RrsO56cfFqkHYlJLx6ywqIhCAy8lSjzAREwaH_sm03QdQheVSq9eI_ZnkU6MylFKgTBV5e2kiQIrq7Gxdsm1TEAQcA62Ce9DKo9rAltA4HXWq0jWbZ5TPj02ms3KGz3s)

- Click the ![](https://lh7-us.googleusercontent.com/TF7o8Oob6sHnQykatLiFZ4TpZZITqXPSPR-JEaKCt5ZqwEe3fMRalEqMq6ld1VPnlFs58sD1DL2qHUNX5tJ0RIH4Yzj4VhQEpo2P7Y96bT3Ojz14CpFVDW2hxmv5PfT8yQZ3r99K64zShQDZ7RIuW5Q) button to update the Visual

![](https://lh7-us.googleusercontent.com/hZZbod23JfzlgfyfxSXlVGk_vlk4QAoykWlGp6csLM-DZBceH0I2g9nTEbbPbx0v8p6aeewn3-4Q4rjtiPWXwpoBFAb8N_MvKCdP64oWc3CirQNdggZy84VyFR9OzzUKoppLdc9BcQkSfpVXLRq3qFI)

- Change the Title & Subtitle for this Visual

  - Click in the enter Title above the chart and enter - Routes with Highest Avg Departure Delays, hit enter
  - Click in the Subtitle and enter - In Minutes, hit enter

![](https://lh7-us.googleusercontent.com/vpx33HFpUg8qnFFJ8u0b3jPgvmT_abP3-7q64bT3U4BcSKV_dxmPqaCBJ9QWACU0MHm3-9-jOkNsspv8uLhKC6BHcI5mAOajSV5xSuZ_RWFoZ9-IX4bU9z4XJXGH1NI6g-8ofSHSCCBdeS0pzpqPZ0w)

-

<!---->

- Add Title & Subtitle for the Dashboard

  - Click in the enter Title right below the banner and enter - **\<user\_id>** Logistics Dashboard
  - Click in the Subtitle and enter - CDW Workshop

![](https://lh7-us.googleusercontent.com/nryNGD740zwhfwi9dBUQp55lbxm4y-fTwVJj2A7SEjNxjumGxelg-US_LlORe8P3vMIhtEBqq15HqM7I7cfYLqjKYUtSE2xt3N38s6KKhTZaLmjB6isrJ1sSGaUfS7mrtFIsQpgconNlYDP9lxGfvds)

- Click on the SAVE button to save this Dashboard, this Dashboard is now named **\<user\_id>** Logistics Dashboard

<!---->

- 2nd Visual - Relationship between flight Cancellation reason and Carrier; are there Carriers or Reasons that need to be addressed?

  - Click on +Visuals - on the far right of the screen you will see the DASH. menu.  This menu allows you to add new visuals and change settings for the Dashboard or Visual such as formatting, style, and anything related to the presentation of the data.

![](https://lh7-us.googleusercontent.com/xzUcfk7-nXispVIJYzoXkUYYBT0mm48HNwgwrkPjvaSMfa4dTXEg5jqiBmQlJDH31Y2oZYkyojc0xkG5A_GrX7M07W_kz51elUwM-VF5lYMe42mOKiQiCm1XLQSQ4aylfR1Fr-Jj1jDVkks2dTZThho)

- Under ADD VISUALS - leave the ![](https://lh7-us.googleusercontent.com/oxn-6B6FybInHot1njZKpvZVx9esputL3drnDcJj5E3KmlcLy54_wKnlKRrwL5LGQXnBhEvBwVRsqa7kPUMrhq5V5iiI67vMFuKaU7J3d9AJlqOTq3p4Jk6g_GA6h4dXXzySZ-nVRX-NcQu-V-wwEZo) (Connection) as \<user\_id>-airlines-lakehouse and ![](https://lh7-us.googleusercontent.com/oxn-6B6FybInHot1njZKpvZVx9esputL3drnDcJj5E3KmlcLy54_wKnlKRrwL5LGQXnBhEvBwVRsqa7kPUMrhq5V5iiI67vMFuKaU7J3d9AJlqOTq3p4Jk6g_GA6h4dXXzySZ-nVRX-NcQu-V-wwEZo) (Dataset) as airlines\_logistics.  However, a Dashboard can have any number of connections and Datasets for various visuals on a Dashboard.

![](https://lh7-us.googleusercontent.com/5dkxFo7qi-_vOhoAdzTUfFfNjxDq3zTurwH6oGYhzmaT12cXomr96RreCBO_0yPWe_3ETmaltfP5VgHdxmf5Ft0GVsJD20_6KluNOAW6y2Iecz2nYWp_OQWqWT5AWZeyWee_gEcbQrVvdcfnF22b6zk)

- This will add a default visual to the canvas
- Click on the ![](https://lh7-us.googleusercontent.com/la-AcD054k-2X89IhFEGFnAlETwkgzROjAFoeC3m0Mt5ZMez03Je8-CqjTDurJdQ9KBwJc1VUHzm6IMuc77Qui72UhBoPcKpegkUBtS2D4u3xoed4dvPyQNoOnzItsqFimK80IHViVFa9Uj0QqXUpfk) button, next to the Table ![](https://lh7-us.googleusercontent.com/nS14UFTcqzZ6TpsM8Y8grClsgBCJ4fm_hLUzzBEl2qNc8c-hOJmVdotVGiWNYeI1IKOjIOz2Vk1NUGyV-zBLH5agDglcdb0CsjbOI9HKxF2gl4d2WXGLPhaboaAcZjkj0f9BlbaOuLWGDdtYOjzovVA).  Instead of manually building this visual, we will use the Visual helper

![](https://lh7-us.googleusercontent.com/ia_ouwTU5bAoEanMj7L0M5UnW3Ntaz4kFvY6QS9TXm0fpJasi76uqlTuQiv8r2_yodr6lvjru_Fz7423uCN5tRzhrZcoNYL0CVeoKjh3rOGThp1VHmvLpfZwI8bM2QjsDoeW9135I-EjAGIKCcz8Jeg)

- Select Uniquecarrier and Cancellationcode under Dimensions; select Cancelled under Measures.  As you select items from the Fields you will see the Possible Visuals change - helping you quickly select the visual based on what you have selected.

![](https://lh7-us.googleusercontent.com/PDKmsK6xxkwmwB-5PwogCQgYTBpPl-9k-m7Mvzt13rZ2ebOv8XfxtCyl1gfOBrtnEudEvWakVcmpwhMmSgaJZPWkrVkBwk5L-HVPhOCFpFNf814lkQr2RhUSpys_igOf9fSEoemEO4NVMJyTB-mxwQ4)

- Click on SEE ALL VISUALS> button - to preview the Possible Visuals with actual data plotted
- Click on the Correlation flow visual - Scroll thru until you see the Correlation flow visual tile

<!---->

- Drag & Drop Cancelled from DATA menu under Measures > flights to the Filter Shelf - There are several ways to apply filters to visuals within the Dashboard, this is one

  - When the dialog box comes up

![](https://lh7-us.googleusercontent.com/yrWaz0A0tsQW9C_f4feGw-vFRfbdRtgN1pJKT4Rcq5EJC7JCiTiD1CXaa7oWEKXwOwXoA71u-NatQVZKwx1c5sAkaew9wMQyAMYsvJgXBcEamNlRUGqfpWqNo79_LkhMvcZMLoNrZy9pCg4h24bwAA4)

- This will filter this chart to only return flights that have been cancelled, and will not return any other data
- Click the REFRESH VISUAL button

![](https://lh7-us.googleusercontent.com/AG9ypJLYjZRFe6LRMmubQAB5got-vhonPPdfhU-T0kFfvsHZe_py_zAgl-_aV7ulE00MkfJ7bZRJTi7fGYk_FNsrmVlPK42ay59VKkgLEazivOxKBOT7zPUyAsvA0yQTkYU45CPV8QsEyY7zldFe_2E)

- **NOTICE**: Since there is a security policy still in effect, you will only see “UA” showing up in this visual.  To see all of the Carriers, you could disable the security Policy and Refresh the Visual.

<!---->

- Click ![](https://lh7-us.googleusercontent.com/Cj0oqa9uCMKuhi-ddPiwRabxi86Macn03nzxU4m9_efQ0cqLxYURNyz2msa_l88jBUGjhPFqQSXn6_KK5YM8Okldi4s2nvCMlkh3o-a_YuDR0ZZsHGtAMt6PFdv6Eb0kEyh0qNAyiTCsn6PMSrfGZmc)in the bottom right corner of the Correlation flow visual and drag it down to resize this chart (make it a bit larger to your liking)

![](https://lh7-us.googleusercontent.com/LSEg_XDheFPDLDWPjjgf28cq_UdsfY25Vu6x1I7QtRsC68JHAZmLjCU8ChhJpUni-oJFc-9YwedjyDY2sS6UdE6VPghtNAaCDCXHE5WZXAm5IISfVR8gKNMMXeX86JoH6otOazsGznkh3I3WiK95tQU)

- Click the enter Title and enter Cancellation Correlation, and hit enter
- Click the SAVE button to save the Dashboard

<!---->

- Add prompts - allow dashboard to be sliced & diced; this is another way to filter on multiple charts at the same time in your Dashboard

  - On the DASH. menu (far right) click on +Filters button

![](https://lh7-us.googleusercontent.com/swViHjEJIUrZEfOberKYh2GjeHzAdrhhmvWJbqeQB5Hhx_dmQR1YV117sEVdhypzuEmmXSWyPJtu6iXpioOnlIiFGe5lD6g8U5YnulO6VHvXvGxMlMjJw1wugNuaWtrdcM2p2oa15ntVGMvFmkNc1aM)

- Click on Engine Type under Dimensions > planes, to add this Field as a filter; you continue to select other Fields that you want to create Filters for and these will also be added

![](https://lh7-us.googleusercontent.com/oxn-6B6FybInHot1njZKpvZVx9esputL3drnDcJj5E3KmlcLy54_wKnlKRrwL5LGQXnBhEvBwVRsqa7kPUMrhq5V5iiI67vMFuKaU7J3d9AJlqOTq3p4Jk6g_GA6h4dXXzySZ-nVRX-NcQu-V-wwEZo)

- Click the drop down arrow next to Engine Type and select any value - the filter(s) are added to the Filter shelf for the Dashboard which is between the Dashboard Title and the Visuals you have been creating.  When you are selecting values from this Filter, the visuals will change to reflect information for just flights where this Engine Type was in the plane for the flight

![](https://lh7-us.googleusercontent.com/SK_ykCPGjwqsd3JEAMzb2_yZUFDmlgcCdYzN2oYHybgNqYgw9BQKu0g270hcZy7JUSZ5Un6bCqSLoUmSMj3zjz-2QPnqJcLyXrP_YFgt7oPvhphE9oE_ViH_GEU2DrFiGAiWhfXruA1yXVFqr9VsUVs)

![](https://lh7-us.googleusercontent.com/lww4SGzxA0t7Wf4pKpY0px_0c3W8ajcHp-sv6ZkMY33inTqs8RnQUZYCR-dhrh8pkp8JAdv6nMDYmH90gpBagd1wlFUTHy77RT23dwGVdu7PemK3DiLFoYbi4BALGiXg5UEUZKupBJV5iHYYT22sB4I)

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

    - On the left navigation menu click the ![](https://lh7-us.googleusercontent.com/qRuysYYxEBBSGP-8peUNm-05RSIa_7OKLNpbrKOpT1MhLQ1XZSt1hyN7tC-3ycb1zjs80_pYUMnTsUXjI0TDOoSWC6evt78mXbH8BLzVM-lqxzTPLRAqdAE0IFugCiZlutdWOyja_kg3yyY7zjmJil4)next to Data Warehouse

![](https://lh7-us.googleusercontent.com/qRuysYYxEBBSGP-8peUNm-05RSIa_7OKLNpbrKOpT1MhLQ1XZSt1hyN7tC-3ycb1zjs80_pYUMnTsUXjI0TDOoSWC6evt78mXbH8BLzVM-lqxzTPLRAqdAE0IFugCiZlutdWOyja_kg3yyY7zjmJil4) ![](https://lh7-us.googleusercontent.com/aDw9iwtdxK9nN0LeOf_kYmFmG7Y1VVwhC3O6HBi4cyO4DIqFMgfJwij0ywP0ZAzq9ylvKJkS2WtaeozYUiNORSdJIIC_1cBJqCv6LE5G7CIExDJEgdRCQP8XsXy7gnH82AAiVEqZU9-eiyUsJ0zqGZA)

- Right click on the Data Catalog and select “Open Link in New Tab” option

                      ![](https://lh7-us.googleusercontent.com/kCbrFFt34cb21O8dDIEJ9UIuDR50VEtW2N0UuaMDkfy31_W_kxDa_nY9JMww9XxHnzs6_UiGnOdZAk3fBEqA0tdBMjAaPQmqzQAHbilYCobCZaxN6Z1VHrI-NN9H2J13hcPogKRK1dGlphyBxI8m5Fo)

- Open browser tab that just opened, should have Data Catalog in the tab title

![](https://lh7-us.googleusercontent.com/1_RSu2hZq7jHRC4ibJAH04_7ZSxdwhxiciYp4veuId-2JCVWRbnD-64kPkIkRXm0ctCREcgx6oVhQu4_W3hDArF8JJ15l4gtijTDHfHG721NeKIF6c81Q8hlaGgmWRBWMpgi8kq-fKdpfPy73rxmC1w)

- To the left, under Data Lakes, ensure the Data Lake provided in Lab Setup radio button is selected

![](https://lh7-us.googleusercontent.com/euaRvICbrrwgQXVDxTAZabJSeL9SvnxMrLrawEdG39rahQiv5TBK2S4nd_zlcIY27jXEcIhE1QrDrbbkWhQ_d_NUy8txx4VjAlyOpPnfuiokxZ0aEx56NN97QfDuEquMqIR_Oo7dtdCK7OL42REemS4)

- Filter for Assets we created - below the Data Lakes on the left of the screen under Filters, select TYPE of Hive Table.  The right side of the screen will update to reflect this selection

![](https://lh7-us.googleusercontent.com/-787CSOKqPc_YfbsTy-Gr6e39hWKBJt6AvPL-3XKPnYmCJhlhhAG_blicwl87_iPOwIABszogS_DwS0rPu2S8MD9bqzFG7q5RUk3lhK-txbXFIGYEyX9_uxfbMwqDEC_YTc8z0XEFO_jtjYlEQICRyc)

- Under DATABASE, click +Add new Value.  In the box that appears start typing your **\<user\_id>** when you see the **\<user\_id>**\_airlines database pop up select it

![](https://lh7-us.googleusercontent.com/f2O3iUI8FFCztNlzW7hF5WLzTwkUQDH25M8h8oVaTFXjCiiHVXXmzzUj_kmu5KAM8NPFrMEe0G0zghCEcAUNqmDTnME6s8dh6YMUj78wHAvpji4xbX-QirYm5EVHaPu3jMizGLdAJi2qtT11-8RgYyo)                          ![](https://lh7-us.googleusercontent.com/SBC-rwWUrkABhjvagK9KETGOa7Epy319kWV5-zUy039AvHcWRx2en0nXhj0zzJlFu31X9fbC4w0j82YQSlehN3ehLTSAOq7-HQxkZ4OnYtJ5Gfh1Q2zQRq2sBJTksh4vUIoIxeboIeGQwoiuNrdy0z8)

- You should now see the tables and materialized views that have been created in the **\<user\_id>**\_airlines database.  Click on flights in the Name column to view more details on the flights table.

![](https://lh7-us.googleusercontent.com/v_93T60m3SMaORQlC9ta4JbRCbd5zoltSmvu3jb0lJVnBxgAQrgfJ2lEG2WIw27VN5OcfMxOCgi1PfhBd6DHYiTCntPPEynKE029eQsUZRfDT0whbKzKd-jfIZAxYijJt_AXmD7vt8dYpczCx5PKjKE)

- This page shows information about the flights table such as the table owner, when the table was created, when it was last accessed, and other properties.  Below the summary details is the Overview tab which shows the lineage - hoover over the flights click on the “i” icon that appears to see more detail on this table

![](https://lh7-us.googleusercontent.com/5bxCa04J_A9OAzLYOWicOafjXsW8f9-RtwYz9N5AAlnd55mN3AwRetKpqR256O3WM6Go5sm_5PlgcREcWYUs_4ZPJrqg2lnZICbEUhubr96W-pr-Q2sk75kN8hQtP5XiNzyK-FsTXycoIr6sdArGGVg)

- The lineage shows 

  - \[blue box] flights data file residing in an s3 folder
  - \[purple box] is showing how the flights\_csv Hive table is created, this table was created and points to the data location of flights’ (blue box) s3 folder 
  - \[orange box] is showing the flights Iceberg table and how it is created, it uses data from flights\_csv Hive table (CTAS) 
  - Traffic\_cancel\_airlines is a Materialized View that uses data from the flights Iceberg table.

![](https://lh7-us.googleusercontent.com/_IOIYOk6Jy1cA0173iGCdPq_yOcROoeJH3oNErZtuCWNR18s1V8Ioj0r0s0IVoEEfDqlW8nrSPHXIN-P6Jgi63ioT_EDkDnVN7t1oz6MeaD9fl__kcrqGtCLbaLTdRBWFbqMddAFI-gdYRshltPEVXA)

- Click on the Schema Tab to see Metadata on this table.  The Metadata includes basic information from the table such as: column names and data types for the columns.  You can also run Profilers that  come as part of CDP:

  - Hive Table Profiler - allows you to gather additional information from the table including Min/Max values in the column, # records with Null Values in a column, etc.
  - Sensitivity Profiler - identifies columns that may contain sensitive information such as PII data, SSN, credit card numbers, ID numbers, etc.  These items will be “Tagged” in the Classification column of the Schema page.

![](https://lh7-us.googleusercontent.com/tLBHRWjsBIOWp3RbS9Z3LSbsYDxIW5Dixkqj50Pqf4mbZ5o5sopWTC2LXFlK5_pYaJmhexl9ZygCTJaIPWRoJhgDygK_UHkJOSY7tuGDt7ksahTT8XHV8f-GxdsYUtmVTEwEurvRtwZQYsjBHhB5bxw)

- Click on the Policy tab to see what security policies have been applied on this table.  There are 2 policies that have been defined to allow some users & groups access via policy “all - database, table, column” and another policy “all - database, table” access.

  - The Access Audits tab allows Administrators to be able to see who, when, where, why either accessed this table or was denied access to this table.  Feel free to switch to this tab to take a look and switch back to the Policy tab.

![](https://lh7-us.googleusercontent.com/1UU5q7xKCUT_L-fF_rbdEVBjqyuR5wxveIi9AsTSiX3_55izfIB6lk549pMbOkOpM4siHYU7-pav38TJlD6YdfvHD_fJHG3gIBpVSSJjPiPx0778J6R4Qvgzuw1L6FqCwO_QVC2xuBjnj62fNH21-lw)

- Click on the ![](https://lh7-us.googleusercontent.com/vq9QvTR4xQePkUGtPZQWQDTeOX3Fly2j7WmIhIErqT4pX5tynOtKEjd2zkSzpVOhlGN7nKyd5eTsVKcywesd-G-s-znkPOf4bWA6_UUiEE1UFwrpoFxs9utFF_1Y6NUTSecX8C1yhFq399zIro1NdfY) next to the “all - database, table” - to modify this policy or create a new policy

![](https://lh7-us.googleusercontent.com/vq9QvTR4xQePkUGtPZQWQDTeOX3Fly2j7WmIhIErqT4pX5tynOtKEjd2zkSzpVOhlGN7nKyd5eTsVKcywesd-G-s-znkPOf4bWA6_UUiEE1UFwrpoFxs9utFF_1Y6NUTSecX8C1yhFq399zIro1NdfY)

26. Security (Ranger) - modify and create security policies for the various CDP Data Services.

    - View the Policy details and click the CANCEL button at the bottom.
    - For this portion of the Lab let’s restrict your access to a subset of data available in the “flights” table.

![](https://lh7-us.googleusercontent.com/wdiSNZXBroCIs9zcY2UNN-VvfYaiJ8JdWuQGeC79aiVps33mJib1oG73zHnQaO33i37_uvIoKuoeZw0gVFkHfTHo0a-X42qWuBo4Uyx7F67kZjlUPTDNtrQH-hitw6NoKMWWl7H3AUpWb7B28whoYd0)

- Click on the Hadoop SQL link in the upper left corner - to view the security policies in place for CDW.  For this Workshop we will stick to the CDW related security features

![](https://lh7-us.googleusercontent.com/SoVXssufcy0nvu0N2_LXtLPkRMAq_XjD6leoO3DSl538ST5Z0DO58nftP-QluQ6DVzdY4W8kssoJA5E5LVvZ4kB-w9LhQJLHLQjycyhjjmBG4LAsQTrj6J7dXhQfz-ip4YqOCOT_kZFHDXpPOfWdz2U)

- This screen shows the general Access related security policies - who has access to which Data Lakehouse databases, tables, views, etc.  Click on the “Row Level Filter” tab to see the policies to restrict access to portions of data

![](https://lh7-us.googleusercontent.com/Z6UoOZ5p7gvso8L8BNCb7bu0dD9ZLPSeuHwOQ5xKAJuEPFhW4A5oYUe2RiKqKH69GEGUKdoW4u2A8fhhe03TpfiX2deONjozIun1PotzQWLmYcDX1CFGbMPN0XZBYHY2z3KFomefSE_9-EigpDahxk8)

- There are currently no policies defined.  Click on the Add New Policy button

![](https://lh7-us.googleusercontent.com/ZeM70yqAmuJKlAs7wvHVrBg53SZcIBiYyrNsvRueFiXYQGMfTwYZLcYRyBLOsRgLrsedUJX5D9y0UWmrzhdVAxWnGnsEAZ8mGOL_MHAZu-9Dpe7ZhXvtiqSHNiqjaUJbPz7UQkAQDmNLS8PDyAGvOT8)

- Fill out the form as follows.  For this policy let’s say you are an Gate Agent for United Airlines and should not be able to see data for any other Airline.  To setup the policy we need to apply a filter that is applied to any query that is run for your **\<user\_id>** so you only see rows for flights run by United Airlines.

  - Policy Name: **\<user\_id>** Workshop Row Level Filter

  - Hive Database: **\<user\_id>**\_airlines (start typing, once you see this database in the list, select it)

  - Hive Table: flights (start typing, once you see this table in the list, select it)

  - Row Level Filtering Conditions

    - Select User - **\<user\_id>** (start typing, once you see this user in the list, select it)
    - Row Level Filter - **uniquecarrier="UA"**
    - For this you could have any number of filter conditions (for this Lab we will only create 1) with many different filter configurations

  - Click ![](https://lh7-us.googleusercontent.com/xZPcYstCIHi24E2gjLvurapN2jHNzp5Fyp_HbdDe24TJOPr-dNXd-fv8FLAMivgNWy8NIg4uwwFDdGJZ_KQRam5ZUOjXWd_HbpT0wyugCS_R8VanfrlXlnp_wDz-O-KWdn5nkTziMV0Qd7waDQmThaE) button to accept this Policy

![](https://lh7-us.googleusercontent.com/645glwdQak3tpXTeWCC7vv7q2JZZZccyWT-xj4UxBxGWt0ppvtxKR2LLlx1NHk5rfHgjrNSAYnzhZJXwV1Kdqwg05JgATcrtrNJB4Ta4sfq9bhy-kMT_Ctw9HeaEFoHLjUjxOJ77n46tZAcLVdACF7E)

- The new policy is added to the “Row Level Filter” policies (as below)

![](https://lh7-us.googleusercontent.com/GdwJ7dMe7HqpdvQvCaNoIDIA0MplMmgZlX3BrIgi-nejh5WGkDlNeVB4l2vwAbLcReoAIoiMFYbKk3jQXe3NeT0Rxf8cv85wk8fXLM7fgsNCts0JMZjFbzg-c620m5NTcp0lr6IQCjipW9Yqkh3UUvY)

- Test the policy is working - Open HUE for the CDW **Impala** Virtual Warehouse - airlines-impala-vw and execute the following query

<!---->

    SELECT uniquecarrier, count(*)

    FROM ${user_id}_airlines.flights

    GROUP BY uniquecarrier;

You should now only see 1 row returned for this query - after the policy was applied you will only be able to access uniquecarrier = “UA” and no other carriers:

![](https://lh7-us.googleusercontent.com/gVVGkoFG6Uz2TrnW6Q9aqob-VwpktFHFCu-0BnTke_GJV5-rrlf9ec_VvMV-Zls5ugtsZoWpfAbt38z5TfH9siaDfS6xD5T0PTO34jKfBsjRdlZ209Vpqr3E0USlfTYyJfiS04SfaMJlwjnN4p149kQ)

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
