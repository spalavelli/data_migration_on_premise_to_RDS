#DATA migration from on premise MS-SQL server to RDS sql server

##Intriductionn 

  * This documentation outlines the steps for migrating a database from an on-premises MS SQL Server to an RDS SQL Server instance.

##pre-requisites

  * Access to the on-premises MS SQL Server instance.
 
  * Access to the RDS SQL Server instance.
 
  * SQL Server Management Studio (SSMS) installed on your local machine.

#launching an RDS Instance

  * Go to the AWS Management Console and select the RDS service.

  * Click on the "Create database" button to launch a new instance.

  * Choose the database engine you want to use (e.g. MySQL, PostgreSQL, etc.) and select the appropriate version.

  * 1.4. Choose the instance type and the amount of storage you need for your database.

  *  Set the network and security settings, such as VPC, subnets, security groups, and publicly accessible settings.

  *  Set the database options such as the database name, username, and password.

  *  Configure the backup and maintenance settings for your database.

  * Review your settings and click on the "Launch DB instance" button.

#Connecting to the RDS Instance

  * Go to the RDS dashboard and select the instance you just created.
  
  * Click on the "Connectivity & Security" tab and note the endpoint, port, username, and password.
  
  * Connect to the RDS instance using a SQL client or other database tools.

#connecting windows MS-SQL server via an EC2 instance RDP client

  * select the sql server EC2 instance and connect to instance
 
  * select RDP client and login with ms-sql server credentials

#authenticating windows sql server database and RDS database 
  
 windows DB:

  * give a server name authenticate with windows sql server db credential and connect.

 RDS DB:
  
  * give server name as RDS endpoint, authenticate with SQL Server Authenticate credentials, create new DB.

#exporting data from ON-premise to REMOTE

 # Data Source

  * Right click on the db which you want to export `tasks`, click `Export Data` you will able to see wizard like choose a data source window, data source SQL server Native client 11.0 for latest, check the details of DB server and clicke next.  
  
 # Destination Source

  * select SQL server native client 11.0, Server name is endpoint of RDS instance database, use SQL sserver Authenticate with RDS DB credentials, and select new db which you have created, click next.
 
  * select Copy data from one or more tables or views
  
  * here you can check the source and destination server names 

  * and, seletc the all tables or individual tables which you want to export click next, RUN immedietly 
  
  * it will start start exporting data, you will see there like total number of tables, how many have exported, errors, and wornings.
  
  * if there are any error you can see the error msg 

##Conclusion

  This documentation outlines the high-level steps for migrating a database from an on-premises MS SQL Server to an RDS SQL Server instance. The exact steps may vary depending on your specific setup and requirements. However, following these steps should help you successfully migrate your database to an RDS SQL Server instance.





