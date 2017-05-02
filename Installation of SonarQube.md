## Instal**lation of SonarQube on SQL Server:** {#during-analysis}

**Infrastructure Setup:**

This is a single box set up of SonarQube on a Windows Server 2012 R2.

Pr**re-Requisities:**

In order to set up SonarQube on a windows server backed by Sql server Windows Authentication the following prerequisites are required…

1. Install Java SE
2. Download SonarQube binaries: Download the latest [SonarQube ](http://www.sonarqube.org/downloads/)bits from the SonarQube download page 
3. Install SQL Server 2014: SonarQube supports various database backend technologies. I’ll be using SQLServer 2014. SonarQube supports SQL Server 2008 and above including SQL Azure. Install SQL Server using the defaults in the wizard. I’ve named the default database instance MSSQLServer

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

  # Run SonarQube without installation on your machine {#run-sonarqube-without-installation}

  * Navigate to the earlier download location of SonarQube. Right click the zip file and choose **unblock**.

  * Unzip the file and copy the binaries to the folder C:\SonarQube\

  * Open the SonarQube properties file **sonar.properties** from the following location C:\SonarQube\sonarqube-6.3.1\conf.

  * In the sonar.properties file look for ‘\#—– Microsoft SQLServer 2008/2012/2014 and SQL Azure’. This needs to have the connection string for the sql server database you intend to use.

  * Update the section by adding the connection string of the database

  ```
  sonar.jdbc.url=jdbc:sqlserver://localhost:<portnumber if otherthan 8080>;databaseName=sonar;integratedSecurity=true
  ```

  ![](http://www.visualstudiogeeks.com/images/screenshots/tarun/SonarQube/sonarqubesqldatabaseconnectionstring.png "StartSonar without install SQL connection string")

  * For Integrated Security to work, you have to download the Microsoft SQL JDBC driver package from 
    [http://www.microsoft.com/en-us/download/details.aspx?displaylang=en&id=11774](http://www.microsoft.com/en-us/download/details.aspx?displaylang=en&id=11774)
     and copy sqljdbc\_auth.dll to your system32 folder.

  ![](/assets/sonarQubeSQLWindowsAuthDrivers.png)

  * Launch a command prompt as administrator. Navigate to C:\SonarQube\sonarqube-6.3.1\bin\windows-x86-64 and run the below listed command.

  * At this point you should see the SonarQube running up in a local webserver mode. Open a browser and navigate to [http://localhost:9000](http://localhost:9000). Since this is the first time, SonarQube will deploy the schema to the sonar database.

  > SonarQube uses 9000 as the default port, you can change this to another port from the sonar.properties file.

  ![](/assets/sonarQubeDefaultPortSetting.png)

  > Remember to look into the log file located at C:\SonarQube\sonarqube-6.3.1\logs if you run into any exceptions. The error messages are quite well documented.

  If you accidently left the database collation to case insensitive you are bound to hit some exceptions…

  > If the database has set up with case insensitive or there are issues with the user permissions expect to see exceptions. The best way to get to the bottom of the issue is to look at the log file available here… C:\SonarQube\sonarqube-6.3.1\logs.

# Install SonarQube on your machine and run as a service {#install-sonarqube-and-run-as-a-service}

In the last section by running SonarQube in commandline we have proven that all required configuration, frameworks and permissions are correct. In this section we’ll install SonarQube as a windows service.

Open up a command line as an administrator and navigate to the folder C:\SonarQube\sonarqube-5.4\bin\windows-x86-64. Invoke InstallNTService.bat. This will install SonarQube as a service.

In run prompt type `services.msc` and search for SonarQube service. Change the service logon user account to SonarUser. Start the service and refresh the services console after a few seconds to ensure that the service hasn’t failed. If the service has failed to start look in the log file to see the reason for the failure.

![](/assets/SonarQubeStartWindowsService.png)

Now open up an instance of the browser and navigate to localhost:9000 to see the SonarQube website being returned from the process running as a windows service.

You can log in to the SonarQube website by using the default account admin // admin.

![](/assets/SonarQubeAsWindowsServiceCompleted.png)

> If you have run into some issues, I recommend you to run the entire SonarQube set up as Administrator.



