# SonarQube Pre-requisities validation & configuration {#sonarqube-pre-requisities-validation--configuration}

To avoid hours of troubleshooting later, it’s best to validate the install & configuration thus far.

* **JAVA SE**: Validate the installation of JavaSE by running the following command on the commandline.

  ![](/assets/sonarqube-validatejavainstall.png)

* **JAVA Environment Variable**: Validate that the system environment variable has been updated with the java install location.

  ![](/assets/java-echopath.png)

* **SQL Setup**: Validate the SQL install. Open SSMS and connect to the sql server instance - .\MSSQLServer

  * Validate the installed version of SQL Server

```
select @@version
```

![](/assets/sqlserverversion.png)

* Validate the SQL Instance & Service name

```
select@@servername,@@servicename
```

![](/assets/sqlserverinstanceservice.png)

* **Database**: Create a new database ‘sonar’ \(all lowercase\)

  > This database collation needs to be Case Sensitive \(CS\) & Accent Sensitive \(AS\) - choose Latin1\_General\_CS\_AS.

  ![](/assets/sonarqube-sqlservercollation.png)

  The collation can be checked by running the following t-sql

```
SELECTCONVERT(varchar,SERVERPROPERTY('collation'));
```

![](/assets/sqlserverdatabasecollation.png)

* **SonarQube Service User**: Create a new windows user ‘SonarUser’. Give this user approprite permissions to the machine. Set this user up for access in the newly created database instance. Run the following command to check the permissions this user has in the database instance. Create a login for this user and permission this user with appropriate permission on the newly created sonar database to be able to create the schema.
* **Static Port**: In the default configuration of SQL Server, Dynamic port are enabled. SonarQube expects a static port to route the requests. Log into SQL Server configuration manager and follow the instructions here to enable the TCP/IP and disable dynamic ports. [https://msdn.microsoft.com/en-GB/library/ms177440.aspx](https://msdn.microsoft.com/en-GB/library/ms177440.aspx)

  > At this point we have all the pre-requisites installed & successfully configured. If any of the configuration validations have failed try restarting the machine and running the validations again…

  #  {#run-sonarqube-without-installation}



