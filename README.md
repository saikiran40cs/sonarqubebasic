# SonarQube {#sonarqube}

You must have proper permission to use this software as it is under General Lesser Public License.

For running SonarQube is that you need to have Java \(Oracle JRE 8 onwards or OpenJDK 8 onwards\) installed on your machine.

**Note**: _On Mac OS X it is highly recommended to install Oracle JDK 8 \(or higher\) instead of the corresponding Oracle JRE since the JRE installation does not fully set up your Java environment properly._

**Hardware Requirements**

1. The SonarQube server requires at least 2GB of RAM to run efficiently and 1GB of free RAM for the OS.
2. The amount of disk space you need will depend on how much code you analyze with SonarQube. As an example, SonarQube.com the public instance of SonarQube, has more than 25 millions lines of code under analysis with 4 years of history. SonarQube.com is currently running on a Amazon EC2 c3.large instance, using about 10 Gb of drive space. It handles 320+ projects having roughly 3M open issues. SonarQube.com is running on PostgreSQL 9.5 and it is using about 15Gb of drive space.
3. SonarQube must be installed on hard drives that have excellent read & write performance. Most importantly, the "data" folder houses the Elasticsearch indices on which a huge amount of I/O will be done when the server is up and running. Great read & write hard drive performance will therefore have a great impact on the overall SonarQube server performance.



