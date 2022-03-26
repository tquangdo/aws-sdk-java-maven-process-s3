# aws-sdk-java-maven-process-s3 🐳

![Stars](https://img.shields.io/github/stars/tquangdo/aws-sdk-java-maven-process-s3?color=f05340)
![Issues](https://img.shields.io/github/issues/tquangdo/aws-sdk-java-maven-process-s3?color=f05340)
![Forks](https://img.shields.io/github/forks/tquangdo/aws-sdk-java-maven-process-s3?color=f05340)
[![Report an issue](https://img.shields.io/badge/Support-Issues-green)](https://github.com/tquangdo/aws-sdk-java-maven-process-s3/issues/new)

## reference
[docs.aws](https://docs.aws.amazon.com/sdk-for-java/latest/developer-guide/get-started.html)

## create project
```shell
mvn -B archetype:generate \
 -DarchetypeGroupId=org.apache.maven.archetypes \
 -DgroupId=com.example.myapp \
 -DartifactId=myapp
=>
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  01:11 min
[INFO] Finished at: 2022-03-26T17:14:54+09:00
[INFO] ------------------------------------------------------------------------
```

## Write the code
- `src/main/java/com/example/myapp/App.java` > `main(), tutorialSetup() & cleanUp()`

## Build and run
1. ### build
    ```shell
    mvn package
    =>
    Results :
    Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
    [INFO] 
    [INFO] --- maven-jar-plugin:2.4:jar (default-jar) @ myapp ---
    [INFO] Building jar: /Users/NC00011462/Documents/GitHub/myapp/target/myapp-1.0-SNAPSHOT.jar
    [INFO] ------------------------------------------------------------------------
    [INFO] BUILD SUCCESS
    [INFO] ------------------------------------------------------------------------
    [INFO] Total time:  2.587 s
    [INFO] Finished at: 2022-03-26T17:20:59+09:00
    [INFO] ------------------------------------------------------------------------
    ```
1. ### run
    1. #### case: NO cmt out cleanUp()
        ```shell
        mvn exec:java -Dexec.mainClass="com.example.myapp.App"
        =>
        Creating bucket: bucket1648282779238
        bucket1648282779238 is ready.
        Uploading object...
        Upload complete
        Cleaning up...
        Deleting object: key
        key has been deleted.
        Deleting bucket: bucket1648282779238
        bucket1648282779238 has been deleted.
        Cleanup complete
        Closing the connection to {S3}
        Connection closed
        ```
    1. #### case: cmt out cleanUp()
        ```shell
        mvn exec:java -Dexec.mainClass="com.example.myapp.App"
        =>
        Creating bucket: bucket1648282867392
        bucket1648282867392 is ready.
        Uploading object...
        Upload complete
        Closing the connection to {S3}
        Connection closed
        ```
        - see in AWS console S3: `Buckets>bucket1648282867392>key`
