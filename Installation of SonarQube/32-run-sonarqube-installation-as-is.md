# Run SonarQube without installation on your machine {#run-sonarqube-without-installation}

* Navigate to the earlier download location of SonarQube. Right click the zip file and choose **unblock**.

* Unzip the file and copy the binaries to the folder C:\SonarQube\

* Open the SonarQube properties file **sonar.properties** from the following location _C:\SonarQube\sonarqube-6.3.1\conf_.

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

If you accidentally left the database collation to case insensitive you are bound to hit some exceptions…

> If the database has set up with case insensitive or there are issues with the user permissions expect to see exceptions. The best way to get to the bottom of the issue is to look at the log file available here… C:\SonarQube\sonarqube-6.3.1\logs.



