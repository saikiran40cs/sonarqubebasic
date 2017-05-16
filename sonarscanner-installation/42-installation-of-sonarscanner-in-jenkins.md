# Configure SonarScanner in Jenkins {#InstallingandConfiguringSonarQubeScanner-Installation}

1. **Install the **[**SonarQube Scanner**](https://plugins.jenkins.io/sonar) **for Jenkins via the Jenkins Update Center**

![](https://nsaikiran.gitbooks.io/jenkins/content/assets/plugin_install.png)**b. Configure sonarqube server to Jenkins**

1. Configure your SonarQube server\(s\)
2. Log into Jenkins as an administrator and go to **Manage Jenkins &gt;  Configure System**: Scroll down to the **SonarQube configuration **section, click on **Add SonarQube **, and add the values you're prompted for.

![](/assets/SonarQube_JenkinsIns.JPG)

Generate the user token by logging into the SonarQube website and provide the key details in Jenkins for SonarQube versions above 5.2.

_**Step 3:**_**Configure the tools in Jenkins Global Configuration**

This step is mandatory if you want to trigger any of your SonarQube analyses with the SonarQube Scanner. You can define as many scanner instances as you wish. Then for each Jenkins job, you will be able to choose with which launcher to use to run the SonarQube analysis.

1. Log into Jenkins as an administrator and go to **Manage Jenkins  &gt; Global Tool Configuration**
2. Scroll down to the **SonarQube Scanner **configuration section and click on **Add SonarQube Scanner**. It is based on the typical Jenkins tool auto-installation. You can either choose to point to an already installed version of SonarQube Scanner \(uncheck 'Install automatically'\) or tell Jenkins to grab the installer from a remote location \(check '_Install automatically_'\).![](https://nsaikiran.gitbooks.io/jenkins/content/assets/sonarqube_scanner.png)

If you don't see a drop down list with all available SonarQube Scanner versions but instead see an empty text field then this is because Jenkins still hasn't downloaded the required update center file \(default period is 1 day\). You may force this refresh by clicking 'Check Now' button in **Manage Plugins &gt; Advanced tab**.



