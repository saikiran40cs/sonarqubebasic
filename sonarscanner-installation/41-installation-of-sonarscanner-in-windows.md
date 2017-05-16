# Installation of SonarScanner {#InstallingandConfiguringSonarQubeScanner-Installation}

1. Expand the downloaded file into the directory of your choice. We'll refer to it as \_&lt;install\_directory&gt; \_in the next steps.
2. Update the global settings \(server URL\) by editing_&lt;install\_directory&gt;/conf/sonar-scanner.properties_:

   | `#----- Default SonarQube server#sonar.host.url=`[`http://localhost:9000`](http://localhost:9000/) |
   | :--- |

3. Create a new _SONAR\_RUNNER\_HOME \_environment variable set to _&lt;install\_directory&gt;\_.

4. Add the \_&lt;install\_directory&gt;/bin \_directory to your path.

5. You can check the basic installation by opening a new shell and executing the command`sonar-scanner -h`\(on Windows platform the command is`sonar-scanner.bat -h`\) . You should get a message like this:

```
usage: sonar-scanner [options]

Options:
 -D,--define <arg>     Define property
 -e,--errors           Produce execution error messages
 -h,--help             Display help information
 -v,--version          Display version information
 -X,--debug            Produce execution debug output
```

If you need more debug information you can add the`sonar.verbose`property by adding the command line parameter`-Dsonar.verbose=true`.

You are now ready to **analyze a project with the SonarQube Scanner.**

