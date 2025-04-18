# Hello Java Maven

This is a simple Java application that prints a message to the console, built using Maven and Jenkins.

## Project Structure

hello-java-maven/ ├── pom.xml └── src/ └── main/ └── java/ └── HelloWorld.java


## Objective

The objective of this project is to set up a **Java Maven build job** in Jenkins. This is a basic example to demonstrate the integration of Jenkins with Maven for Continuous Integration (CI).

### Build Flow

1. **Clean** the workspace to remove any previously compiled files.
2. **Package** the application into a JAR file using Maven.

## Prerequisites

- **Java JDK 8 or 11** (required to compile the Java application)
- **Maven** (used to build the application)
- **Jenkins** (used for automating the build process)

## Setup

1. **Create the Java Application**

   In the `src/main/java/HelloWorld.java` file, the following Java code is written:

   ```java
   public class HelloWorld {
       public static void main(String[] args) {
           System.out.println("Hello, Jenkins + Maven!");
       }
   }

   Create the pom.xml File

Here's the pom.xml file configuration for Maven:

<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>
    <artifactId>hello</artifactId>
    <version>1.0</version>

    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.8.1</version>
                <configuration>
                    <source>1.8</source>
                    <target>1.8</target>
                </configuration>
            </plugin>
        </plugins>
    </build>
</project>

Jenkins Setup
Install Required Tools

Go to Manage Jenkins → Global Tool Configuration.

Add Maven (e.g., Maven 3.8.6).

Make sure you have Java JDK 8 or 11 installed.

Create a Jenkins Freestyle Job

Go to Jenkins Dashboard → New Item → Freestyle Project.

In the Build section, select Invoke top-level Maven targets.

Set the Goal to clean package.

Run the Build

After setting up the job, click Save and then Build Now.

You should see the "BUILD SUCCESS" message in the console output.


Console Output
Once the build is complete, the console output should show:

pgsql

[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  31.817 s
[INFO] Finished at: 2025-04-18T16:14:24+05:30
[INFO] ------------------------------------------------------------------------

Conclusion
This setup allows you to automate the build process using Jenkins and Maven. You can extend this setup to deploy the application, run tests, and integrate with other tools.





















