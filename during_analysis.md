## **During Analysis** {#during-analysis}

During analysis, data is requested from the server, the files provided to the analysis are analyzed, and the resulting data is sent back to the server at the end in the form of a report, which is then analyzed asynchronously server-side.

Analysis reports are queued, and processed sequentially, so it is quite possible that for a brief period after your analysis log shows completion, the updated values are not visible in your SonarQube project. However, you will be able to tell what&#039;s going on because an icon will be added next to the project name. Mouse over it for more detail (and links if you&#039;re logged in with the proper permissions.)

**Getting Started in Two Mintes:**

1. [Download](http://www.sonarsource.org/downloads/) and unzip the SonarQube distribution (let&#039;s say in &quot;C:\sonarqube&quot; or &quot;/etc/sonarqube&quot;)

2\. Start the SonarQube server:

| **# On Windows, execute:** |
| --- |

3. [Download](http://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner) and unzip the SonarQube Scanner (let&#039;s say in &quot;C:\sonar-scanner&quot; or &quot;/etc/sonar-scanner&quot;)

4. [Download](https://github.com/SonarSource/sonar-examples/archive/master.zip) and unzip some project samples (let&#039;s say in &quot;C:\sonar-examples&quot; or &quot;/etc/sonar-examples&quot;)

5\. Analyze a project:

| **# On Windows:** |
| --- |

6\. Browse the results at [http://localhost:9000](http://localhost:9000/) (default [System administrator](http://docs.sonarqube.org/display/SONAR/Authorization) credentials are admin/admin)

**SonarQube – How to use**

To start the SonarQube always start the service from C:\sonarqube\bin\windows-x86-xx\StartSonar.bat and login the web console by entering [http://localhost:9000](http://localhost:9000/) (default System administrator credentials are admin/admin)

If you want to validate the project then first you must navigate to the project folder in command prompt and hit the following command

_C:\sonar-scanner-2.7\bin\sonar-scanner.bat_

The above command requires the **sonar-project.properties** file to be available in the project location otherwise it gives error messages.

So, use the below code to create the sonar-project.properties file to compile the code and analyse it.

| # Required metadata |
| --- |

After saving the above code try to run the code using the following lines

_cd C:\&lt;workspace location&gt;\&lt;ProjectName&gt;\_

_C:\sonar-scanner-2.7\bin\sonar-scanner.bat_

Now you can see the report in the web console.

**Report Generation in SonarQube**

After logging in as administrator into the Web Console you will be able to view

When you click on any of the respective columns like Code Smells it will display what needs to be done to change the code.

This is the beginning for learning ….