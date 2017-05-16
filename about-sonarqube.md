## About SonarQube {#during-analysis}

**SonarQube® **platform is an open source quality management platform, dedicated to continuously analyzing and measuring the technical quality of source code, from project portfolio down to the method level, and tracking the introduction of new Bugs, Vulnerabilities, and Code Smells in the Leak Period.

SonarQube can perform analysis on 20+ different languages. The outcome of this analysis will be quality measures and issues \(instances where coding rules were broken\). However, what gets analyzed will vary depending on the language:

* On all languages, "blame" data will automatically be imported from supported SCM providers. Git and SVN are supported automatically. Other providers require [additional plugins](http://docs.sonarqube.org/display/PLUG/Plugin+Library).
* On all languages, a static analysis of source code is performed \(Java files, COBOL programs, etc.\)
* A static analysis of compiled code can be performed for certain languages \(_.class_ files in Java, _.dll_ files in C\#, etc.\)
* A dynamic analysis of code can be performed on certain languages.



