# SonarQube {#sonarqube}

**Getting Started With SonarQube**

**Pre Requisite**

You must have proper permission to use this software as it is under General Lesser Public License.

For running SonarQube is that you need to have Java (Oracle JRE 8 onwards or OpenJDK 8 onwards) installed on your machine.

![(warning)](export/assets/warning.png) **Note**: _On Mac OS X it is highly recommended to install Oracle JDK 8 (or higher) instead of the corresponding Oracle JRE since the JRE installation does not fully set up your Java environment properly._

**Hardware Requirements**

1.  The SonarQube server requires at least 2GB of RAM to run efficiently and 1GB of free RAM for the OS.
2.  The amount of disk space you need will depend on how much code you analyze with SonarQube. As an example, SonarQube.com the public instance of SonarQube, has more than 25 millions lines of code under analysis with 4 years of history. SonarQube.com is currently running on a Amazon EC2 c3.large instance, using about 10 Gb of drive space. It handles 320+ projects having roughly 3M open issues. SonarQube.com is running on PostgreSQL 9.5 and it is using about 15Gb of drive space.
3.  SonarQube must be installed on hard drives that have excellent read &amp; write performance. Most importantly, the &quot;data&quot; folder houses the Elasticsearch indices on which a huge amount of I/O will be done when the server is up and running. Great read &amp; write hard drive performance will therefore have a great impact on the overall SonarQube server performance.

**About the Software:**

**SonarQube**

**SonarQube® **platform is an open source quality management platform, dedicated to continuously analyzing and measuring the technical quality of source code, from project portfolio down to the method level, and tracking the introduction of new Bugs, Vulnerabilities, and Code Smells in the Leak Period.

SonarQube can perform analysis on 20+ different languages. The outcome of this analysis will be quality measures and issues (instances where coding rules were broken). However, what gets analyzed will vary depending on the language:

*   On all languages, &quot;blame&quot; data will automatically be imported from supported SCM providers. Git and SVN are supported automatically. Other providers require [additional plugins](http://docs.sonarqube.org/display/PLUG/Plugin+Library).
*   On all languages, a static analysis of source code is performed (Java files, COBOL programs, etc.)
*   A static analysis of compiled code can be performed for certain languages (_.class_ files in Java, _.dll_ files in C#, etc.)
*   A dynamic analysis of code can be performed on certain languages.