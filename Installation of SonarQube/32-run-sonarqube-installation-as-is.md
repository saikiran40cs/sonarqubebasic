# SonarQube - MySQL Server configuration {#sonarqube-pre-requisities-validation--configuration}

**MySQL Setup**:

MySQL Server Community Edition for Windows can be installed using the MySQL Installer that installs and updates all MySQL products on Windows or the standalone .msi installation package.

**Important**

Installing MySQL Workbench using an Installer package requires either Administrator or Power User privileges.

#### Requirements for Windows

* Microsoft .NET Framework 4.5

* Microsoft Visual C++ 2015 Redistributable Package

  Note The 2013 version was changed to 2015 with MySQL Workbench 6.3.9.

Note: MySQL Workbench 6.1 supports earlier versions of Windows, including Vista.

#### Installation Using MySQL Installer

The general MySQL Installer download is available at [http://dev.mysql.com/downloads/windows/installer/](http://dev.mysql.com/downloads/windows/installer/). The MySQL Installer application can install, upgrade, and manage most MySQL products, including MySQL Workbench.

##### This is the Recommended Approach

Managing all of your MySQL products, including Workbench, with [MySQL Installer](http://dev.mysql.com/downloads/windows/installer/) is the recommended approach. It handles all requirements and prerequisites, configurations, and upgrades.

When executing [MySQL Installer](https://dev.mysql.com/doc/refman/5.7/en/mysql-installer.html), you may choose MySQL Workbench as one of the products to install. It is selected by default, and essentially executes the standalone Installer Package described below.

#### Installation Using the Installer Package

The standalone download is available at [http://dev.mysql.com/downloads/workbench/](http://dev.mysql.com/downloads/workbench/).

MySQL Server Community can be installed using the Windows Installer \(`.msi`\) installation package. The MSI package bears the name`mysql-server-community`-`version`-win`arch`.msi, where`version`_\_indicates the MySQL Workbench version number, and_`arch`\_the build architecture \(winx64\).

1. To install MySQL Workbench, right-click the MSI file and select the Install item from the pop-up menu, or double-click the file.

2. In theSetup Typewindow you may choose a`Complete`or`Custom`installation. To use all features of MySQL Workbench choose the`Developer(default)`option.

3. Unless you choose otherwise, MySQL is installed in`C:\%PROGRAMFILES%`\MySQL\MySQL Server`edition_type`\, where\_`%PROGRAMFILES%`\_is the default directory for programs for your locale. The`%PROGRAMFILES%`directory is defined as`C:\Program Files\`on most systems.

Once the installation is done configure the setup by changing the root password and remember for future purpose.

After the installation open the "MySQL Workbench 6.3 CE" and connect to the default instance by entering the root password.

Open a new query editor and run the query.

```
If Database Sonar already exists then use below ddl command.

DROP DATABASE 'sonar'

If Database Sonar Does NOT exists then enter below commands.

CREATE DATABASE sonar CHARACTER SET utf8 COLLATE utf8_general_ci;
CREATE USER ‘sonar’ IDENTIFIED BY 'sonar';
GRANT ALL ON sonar.* TO 'sonar’@'%' IDENTIFIED BY 'sonar';
GRANT ALL ON sonar.* TO 'sonar'@'localhost' IDENTIFIED BY 'sonar';
FLUSH PRIVILEGES;
```

Navigate to the earlier download location of SonarQube. Right click the zip file and choose unblock.

*  Unzip the file and copy the binaries to the folder C:\SonarQube\
* Open the SonarQube properties file sonar.properties from the following location C:\SonarQube\sonarqube-6.7.1\conf.
*  In the sonar.properties file look for ‘\#—– MySQL Server. This needs to have the connection string for the sql server database you intend to use.
* Update the section by adding the connection string of the database

```
# DATABASE
#
# IMPORTANT:
# - The embedded H2 database is used by default. It is recommended for tests but not for
#   production use. Supported databases are MySQL, Oracle, PostgreSQL and Microsoft SQLServer.
# - Changes to database connection URL (sonar.jdbc.url) can affect SonarSource licensed products.

# User credentials.
# Permissions to create tables, indices and triggers must be granted to JDBC user.
# The schema must be created first.
sonar.jdbc.username=sonar
sonar.jdbc.password=sonar

#----- Embedded Database (default)
# H2 embedded database server listening port, defaults to 9092
#sonar.embeddedDatabase.port=9092

#----- MySQL 5.6 or greater
# Only InnoDB storage engine is supported (not myISAM).
# Only the bundled driver is supported. It can not be changed.
sonar.jdbc.url=jdbc:mysql://localhost:3306/sonar?useUnicode=true&characterEncoding=utf8&rewriteBatchedStatements=true&useConfigs=maxPerformance&useSSL=false


#--------------------------------------------------------------------------------------------------
# WEB SERVER
# Binding IP address. For servers with more than one IP address, this property specifies which
# address will be used for listening on the specified ports.
# By default, ports will be used on all IP addresses associated with the server.
#sonar.web.host=0.0.0.0

# Web context. When set, it must start with forward slash (for example /sonarqube).
# The default value is root context (empty value).
sonar.web.context=/
# TCP port for incoming HTTP connections. Default value is 9000.
sonar.web.port=9081

```

Save and Start the Server to get the sonarqube service running.

