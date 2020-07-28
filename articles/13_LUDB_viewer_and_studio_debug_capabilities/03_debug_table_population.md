# Debug Table Population

A [Table Population](/articles/07_table_population/01_table_population_overview.md) is a Fabric Studio component that defines and executes the mapping and data[ transformation rules](/articles/07_table_population/05_table_population_mode.md) from a data source, like a DB table or Input file, into a target [Logical Unit (LU) table.](/articles/03_logical_units/01_LU_overview.md) 

The Table Population window is used to define and display the transformation rules that are applied to data when it is loaded into a Fabric database.

The following is an example of the Table Population window:

![image](/articles/13_LUDB_viewer_and_studio_debug_capabilities/images/13_03_01%20Table%20Population%20window..png)

The Population window has a **Debug** option that can be used to execute a Table Population in a Debug mode. The mapped data is displayed in the Population Window working area and errors, if they exist, are displayed in the [Log window](/articles/13_LUDB_viewer_and_studio_debug_capabilities/02_fabric_studio_log_files.md). 

The Debug process either runs an existing LUDB file which has been generated by the [Data Viewer](/articles/13_LUDB_viewer_and_studio_debug_capabilities/01_data_viewer.md) or generates a new LUDB file. In the Table Population a source object can return one or many records whereby each output record is mapped and populated into a target LU table. A Debug process can be executed on each record in the population.

### How do I Use the Debug Toolbar?

The **Debug Toolbar** is used to test the Table Population map by executing its population logic on a selected [Instance ID](/articles/01_fabric_overview/02_fabric_glossary.md#instance-id).
* When the execution is successful, the values of the Input and Output fields are displayed in the working area above the connection lines between the source and the target. 
* If there is an error, it is displayed in the Fabric Studio [Server Log](/articles/13_LUDB_viewer_and_studio_debug_capabilities/02_fabric_studio_log_files.md) section.

The **Debug Toolbar** has the following icons:

<table>
<tbody>
<tr>
<td width="200pxl">&nbsp; <img src="/articles/13_LUDB_viewer_and_studio_debug_capabilities/images/table1.png" alt="" /></td>
<td width="500pxl">
<p>Enable / Disable Debug.</p>
<p>By default, the Debug icon is disabled. To enable Debug Mode and display its icons on the toolbar, click the Debug icon.</p>
</td>
</tr>
<tr>
<td width="200pxl">&nbsp; <img src="/articles/13_LUDB_viewer_and_studio_debug_capabilities/images/table2_1.png" alt="" /><img src="/articles/13_LUDB_viewer_and_studio_debug_capabilities/images/table2_2.PNG" alt="" /></td>
<td width="364">
<p>Displays a list of <a href="/articles/01_fabric_overview/02_fabric_glossary.md#instance-id">Instance IDs</a> for which the LUDB file exists.</p>
<p>Either search for the Instance ID or select it from the dropdown list of debugged Instance IDs.</p>
</td>
</tr>
<tr>
<td width="200pxl">&nbsp; <img src="/articles/13_LUDB_viewer_and_studio_debug_capabilities/images/table3_1.png" alt="" /><img src="/articles/13_LUDB_viewer_and_studio_debug_capabilities/images/table3_2.PNG" alt="" /></td>
<td width="364">
<p>Displays a list of existing LUDB files.</p>
<p>Click to select the file from the existing LUDB files or generate a new one. By default, the newest LUDB file is selected for the Debug&rsquo;s execution. &nbsp;&nbsp;</p>
</td>
</tr>
<tr>
<td width="200pxl">&nbsp; <img src="/articles/13_LUDB_viewer_and_studio_debug_capabilities/images/table4.png" alt="" /></td>
<td width="364">
<p>Displays the current record&rsquo;s number.</p>
</td>
</tr>
<tr>
<td width="200pxl">&nbsp; <img src="/articles/13_LUDB_viewer_and_studio_debug_capabilities/images/table5.png" alt="" /></td>
<td width="364">
<p>Execute Debug Mode: Options include Debug, Debug Next Record or Debug Next Instance which enable moving between the returned records.</p>
</td>
</tr>
</tbody>
</table>

[![Previous](/articles/images/Previous.png)](/articles/13_LUDB_viewer_and_studio_debug_capabilities/02_fabric_studio_log_files.md)
