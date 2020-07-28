# Navigating an LU Schema

When creating or editing a [Logical Unit schema](/articles/03_logical_units/03_LU_schema_window.md) the following options are used to navigate, configure and display information:
* [Diagram Outline](/articles/12_LU_navigation/01_Navigating_an_LU_schema.md#how-do-i-use-the-diagram-outline) tab, a representation of the LU schema table’s list.
* [Navigation pane](/articles/12_LU_navigation/01_Navigating_an_LU_schema.md#what-is-the-navigation-pane), an overview of the [LU schema](/articles/03_logical_units/03_LU_schema_window.md) located in the right corner of the working area.
* LU working area, where view options can be set.

[Click for more information about the Diagram Outline and Toolbars.](/articles/04_fabric_studio/03_diagram_and_toolbars.md)

### How Do I Use the Diagram Outline?
 
The Diagram Outline displays an overview of the LU structure and can be used to search for a subset of tables included in the Schema. 

![image](/articles/12_LU_navigation/images/10_01_01.jpg)

To search for an LU table in an [LU schema](/articles/03_logical_units/03_LU_schema_window.md):
1.	Open the **LU Schema** window. 
2.	Click the **Diagram Outline** tab in the right panel.
3.	In the **Search** field, type the **name** of the **table** or **column** and then click it  in the displayed list. The table or column is highlighted with a green border.

### What is the Navigation Pane? 
 
The Navigation pane in the right corner of an [LU schema](/articles/03_logical_units/03_LU_schema_window.md) is used to move between the different areas of a Schema. This is useful when looking at large Logical Units with many tables or hierarchy levels.

![image](/articles/12_LU_navigation/images/10_01_02.jpg)

### What are the LU Working Area View Options?
 
LU Tables relationship options:\
In the LU working area, right click an LU table object to display a context menu with the following actions:

<table width="595">
<tbody>
<tr>
<td width="300pxl">
<p><strong>set as: root&nbsp;</strong></p>
</td>
<td width="600pxl">
<p>Sets the table object as the root of this LU.</p>
</td>
</tr>
<tr>
<td width="283">
<p><strong>show only Predecessor nodes</strong></p>
</td>
<td width="312">
<p>Shows only objects and links that are predecessors of this object / field.</p>
</td>
</tr>
<tr>
<td width="283">
<p><strong>show only successor nodes</strong></p>
</td>
<td width="312">
<p>Shows only objects and links that are successors of this object / field.</p>
</td>
</tr>
<tr>
<td width="283">
<p><strong>show only connected nodes</strong></p>
</td>
<td width="312">Shows all objects and links connected to this object / field.</td>
</tr>
<tr>
<td width="283">
<p><strong>show all nodes</strong></p>
</td>
<td width="312">
<p>Shows all objects and links in this table.</p>
</td>
</tr>
<tr>
<td width="283">
<p><strong>clear input links</strong></p>
</td>
<td width="312">
<p>Clears all input links from objects in the Schema.</p>
</td>
</tr>
<tr>
<td width="283">
<p><strong>clear output links</strong></p>
</td>
<td width="312">
<p>Clears all <a href="/articles/03_logical_units/12_LU_hierarchy_and_linking_table_population.md">output links</a> from this LU table to its children Table Populations.</p>
</td>
</tr>
<tr>
<td width="283">
<p><strong>clear all links</strong></p>
</td>
<td width="312">
<p>Clears all <a href="/articles/03_logical_units/12_LU_hierarchy_and_linking_table_population.md">input and output</a> links in the LU tables.</p>
</td>
</tr>
<tr>
<td width="283">
<p><strong>show data</strong></p>
</td>
<td width="312">
<p>When clicked, a Query Builder window opens automatically in the newest LU file.</p>
<p><a href="/articles/13_LUDB_viewer_and_studio_debug_capabilities/01_data_viewer.md">Click for more information about the Data Viewer</a>.</p>
</td>
</tr>
</tbody>
</table>
<p>&nbsp;</p>


**For Example**


Taking the CONTRACT table from the CUSTOMER LU as an example, the following illustrates key table relationship view options:

Show only predecessor nodes

![image](/articles/12_LU_navigation/images/10_01_03%20predecessor%20nodes.jpg)


Show only successor nodes
![image](/articles/12_LU_navigation/images/10_01_04%20successor%20nodes.jpg)


Show only connected nodes
![image](/articles/12_LU_navigation/images/10_01_05%20connected%20nodes.jpg)


**Display Options** 
 
In the LU working area right click anywhere to display a context menu with the following actions:

<table width="595">
<tbody>
<tr>
<td width="198pxl">
<p><strong>Collapse All Views</strong></p>
</td>
<td width="700pxl">
<p>Collapses the LU table columns.</p>
</td>
</tr>
<tr>
<td width="198">
<p><strong>Expand All Views</strong></p>
</td>
<td width="397">
<p>Expands the LU tables display.</p>
</td>
</tr>
<tr>
<td width="198">
<p><strong>show all nodes</strong></p>
</td>
<td width="397">
<p>Shows all objects and links in the LU Schema.</p>
</td>
</tr>
<tr>
<td width="198">
<p><strong>Automatic Layout</strong></p>
</td>
<td width="397">
<p>Arranges table items in an orderly manner.</p>
</td>
</tr>
<tr>
<td width="198">
<p><strong>Automatic Layout and Fit</strong></p>
<p>&nbsp;</p>
</td>
<td width="397">
<p>Arranges table items in an orderly manner and adjusts the Table Population resolution to fit the screen.</p>
</td>
</tr>
</tbody>
</table>

[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/12_LU_navigation/02_searching_a_fabric_project.md) 
