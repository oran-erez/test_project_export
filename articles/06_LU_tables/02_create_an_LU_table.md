# Create an LU Table

### How Do I Create a New LU Table?
LU tables are the basic building blocks for creating [Logical Units](/articles/03_logical_units/01_LU_overview.md#logical-unit-lu-overview). There are several ways to create a new LU table.

From the [LU schema](/articles/03_logical_units/03_LU_schema_window.md):

*	Right click the work area and select either the **New Table From SQL Based DB Query** or **New Table From SQL Based Root Function** option.
*	Drag the table into the **LU Schema** window from the **DB Objects tab**. 

From the Project Tree: 
*	Via the [**Auto Discovery Wizard**](/articles/03_logical_units/06_auto_discovery_wizard.md) to create or edit the LU. The tables and their populations are automatically created and added to the LU schema. If a table exists, you can select to either override the existing implementation or not.
*	Creating a new table **manually**. In this option the table population should be created separately. Once the population is created, add the table to the LU schema. Note that if the table is used as the Master of Data, there is no need to create a Table Population.
*	Copying an existing LU table from one LU to another. In this option if there is a Table Population it is also copied. 
*	Creating a set of tables based on an **XSD file**.
*	Using the **Save As** option. Note that this option does not copy the Table Population.

[Click for More Information about Adding a Table to a Schema](/articles/03_logical_units/09_add_table_to_a_schema.md).
 
### How do I Create a New LU Table Manually?  
1.	Go to **Project Tree** > **Logical Units** > [**LU Name**], right click **Tables** > **New Table** to display the **Columns tab** in the **Table Schema** window.
2.	Define the [**Table Schema**](/articles/06_LU_tables/02_create_an_LU_table.md#table-schema-definition):\
   a.	Complete the settings of each table column like the **Name** or **Data Type**.\
   b.	Optional: Define the table [**Indexes**](/articles/06_LU_tables/03_table_indexes.md).\
   c.	Optional: Define the **CDC** and the table’s **Search** indexes.
3.	Define the [**Table Properties**](/articles/06_LU_tables/04_table_properties.md). 
4.	**Save** the table.

### How Do I Edit an LU Table? 
1.	Go to **Project Tree** > **Logical Units** > [**LU Name**] > **Tables** > [**Table Name**] to display the **Columns tab** in the **Table Schema** window.
2.	Optional: Edit the table’s **Columns**, **Indexes**, **Search Indexes** or **Table Properties**.
3.	**Save** the table.

Note that in specific cases the Data Type of a column that has been automatically created based on a DB table may need to be edited manually. For example, a **Number** column in Oracle is created in Fabric with **Data Type = Real**. This column might need to be modified to an **Integer** or **Text** in the LU table.

### Table Schema Definition  
The **LU Table Schema** is defined in the **Columns Tab** in the **Table** window where you can set the columns and their types, mark mandatory fields and set the default values. 

<table width="623">
<tbody>
<tr>
<td width="200pxl">
<p><strong>Index</strong></p>
</td>
<td width="700pxl">
<p>Defines the position of the column in the table which can be moved up or down.</p>
</td>
</tr>
<tr>
<td width="122">
<p><strong>Name</strong></p>
</td>
<td width="502">
<p>Column name.</p>
</td>
</tr>
<tr>
<td width="122">
<p><strong>Data Type</strong></p>
</td>
<td width="502">
<p>The Data Type of the values in the column. The following types are supported:</p>
<ul>
<li>Integer</li>
<li>Real</li>
<li>Text</li>
<li>Blob</li>
</ul>
<p>Note that if the Oracle field type is <strong>Number</strong>, Fabric sets the <strong>Data Type</strong> of this field to <strong>Real</strong> in the <strong>LU table</strong> and the number in Fabric has a decimal point. Therefore, if a column in the <strong>LU table</strong> does not need a decimal point (for example, for the CUSTOMER ID), change the <strong>Data Type</strong> of the <strong>LU Table</strong> column to <strong>Integer</strong> or <strong>Text</strong>.</p>
</td>
</tr>
<tr>
<td width="122">
<p><strong>Mandatory</strong></p>
</td>
<td width="502">
<p>When checked, this column must be populated (not null), otherwise leave it unchecked.</p>
</td>
</tr>
<tr>
<td width="122">
<p><strong>Default Value</strong></p>
</td>
<td width="502">
<p>The value set in this column is used to populate the table when there is no input for this column.</p>
</td>
</tr>
<tr>
<td width="122">
<p><h4><strong>Column Type</strong></p>
</td>
<td width="502">
<p>Two Column Types are supported:</p>
<ul>
<li>Regular, (default) whereby the column is populated using the table&rsquo;s mapping.</li>
<li>Computed field, whereby the column is updated using an Enrichment function.</li>
</ul>
<p>The difference between the Column Types is the timing of their execution. When a column is defined as a Computed Column, the execution of the function is performed <strong>after</strong> all tables in the Logical Unit have been populated.</p>
</td>
</tr>
<tr>
<td width="122">
<p><strong>Comment</strong></p>
</td>
<td width="502">
<p>Additional information.</p>
</td>
</tr>
<tr>
<td width="122">
<p><strong>ID</strong></p>
</td>
<td width="502">
<p>Unique ID of the column generated by Fabric.</p>
</td>
</tr>
</tbody>
</table>
<p>&nbsp;</p>

[![Previous](/articles/images/Previous.png)](/articles/06_LU_tables/01_LU_tables_overview.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/06_LU_tables/03_table_indexes.md)
