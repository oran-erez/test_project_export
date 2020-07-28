# Backup of Fabric Credentials

When testing the system, [user credentials setup](/articles/17_fabric_credentials/01_fabric_credentials_overview.md#setting-credentials) may need to be repeated for a number of reasons. For example, due to an environmental cleanup or when creating additional environments. 

To prevent data loss and to speed up the setup process, it is recommended to create a Crontab expression that periodically backs up the credentials. The backup script can export the data from [Cassandra](/articles/02_fabric_architecture/01_fabric_architecture_overview.md#cassandra-) into a text file. If needed, this data can be imported from the text file into Cassandra.  

### Example of Exporting Data

<pre><code> 
 echo "COPY k2auth.roles TO '$K2_HOME/k2auth.roles.csv' WITH HEADER = TRUE ;"|cqlsh -u[user] -p[password]
 echo "COPY k2auth.credentials TO '$K2_HOME/k2auth.credentials.csv' WITH HEADER = TRUE ;"|cqlsh -u[user] -p[password]
 echo "COPY k2auth.permissions TO '$K2_HOME/k2auth.permissions.csv' WITH HEADER = TRUE ;"|cqlsh -u[user] -p[password]
 echo "COPY k2auth.user_credentials TO '$K2_HOME/k2auth.user_credentials.csv' WITH HEADER = TRUE ;"|cqlsh -u[user] -p[password]
 echo "COPY system_auth.roles TO '$K2_HOME/system_auth.roles.csv' WITH HEADER = TRUE ;"|cqlsh -u[user] -p[password] 
 </code></pre>
### Example of Importing Data

<pre><code> 
echo "COPY k2auth.roles FROM '$K2_HOME/k2auth.roles.csv' WITH HEADER = TRUE ;"|cqlsh -u[user] -p[password]
echo "COPY k2auth.credentials FROM '$K2_HOME/k2auth.credentials.csv' WITH HEADER = TRUE ;"|cqlsh -u[user] -p[password]
echo "COPY k2auth.permissions FROM '$K2_HOME/k2auth.permissions.csv' WITH HEADER = TRUE ;"|cqlsh -u[user] -p[password]
echo "COPY k2auth.user_credentials FROM '$K2_HOME/k2auth.user_credentials.csv' WITH HEADER = TRUE ;"|cqlsh -u[user] -p[password]
echo "COPY system_auth.roles FROM '$K2_HOME/system_auth.roles.csv' WITH HEADER = TRUE ;"|cqlsh -u[user] -p[password]
</code></pre>
[![Previous](/articles/images/Previous.png)](/articles/17_fabric_credentials/02_fabric_credentials_commands.md)
