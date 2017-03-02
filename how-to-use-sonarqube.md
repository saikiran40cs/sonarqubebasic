## Usage of SonarQube**:** {#during-analysis}

To start the SonarQube always start the service from C:\sonarqube\bin\windows-x86-xx\StartSonar.bat and login the web console by entering [http://localhost:9000](http://localhost:9000/) \(default System administrator credentials are admin/admin\)

![](/assets/SonarQubeViewer.png)

If you want to validate the project then first you must navigate to the project folder in command prompt and hit the following command

_C:\sonar-scanner-2.7\bin\sonar-scanner.bat_

The above command requires the **sonar-project.properties** file to be available in the project location otherwise it gives error messages.

So, use the below code to create the sonar-project.properties file to compile the code and analyse it.

```
#Required metadata
sonar.projectKey=org.sonarqube:WAS_Sovellukset
sonar.projectName=Java :: Test Project:: SonarQube Scanner
sonar.projectVersion=1.0
# Comma-separated paths to directories with sources (required)
sonar.sources=src
# Language
sonar.language=java
# Encoding of the source files
sonar.sourceEncoding=UTF-8
```

After saving the above code try to run the code using the following lines

_cd C:\&lt;workspace location&gt;\&lt;ProjectName&gt;\_

_C:\sonar-scanner-2.7\bin\sonar-scanner.bat_

![](/assets/SonarQubeViewerCmd.png)

After we get a success message we can view it in console.

