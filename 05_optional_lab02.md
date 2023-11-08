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

