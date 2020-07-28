# Query Builder Overview

The Query Builder is an embedded visual query building component that allows you to build complex SQL queries on a selected [DB interface](/articles/05_DB_interfaces/03_DB_interfaces_overview.md) using an intuitive interface. 

The Query Builder window has two tabs: 
* Query, where you can build and run an SQL query on selected DB Tables, Views or Synonyms. 
* Results, which displays the results of the executed SQL query. 

Note: 
The [DB interface](/articles/05_DB_interfaces/03_DB_interfaces_overview.md) has a [Schema Filter](/articles/05_DB_interfaces/03_DB_interfaces_overview.md#schema-filter) setting which enables filtering the DB schema’s list that is used by the Query Builder and the [DB queries](/articles/07_table_population/01_table_population_overview.md) in the DB interface.

### Opening the Query Builder Window
 The Query Builder window can be opened in several ways. Select one of the following options: 
1.	[**Fabric Studio Toolbars Tab**](/articles/04_fabric_studio/01_UI_components_and_menus.md#fabric-studio-toolbar-tabs) > <img src="/articles/11_query_builder/images/12_1_1%20icon.png"> **Query Builder**.
2.	**Project Tree**, right click **DB Interface** > **Show Query Builder.**
3.	**Fabric Studio Java Editor**, right click the **Editor** pane > **Open Query Builder** > **Schema**.

![image](/articles/11_query_builder/images/12_1_2%20Schema..png)

4.	[**Table Population**](/articles/07_table_population/01_table_population_overview.md) or **Parser Maps**, if the Source Object is a DB query, double click the **Source Object** or click **Edit Query** in the [**Source Object Properties tab**](/articles/07_table_population/04_table_population_properties_tab.md#source-object---db-query-properties).
5.	[**Logical Unit Schema window**](/articles/03_logical_units/03_LU_schema_window.md), right click and select either **New Table from SQL Based DB Query** or **New Table From SQL Based Root Function** to [create a new LU table](/articles/06_LU_tables/02_create_an_LU_table.md) based on the SQL query. Both options open the Query Builder window to build the SQL query.  The LU table and its population are automatically generated based on the SQL query defined in the Query Builder.
6.	[**Translation object**](/articles/09_translations/01_translations_overview_and_use_cases.md#translation-schema), the data in a **Translation** field can be validated using the Query Builder if the **Field Type = SQL**. Click **SQL** next to the field to open the Query Builder.

![image](/articles/11_query_builder/images/12_1_3%20query%20builder.png)

7.	**Instance Group**, right click and select **Open Query Builder** > **Schema**.
8.	**Graphit window** click <img src="/articles/11_query_builder/images/12_1_1%20icon.png"> **Query Builder** in the **SQL** or **SQL non-prepared** node type.

9.	**Broadway**, click the **QB button** in the **DbCommand actor** to open the **Query Builder**.   
<!--Next drops (drop 2)- add links to Broaway, Instance Group, Graphit-->

[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/11_query_builder/02_query_builder_window.md)

