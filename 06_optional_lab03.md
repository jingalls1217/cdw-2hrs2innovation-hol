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
