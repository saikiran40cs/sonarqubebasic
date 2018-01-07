## Instal**lation of SonarQube ** {#during-analysis}

## **SQL Server/MySQL Server:** {#during-analysis}

**Infrastructure Setup:**

This is a single box set up of SonarQube on a **Windows Server 2012 R2.**

**Pre-Requisities for standalone installation:**

In order to set up SonarQube on a windows server backed by Sql server Windows Authentication the following prerequisites are required…

1. Install Java SE
2. Download SonarQube binaries: Download the latest [SonarQube ](http://www.sonarqube.org/downloads/)bits from the SonarQube download page 
3. Install SQL Server 2014: SonarQube supports various database backend technologies. I’ll be using SQLServer 2014. SonarQube supports SQL Server 2008 and above including SQL Azure. Install SQL Server using the defaults in the wizard. I’ve named the _default database instance_ **MSSQLServer**
4. You can also install on MySQL Server Community Edition version 5.7

#  {#install-sonarqube-and-run-as-a-service}



