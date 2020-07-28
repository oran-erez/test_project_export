# Building an LU Hierarchy and Linking Table Populations

## Table Population Links Overview
An LU schema structure displays a hierarchical representation of the data related to the Root Table. Parent-child links in LU tables are created via their Table Population objects :
* Each LU table can have one or several Table Population objects and each Table Population object, except the Table Population object of the Root LU table, must be linked to a parent table via its [input arguments](/articles/03_logical_units/12_LU_hierarchy_and_linking_table_population.md#what-are-the-table-populations-input-arguments) (input columns). 
* Each Table Population object can be linked to a different parent LU table.

  **For example:** an ADDRESS LU table is populated by two populations: 
  
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Population 1, populates the customer’s billing address.</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It is linked to the CUSTOMER table and selects source address records that belong to the CUSTOMER_ID.</p> 
 
  
![image](/articles/03_logical_units/images/03_12_link_tables1.png)



<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Population 2, populates the the installation address of each subscription.</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It is linked to the SUBSCRIBER table and selects the source address records that belong to the SUSBCRIBER_ID.</p>


![image](/articles/03_logical_units/images/03_12_link_tables2.png)

* A link from a Table Population object to a parent LU table can be based on several columns where all columns must be linked to the **same parent LU table**.

  **Example 1:**\
The INVOICE Table Population object can be linked to the BALANCE LU table by two columns: SUBSCRIBER_ID and BALANCE. This is a valid link.

![image](/articles/03_logical_units/images/03_12_link_tables3.png)

  **Example 2:**\
Linking the INVOICE Table Population object to two different LU tables - BALANCE and SUBSCRIBER is invalid.

![image](/articles/03_logical_units/images/03_12_link_tables4.png)

* The DB query population filters the selected data based on the link to the parent LU table. For example, the parent table of ADDRESS is CUSTOMER. The ADDRESS DB query selects the ADDRESS records that belong to the CUSTOMER_ID of each LU Instance.

**Note:** An LU table can be added to an LU schema without a Table Population object. This table is not populated by the sync of the instance, but can be populated by a separate transaction.


## What Are the Table Population's Input Arguments?
Input arguments are a property of the [Source Object](/articles/01_fabric_overview/02_fabric_glossary.md#source-object)  of a Table Population object.

There are [two types of Source Objects](/articles/07_table_population/02_source_object_types.md) for a Table Population object:
* DB query
* Root function

**DB Query**
* A DB query Table Population object can be linked to a parent table via its input argument fields. Only input arguments that are defined as True can be linked to parent tables.
* In the DB query of a Root Table, only one field can be defined as True and is populated by the [Instance ID](/articles/01_fabric_overview/02_fabric_glossary.md#instance-id).
* Other LU Tables can have several fields defined as input arguments. 

**Root Function**
* Each root function must have at least one Input parameter.
* A population can be linked to a parent table via its Input parameters based on a Root function. 
* The Root function of a Root Table can have only one Input parameter and is populated by the Instance ID.

[Click for more information about Table Population Types.](/articles/07_table_population/02_source_object_types.md#table-population---source-object-types)


## How Do I Edit the Input Arguments In a DB Query?
When creating a DB query, by default all Input fields are set to True.  

To edit an Input argument, do the following: 

Click the **source object** of the Population window (the DB query) and verify that the fields that should be linked to the **parent table** are set to **True**. Other fields which do not need to be linked to a parent table, can be set to **False**. 

![image](/articles/03_logical_units/images/03_12_link_tables5.png)

## How Do I Link a Table Population to the LU Schema? 
A link can be added in both directions:
* **Child to parent**, linking the child population to a parent table.
* **Parent to child**, linking a parent table to a child population.

## How Can I Link the Child Population to a Parent Table? 
1. Click the **Child Population** header.
1. Connect each **input field** to a **parent table** using one of the following methods:\
  a. Drag the **connection line** to the **parent table** and **column**.\
  b. Right click, select **Add link from** > **parent table** > **column**.

**Note:** Link all the Input fields of the selected Table Population object to one parent table. A Table Population object cannot be linked to several parent tables.  

## How Can I Link a Parent Table to a Child Population?
1. Click the **parent table**.
1. Connect each **parent column** to the **child population** using one of the following methods:\
  a. Click the **child population** header and drag the **connection line** to the **parent table** and **column**.\
  b. Right click, select **Add link to** > **child population** > **column**.

**Note:** Link all Input fields of the selected Table Population object to one parent table. A Table Population object cannot be linked to several parent tables.  

## How Can I Delete Table Population Links?
Click the **link** and press the **Delete key**, or right click and select **Delete**.

[![Previous](/articles/images/Previous.png)](/articles/03_logical_units/11_add_delete_table_population.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/03_logical_units/13_disable_enable_populations_in_schema.md)

