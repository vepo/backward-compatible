# Java Backward Compatible

The question is: how to build a Java library with module-info.java that can be executed in Java 8 applications?

Running with Java 8.

```bash
$ mvn clean package
[INFO] Scanning for projects...
[INFO]
[INFO] --------------------< io.vepo:backward-compatible >---------------------
[INFO] Building Backward Compatible 0.0.1-SNAPSHOT
[INFO] --------------------------------[ jar ]---------------------------------
[INFO]
[INFO] --- maven-clean-plugin:2.5:clean (default-clean) @ backward-compatible ---
[INFO] Deleting C:\Users\victoro\eclipse-workspace\backward-compatible\target
[INFO]
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ backward-compatible ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] skip non existing resourceDirectory C:\Users\victoro\eclipse-workspace\backward-compatible\src\main\resources
[INFO]
[INFO] --- maven-compiler-plugin:3.8.1:compile (default-compile) @ backward-compatible ---
[INFO] Changes detected - recompiling the module!
[INFO] Compiling 2 source files to C:\Users\victoro\eclipse-workspace\backward-compatible\target\classes
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.949 s
[INFO] Finished at: 2020-04-06T14:16:01-03:00
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-compiler-plugin:3.8.1:compile (default-compile) on project backward-compatible: Fatal error compiling: invalid flag: --release -> [Help 1]
[ERROR]
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR]
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/MojoExecutionException
```

Running with Java 14.

```bash
$ mvn clean package
[INFO] Scanning for projects...
[INFO]
[INFO] --------------------< io.vepo:backward-compatible >---------------------
[INFO] Building Backward Compatible 0.0.1-SNAPSHOT
[INFO] --------------------------------[ jar ]---------------------------------
[INFO]
[INFO] --- maven-clean-plugin:2.5:clean (default-clean) @ backward-compatible ---
[INFO] Deleting C:\Users\victoro\eclipse-workspace\backward-compatible\target
[INFO]
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ backward-compatible ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] skip non existing resourceDirectory C:\Users\victoro\eclipse-workspace\backward-compatible\src\main\resources
[INFO]
[INFO] --- maven-compiler-plugin:3.8.1:compile (default-compile) @ backward-compatible ---
[INFO] Changes detected - recompiling the module!
[INFO] Compiling 2 source files to C:\Users\victoro\eclipse-workspace\backward-compatible\target\classes
[INFO] -------------------------------------------------------------
[ERROR] COMPILATION ERROR :
[INFO] -------------------------------------------------------------
[ERROR] /C:/Users/victoro/eclipse-workspace/backward-compatible/src/main/java/module-info.java:[1,1] modules are not supported in -source 8
  (use -source 9 or higher to enable modules)
[INFO] 1 error
[INFO] -------------------------------------------------------------
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  1.337 s
[INFO] Finished at: 2020-04-06T14:15:30-03:00
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-compiler-plugin:3.8.1:compile (default-compile) on project backward-compatible: Compilation failure
[ERROR] /C:/Users/victoro/eclipse-workspace/backward-compatible/src/main/java/module-info.java:[1,1] modules are not supported in -source 8
[ERROR]   (use -source 9 or higher to enable modules)
[ERROR]
[ERROR] -> [Help 1]
[ERROR]
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR]
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/MojoFailureException
```