# Fabric Troubleshooting Overview

Fabric provides the following methods for troubleshooting executed processes.

- **Log files**. All activities performed in Fabric are written into [log files](/articles/21_Fabric_troubleshooting/02_Fabric_troubleshooting_log_files.md) in the server. In addition the activities run on the local Fabric server started by the Studio are written to the [Log screen in the Fabric Studio](/articles/13_LUDB_viewer_and_studio_debug_capabilities/02_fabric_studio_log_files.md).  
- **Monitoring stuck processes**, using the following tools:

  - [**PS** command](/articles/02_fabric_architecture/04_fabric_commands.md#ps-and-kill-commands) – a Fabric command like User Jobs, [Web Services](/articles/15_web_services/01_web_services_overview.md), Graphit or a [Sync process](/articles/14_sync_LU_instance/01_sync_LUI_overview.md) which displays tasks running on the Fabric server. The PS command can be used to identify stuck processes and their running duration and when needed, to kill stuck processes using the [**kill** command](/articles/02_fabric_architecture/04_fabric_commands.md#ps-and-kill-commands).
  <!-- drop 3- add links to user jobs and graphit -->

  - [**jjstack.sh** script](/articles/21_Fabric_troubleshooting/01_Fabric_troubleshooting_overview.md#how-do-i-run-jjstack) – a Fabric script that collects Java stack traces for a given process, stores the stacks and analyzes the results. The script can be applied to the Fabric server or the IID Finder. 

- **Monitoring memory leaks or intensive memory consumption** using a [**Heap Dump**](/articles/21_Fabric_troubleshooting/01_Fabric_troubleshooting_overview.md#how-is-a-heap-dump-file-created) file which is created either automatically during a Fabric crash when memory usage exceeds the definition, or manually on demand. Heap Dump files can be investigated to analyze the source of a memory leak.

    

### How Do I Run jjstack?

Use cases for running **jjstack.sh** are:

- An explicit request from R&D to enable the investigation of a problem in Fabric.
- When you suspect that a job or a **Migrate** command is stuck.
- To investigate a performance issue in the implementation layer.

The procedure is to run the script. You can analyze the output either on your own or with the help of R&D.

The following table describes the syntax and the parameters for calling the **jjstack.sh** script. The script is located under **$K2_HOME/fabric/scripts** in the Fabric server.

<table>
<tbody>
<tr>
<td width="170px">
<p><strong>jjstack.sh</strong></p>
</td>
<td width="730px">
<p><strong>Description</strong>: The script collects Java stack traces of a given process, stores stacks into the store directory and analyzes the results.</p>
<p><strong>Usage</strong>: ./jjstack.sh [pid] [sample count] [store directory] [cutoff limit]</p>
<p><strong>Options</strong>:</p>
<ul>
<li>[pid] &ndash; optional parameter. Java process ID to sample. By default, the script scans the Fabric server - see Example 1. When this parameter is a default and other parameters must be provided, use &ldquo;&rdquo; - see Example 2.</li>
<li>[sample count] - optional parameter. Number of samples and number of output files created.</li>
<li>[store directory] - optional parameter. Location for storing output files that can be later analyzed. By default, the output directory is <strong>/tmp</strong>.</li>
<li>[cutoff limit] - optional parameter. Minimum number of appearances of the Java methods to show in the output file.</li>
</ul>
<p>Note that it is recommended to set both the sample count and the cutoff limit to proportional values. The recommended values are:</p>
<ul>
<li>Sample count = 100.</li>
<li>Cutoff limit = 30.</li>
</ul>
<p><strong>Examples:</strong></p>
<ul>
<li>Sample the Fabric server 100 times, create the files in /tmp. No cutoff limit:
<ul>
<li><strong>&nbsp;</strong>./jjstack.sh &nbsp;</li>
</ul>
</li>
<li>Sample&nbsp;the Fabric server 50 times, create the files in the <strong>js_iid1</strong> output directory. No cutoff limit:
<ul>
<li><strong>&nbsp;</strong>./jjstack.sh &ldquo;&rdquo; 50 js_iid1</li>
</ul>
</li>
<li>Sample the process 14323 100 times, create the files in the&nbsp;<strong>js_iid1</strong>&nbsp;output directory and output only entries with at least 30 appearances:
<ul>
<li>./jjstack.sh 14323 100 js_iid1 30</li>
</ul>
</li>
</ul>
</td>
</tr>
</tbody>
</table>


[Click to view the Example of the **jjstack** Output File.](/articles/21_Fabric_troubleshooting/images/jjstack.md)



### How Is a Heap Dump File Created?

A Heap Dump file is automatically created if Fabric crashes due to memory usage exceeding the definition. When required, a Heap Dump file can also be created manually using the **jmap** command. 

Default memory usage is defined in the **$K2_HOME/config/ jvm.options** configuration file and is equal to 2G.  The location of a Heap Dump file is defined in the **jvm.options** configuration file. If it is not defined there, it is created in the folder where Fabric is started, which is usually **$K2_HOME** or **$K2_HOME/fabric/scripts**. 

Note that Heap Dump files can take up a lot of disk space, therefore it is recommended to delete them after an investigation has been completed. Head Dump files should be uploaded to [K2view sftp dedicated servers](https://k2view.sharepoint.com/sites/Wiki/IT%20%20Technology/Heap%20dump%20upload%20point.aspx) in order to allow their analysis by the R&D team.
 

The following table describes the syntax and parameters for creating the Heap Dump file using the **jmap** command. 

<table>
<tbody>
<tr>
<td width="170px">
<p><strong>jmap -dump:&lt;dump-options&gt;</strong></p>
</td>
<td width="730px">
<p><strong>Description</strong>: To connect to the running process and to dump Java heap in hprof binary format</p>
<p><strong>Usage</strong>: jmap -dump:[dump-options] [pid]</p>
<p><strong>Options</strong>:</p>
<ul>
<li>Dump-options are:
<ul>
<li>live - dump only live objects. If not specified, all objects in the heap are dumped.</li>
<li>format=b - binary format.</li>
<li>file=&lt;file&gt; &nbsp;- dump heap to file in the local directory (scan be absolute path).</li>
</ul>
</li>
<li>[pid] - Fabric process ID.</li>
</ul>
<p><strong>Example</strong>:</p>
<p>jmap -dump:live,format=b,file=heap.bin &lt;pid&gt; &nbsp;</p>
</td>
</tr>
</tbody>
</table>

[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/21_Fabric_troubleshooting/02_Fabric_troubleshooting_log_files.md) 
