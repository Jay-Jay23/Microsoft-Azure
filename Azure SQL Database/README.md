# Create a SQL database

# Summary
<p>Organisation has chosen Azure SQL Database for part of its migration to the cloud. Been tasked with creating the database.
In this exercise, will create a SQL database in Azure and then test query the data in that database.</p>

<p>Azure SQL Database is a relational database based on the latest stable version of the Microsoft SQL Server database engine. SQL Database is a high-performance, reliable, fully managed, and secure database. You can use it to build data-driven applications and websites in the programming language of your choice, without needing to manage infrastructure.</p>

# Task 1: Create the database
<ul>
  <li>Sign in to the Azure portal.</li>
  <li>Select <b>Create a resource</b> > <b>Databases</b> > <b>SQL database</b>. The Create SQL Database pane appears.</li>
  <li>Enter the following values for each setting.</li>
  <img src="https://github.com/Jay-Jay23/Microsoft-Azure/blob/main/Azure%20SQL%20Database/image/Create%20a%20SQL%20database.png" alt="SQL">
  <li>Enter the following values for each setting.</li>
   <img src="https://github.com/Jay-Jay23/Microsoft-Azure/blob/main/Azure%20SQL%20Database/image/Create%20a%20SQL%20database2.png" alt="SQL">
  <li>Select OK.</li>
  <li>Complete the remaining fields for <b>Create SQL Database</b> using the following values.</li>
  <img src="https://github.com/Jay-Jay23/Microsoft-Azure/blob/main/Azure%20SQL%20Database/image/Create%20a%20SQL%20database3.png" alt="SQL">
  <img src="https://github.com/Jay-Jay23/Microsoft-Azure/blob/main/Azure%20SQL%20Database/image/Create%20a%20SQL%20database4.png" alt="SQL">
  <li>Select <b>Next : Networking</b>, and configure the following settings (accept defaults for fields not specified).</li>
  <img src="https://github.com/Jay-Jay23/Microsoft-Azure/blob/main/Azure%20SQL%20Database/image/Create%20a%20SQL%20database5.png" alt="SQL">
  <li>Select <b>Next : Security</b>, and for Enable Azure Defender for SQL, choose Not now. Leave the remaining settings as default (not configured).</li>
  <img src="https://github.com/Jay-Jay23/Microsoft-Azure/blob/main/Azure%20SQL%20Database/image/Create%20a%20SQL%20database6.png" alt="SQL">
  <li>Select <b>Next : Additional settings</b>, and configure the following settings.</li>
  <img src="https://github.com/Jay-Jay23/Microsoft-Azure/blob/main/Azure%20SQL%20Database/image/Create%20a%20SQL%20database7.png" alt="SQL">
  <li>Select <b>Review + create</b> to validate configuration entries.</li>
  <li>Select <b>Create</b> to deploy the server and database. It can take approximately two to five minutes to create the server and deploy the sample database. The deployment pane shows the status, with updates for each resource that is created.</li>
  <li>When deployment is complete, select <b>Go to resource</b>. The db1 SQL database Overview pane shows the essentials of the newly deployed database</li>
  <li>In the command bar, select <b>Set server firewall</b>. The Firewall settings page appears.</li>
  <li>Check the box next to <b>Allow Azure services and resources</b> to access this server at the bottom of the page, leaving other settings as default.</li>
  <li>Select <b>Save</b> to update firewall settings, then close the Firewall settings pane.</li>
  </ul>
  
  # Task 2: Test the database
<ul>
    <li>In Azure resources menu, select <b>All resources</b>. Search for and select the SQL database resource Type, and ensure that your new database was created.
      You might need to refresh the page.</li>
  <img src="https://github.com/Jay-Jay23/Microsoft-Azure/blob/main/Azure%20SQL%20Database/image/test%20database.png" alt="test database">
  <li>Select <b>db1</b>, the SQL database you created.</li>
  <li>In the SQL database menu, select <b>Query editor (preview)</b>. The <b>Query editor (preview)</b> pane appears.</li>
  <img src="https://github.com/Jay-Jay23/Microsoft-Azure/blob/main/Azure%20SQL%20Database/image/test%20database2.png" alt="test database">
  <li>Sign in as sqluser, with the password Pa$$w0rd1234.</li>
  <p>You will not be able to sign in because your IP address needs to be enabled in a firewall rule.</p>
  <img src ="https://github.com/Jay-Jay23/Microsoft-Azure/blob/main/Azure%20SQL%20Database/image/test%20database3.png" alt="test database">
  <li>In the Query editor menu, select <b>Overview</b> (your edits will be lost), and in the command bar, select <b>Set server firewall</b>. The <b>Firewall settings</b> page appears.</li>
  <li>In the <b>Client IP address</b> section, your IP will be shown (verify that it is the same client IP address from the error you received in the previous step).</li>
  <li>In the command bar select <b>Add your client IPv4 address</b>. This will add a <b>Rule name</b> that contains your IP address in both the <b>Start IP</b> and <b>End IP</b> fields.</li>
  <li>Select <b>Save</b> to save this firewall rule.</li>
  <img src ="https://github.com/Jay-Jay23/Microsoft-Azure/blob/main/Azure%20SQL%20Database/image/test%20database4.png" alt="test database">
  <li>Select your db1 database in the breadcrumb at the top of the page to return to your SQL database, and then select <b>Query editor (preview)</b> from the       menu.</li>
<li>Sign in again as <b>sqluser</b>, with the password <b>Pa$$w0rd1234</b>. This time you should succeed. It might take a couple of minutes for the new firewall rule to be deployed. If you still get an error, verify the client IP address in the error, and return to <b>Firewall settings</b> to add the correct client IP address.</li>
<li>After you sign in successfully, the query pane appears. Enter the following SQL query into the editor pane.</li>
</ul>

## Code
``` sql
SELECT TOP 20 pc.Name as CategoryName, p.name as ProductName
FROM SalesLT.ProductCategory pc
JOIN SalesLT.Product p
ON pc.productcategoryid = p.productcategoryid;
```
