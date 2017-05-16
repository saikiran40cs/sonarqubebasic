## How to Analyse using SonarQube**:** {#during-analysis}



If you want to validate the project then first you must navigate to the project folder in command prompt and hit the following command

_C:\sonar-scanner-3.0.1.733\bin\sonar-scanner.bat_

The above command requires the **sonar-project.properties** file to be available in the project location otherwise it gives error messages.

So, use the below code to create the sonar-project.properties file to compile the code and analyse it.

```
#Required metadata
sonar.projectKey=org.sonarqube:<ProjectName>
sonar.projectName=Java :: Test Project:: SonarQube Scanner
sonar.projectVersion=1.0
# Comma-separated paths to directories with sources (required)
sonar.sources=src
# Language
sonar.language=java
# Encoding of the source files
sonar.sourceEncoding=UTF-8
```

###### \* - REPLACE WITH APPROPRIATE CONTENTS FOR THE LINES WITH ANGULAR BRACES &lt;&gt;

After saving the above code try to run the code using the following lines

_cd C:\&lt;workspace location&gt;\&lt;ProjectName&gt;\_

_C:\sonar-scanner-3.0.1.733\bin\sonar-scanner.bat_

![](/assets/SonarQubeViewerCmd.png)

After we get a success message we can view it in console.

