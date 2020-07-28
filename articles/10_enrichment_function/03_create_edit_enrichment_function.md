# Creating or Editing an Enrichment Function

An Enrichment function is a [Project function](/articles/07_table_population/08_project_functions.md) without Input / Output parameters that is used to insert, update, or delete an LU Table's data after it has already been populated from a source object. It is defined as a specific category of Fabric [Regular functions](/articles/07_table_population/08_project_functions.md).

### How Can I Create or Edit an Enrichment Function?

The steps for creating an Enrichment function in Fabric Studio are the same as those for a Regular function. 
The steps which are unique for Enrichment functions are as follows:
1. In the **Function Properties** tab, set the **Function Type** to **Regular Function**. 
2. Do not define Input / Output parameters.
3. It is recommended to set the **Category** to **Enrichment**.

![10_03_create_enrichment_1](/articles/10_enrichment_function/images/10_03_create_enrichment_1.PNG)

[Click for more information about How to Create a Project Function.](/articles/07_table_population/10_creating_a_project_function.md)

### How Do I Attach an Enrichment Function to an LU Table?

An Enrichment function must be attached to one or more [LU tables](/articles/06_LU_tables/01_LU_tables_overview.md) in the [LU schema](articles/03_logical_units/03_LU_schema_window.md) to be executed during the [LUI sync](/articles/14_sync_LU_instance/01_sync_LUI_overview.md). 

Do the following:
1. Go to **Project Tree** > **Logical Units** > [**LU Name**] > **Tables** > [**Table Name**] to display the **Table Schema** window.

2. To attach the [Enrichment function](/articles/06_LU_tables/04_table_properties.md#enrichment-functions) using the Table Properties tab, click the **three dots** next to the **Enrichment Functions** option to open the **Enrichment Item Collection Editor**. 

   ![10_03_create_enrichment_2_1](/articles/10_enrichment_function/images/10_03_create_enrichment_2_1.PNG)

3. Click **Add** and then click the area next to **Name** to display the list of Enrichment functions. Note that only the functions without Input and Output parameters are displayed.

   ![10_03_create_enrichment_2_2](/articles/10_enrichment_function/images/10_03_create_enrichment_2_2.PNG)

4. Select the function from the list. 

5. (Optional) To add more **Enrichment functions** to the same LU table, click **Add** again and select the additional functions. Define the Enrichment functions execution order using the **arrows** next to the **function names** in the **Editor**.

   ![10_03_create_enrichment_3](/articles/10_enrichment_function/images/10_03_create_enrichment_3.PNG)

6. Click **OK** to close the Editor.

7. **Save** the table.

8. Open the **LU Schema > Enrichment Order** tab to verify that the enrichment order of all the Enrichment functions in the LU is correct. Note that you can [edit the enrichment order](/articles/03_logical_units/14_edit%20enrichment%20order.md#edit-enrichment-order) on the LU schema level.



### How Do I Remove an Enrichment Function from an LU Table? 

To remove an Enrichment function from the LU table, do the following:

1. Go to **Project Tree** > **Logical Units** > [**LU Name**] > **Tables** > [**Table Name**] to display the **Table Schema** window.

2. In the [Table Properties tab](/articles/06_LU_tables/04_table_properties.md#enrichment-functions), click the **three dots** next to the **Enrichment Functions** option to open the **Enrichment Item Collection Editor**.

   ![10_03_create_enrichment_3](/articles/10_enrichment_function/images/10_03_create_enrichment_3.PNG)

3. Select the function and click **Remove**.

4. Click **OK** to close the Editor.

5. **Save** the table.

[![Previous](/articles/images/Previous.png)](/articles/10_enrichment_function/02_enrichment_vs_root_func_comparison_analysis.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/10_enrichment_function/04_enrichment_function_code_examples.md)
