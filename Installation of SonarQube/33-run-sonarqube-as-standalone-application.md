# Install SonarQube on your machine and run as a service {#install-sonarqube-and-run-as-a-service}

In the last section by running SonarQube in command line we have proven that all required configuration, frameworks and permissions are correct. In this section we’ll install **SonarQube as a windows service.**

If you want to change the default URL of SonarQube then update the following in _**sonar.properties under configuration folder\(conf\)of sonarQube**_ installation.

```
sonar.web.host=0.0.0.0

# Web context. When set, it must start with forward slash (for example /sonarqube).
# The default value is root context (empty value).
sonar.web.context=/
# TCP port for incoming HTTP connections. Default value is 9000.
sonar.web.port=<to the port number you want to change>
```

Open up a command line as an **administrator **and navigate to the folder _C:\SonarQube\sonarqube-6.3.1\bin\windows-x86-64_. Invoke _InstallNTService.bat_. This will install SonarQube as a service.

In run prompt type `services.msc` and search for SonarQube service. Change the service logon user account to the desired account \(In my case it is SonarUser\). Start the service and refresh the services console after a few seconds to ensure that the service hasn’t failed. If the service has failed to start look in the log file to see the reason for the failure.

![](/assets/SonarQubeStartWindowsService.png)

Now open up an instance of the browser and navigate to **localhost:9000** to see the SonarQube website being returned from the process running as a windows service.

You can log in to the SonarQube website by using the default account _admin/admin_.

![](/assets/SonarQubeAsWindowsServiceCompleted.png)

> If you have run into some issues, I recommend you to view the Logs section in the SonarQube installation directory. At enterprise level installation it is recommended to be performed by the installation team.



