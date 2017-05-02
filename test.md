## Instal**lation of SonarQube on SQL Server:** {#during-analysis}

**Infrastructure Setup:**

This is a single box set up of SonarQube on a Windows Server 2012 R2. In future post I’ll cover a more scaled out enterprise set up of SonarQube.

Prerequisites

In order to set up SonarQube on a windows server backed by Sql server Windows Authentication the following prerequisites

are required…

1. Install Java SE
2. Download SonarQube binaries: Download the latest SonarQube bits from the SonarQube download page http://www.sonarqube.org/downloads/
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



