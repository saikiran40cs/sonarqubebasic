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

MySQL Workbench can be installed using the Windows Installer \(`.msi`\) installation package. The MSI package bears the name`mysql-server-`_`community`_-_`version`_-win_`arch`_.msi, where_`version`_indicates the MySQL Workbench version number, and_`arch`_the build architecture \(winx64\).

1. To install MySQL Workbench, right-click the MSI file and select theInstallitem from the pop-up menu, or double-click the file.

2. In theSetup Typewindow you may choose a`Complete`or`Custom`installation. To use all features of MySQL Workbench choose the`Complete`option.

3. Unless you choose otherwise, MySQL is installed in`C:\`_`%PROGRAMFILES%`_\MySQL\MySQL Server_`edition_type`_\, where_`%PROGRAMFILES%`_is the default directory for programs for your locale. The`%PROGRAMFILES%`directory is defined as`C:\Program Files\`on most systems.



Once the installation is done configure the setup by changing the root password and remember for future purpose.



