# Deploying a Fabric Project

### What Is Fabric Deployment?
The implementation of a Fabric project can be divided into two steps:
- **Design, configuration and coding**, which includes the creation of a Fabric project and the definition of the relevant objects in the Fabric Studio in order to implement the business requirements.
- **Deployment** of the project into the Fabric Server so that the first deployment of the new project or all recent changes since its last deployment are compiled and become effective on the server side. 

A deployment includes the definition of Fabric objects like the [LU Schema](/articles/03_logical_units/03_LU_schema_window.md), [LU Tables](/articles/06_LU_tables/01_LU_tables_overview.md), [Interfaces](/articles/05_DB_interfaces/03_DB_interfaces_overview.md), [Globals](/articles/08_globals/01_globals_overview.md), [Project functions](/articles/07_table_population/08_project_functions.md), [Web Services](/articles/15_web_services/01_web_services_overview.md), [Broadway flows], [Graphit] and [Translations](/articles/09_translations/01_translations_overview_and_use_cases.md) and is required whenever these objects are created or modified. 

Deployment is needed for any change operated in any of these objects, excluding the migration of source data into the Fabric Server. 
The deployment of a Fabric project is performed on the following levels:
- **Deployment of Logical Units**, each LU should be deployed separately. 
  - When needed, a deployment can be performed on a specific LU if only that LU has been modified.
- **Deployment of Broadway flows** as part of the LU to which they belong.
- **Deployment of References objects**, when they exist in a project. All Reference (common) tables are deployed together.
- **Deployment of Web Services**, when they exist in the project. The following deployment options are available: 
  - Deployment of all Web Services. 
  - Deployment of selected Web Services category files.  
  - Deployment of selected Web Services.
- **Deployment of Graphit**, when they exist in the project. The following deployment options are available: 
  - Each Graphit object can be deployed separately or all Graphit objects can be deployed as part of the Web Services. 
- **Deployment of Environments**.  <!--Future link to DROP 2 item-->

Deployment can be performed either:
- [From the Fabric Studio](/articles/16_deploy_fabric/02_deploy_from_Fabric_Studio.md#deploy-from-fabric-studio) using **Deploy to Server**.
- [Offline Deploy](/articles/16_deploy_fabric/03_offline_deploy.md) by creating the artifacts in the Fabric Studio using **Build Deploy Artifacts** and running the deployment on the server side. 

When a Fabric object is deployed to the server, the deployment artifacts are created in the **/storage/lu** directory of the Fabric Server – one **ludb.jar** for each deployment. 
A folder is created under **/storage/lu** for each object’s first deployment. For example, when the CRM LU is deployed for the first time, the CRM folder is created under **/storage/lu**. The **/storage/lu/CRM** will include the folder named as the deployment time and will include the **ludb.jar**.

Note that Shared Objects are not independent objects in a project and therefore cannot be deployed as stand-alone items. You must re-deploy the object using the updated Shared Object to make the change in a shared object available in the Fabric Server. For example, when an Interface is updated, all Logical Units using this Interface should be re-deployed to make this change effective.

### How Do I Check Which Project Is Deployed to Fabric? 
Only **one Project** can be deployed to [**each Fabric cluster**](/articles/02_fabric_architecture/01_fabric_architecture_overview.md#fabric-cluster). If a project has been deployed and an attempt to deploy a different project to the same cluster is made, an error message is displayed. 

To check the project’s deployment in the Fabric Server, use the **SET** command from the Fabric console. 
###### Syntax:
<pre><code>
    set;
</code></pre>

This command displays the currently **deployed project name**, as well as the values of various project parameters. 

[Click for more information about Fabric Basic Commands](/articles/02_fabric_architecture/04_fabric_commands.md#fabric-commands). 

### How Are Deployed Objects Reflected in the Fabric Server?
You can check which objects are deployed in the Fabric Server using the Fabric **list** command.
- **list LU_TYPES/LUT** provides a list of Logical Unit Types deployed to the Fabric Server.
- **list WS** provides a list of all Web Service methods deployed to the Fabric Server. 
- **list ENVIRONMENTS/ENVS** provides a list of environments deployed to the Fabric Server.
- **list BF/BROADWAY_FLOWS** - list all Broadway flows of all LU Types deployed to the Server.
- **list INSTANCE_GROUPS/IGS** - lists all instance groups of all LU Types deployed to the Server.
- **list DB_SOURCES** - list all the DB interfaces.

###### Syntax:
<pre><code> 
    list lut; 
    list lu_types;
    list ws;
    list ENVIRONMENTS; 
    list ENVS;
    list BF;
    list BROADWAY_FLOWS;
    list IGS;
    list INSTANCE_GROUPS;
    list DB_SOURCES;
</code></pre>

### How Are Deployed Objects Reflected in Cassandra?
Project deployment is reflected in [**Cassandra**](/articles/02_fabric_architecture/01_fabric_architecture_overview.md#cassandra-) as follows:
- The deployment of a [Logical Unit](/articles/03_logical_units/01_LU_overview.md), [References] <!--Future link to DROP 2 item-->and [Web Services](/articles/15_web_services/01_web_services_overview.md) creates new records in the [**k2_lut_info** table](/articles/02_fabric_architecture/06_cassandra_keyspaces_for_fabric.md) under the **k2system** keyspace. A separate record is created for each LU and Reference table and for each deployed Web Service.
- Each deployed LU creates a new Cassandra **keyspace** named **k2view_[LU Name]**.
- The first deployed WS creates a new Cassandra **keyspace** named **k2view_k2_ws**.
 
### How Do I Get the Deployed Implementation?
After the project is deployed to the server, there might be a need to clarify which code has been deployed in a specific environment. For example, if there are many code changes in the project and you need to verify whether a specific change has already been deployed to the server. Fabric supports the creation of a zip file for a selected LU name, so that the implementor can download the code deployed in the environment and check it.

###### Syntax:
<pre><code>
	http://[host]:3213/lut?lutName=[luname]&token=[token]
	http://[host]:3213/lut?lutName=k2_ws&token=[token]
	http://[host]:3213/lut?lutName=k2_ref&token=[token]
</code></pre>

The outcome of this command is that **ludbXMLs.zip** is downloaded to your local machine and can be opened in the Studio.


[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/16_deploy_fabric/02_deploy_from_Fabric_Studio.md)
