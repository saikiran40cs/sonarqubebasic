## Analyse using SonarQube {#during-analysis}

---

## **Unrecognized files** {#unrecognized-files}

By default, only files that are recognized by a language plugin are loaded into the project during analysis. For example if your SonarQube instance has the Java and JavaScript plugins on board, all .java and .js files will be loaded, but .xml files will be ignored. However, it is possible to import all text files in the analysis encoding in a project by setting **Settings &gt; Exclusions &gt; Files &gt;** Import unknown files to true.

## **During Analysis** {#during-analysis}

During analysis, data is requested from the server, the files provided to the analysis are analyzed, and the resulting data is sent back to the server at the end in the form of a report, which is then analyzed asynchronously server-side.

Analysis reports are queued, and processed sequentially, so it is quite possible that for a brief period after your analysis log shows completion, the updated values are not visible in your SonarQube project. However, you will be able to tell what's going on because an icon will be added next to the project name. Mouse over it for more detail \(and links if you're logged in with the proper permissions.\)

