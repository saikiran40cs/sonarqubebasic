# Naive Analysis using SonarQube

---

Below is the basic code to create the sonar-project.properties file to compile the code and analyse it.

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

If you want to validate the project then first you must navigate to the project folder in command prompt and hit the following command

> _sonar-scanner_

The above command requires the **sonar-project.properties** file to be available in the project location otherwise it gives error messages.After saving the above code try to run the code using the following lines

1. If you haven't set the environment variables then run using the following commands

> cd C:\&lt;workspace location&gt;\&lt;ProjectName&gt;\sonar-project.properties C:\&lt;sonar-scanner-installation directory&gt;\bin\sonar-scanner.bat

  2. If you have set the environment variables set for sonar scanner then type the following command

> sonar-scanner sonar-tester.properties

![](/assets/SonarQubeViewerCmd.png)

After we get a success message we can view it in the dashboard of sonarQube.

![](/assets/SonarQubeResult.png)

