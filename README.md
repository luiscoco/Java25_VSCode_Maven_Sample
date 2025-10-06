# How to create a new Java25 Project with VSCode and MavenSample

## 1. Install VSCode

https://code.visualstudio.com/download

<img width="1372" height="939" alt="image" src="https://github.com/user-attachments/assets/862b17e7-6419-41c2-90f5-5cca23503d38" />

## 2. Install Java

https://www.oracle.com/es/java/technologies/downloads/#jdk25-windows

<img width="1714" height="939" alt="image" src="https://github.com/user-attachments/assets/2c33ca8b-9fdf-4412-a0c5-0ea2d58f55ec" />

We confirm the Java version installed:

```
java -version
```

<img width="963" height="122" alt="image" src="https://github.com/user-attachments/assets/611aa674-7567-45e5-9df1-39a0aa04c1c2" />

## 3. Install Maven

**Binary distribution**

To install **Apache Maven**, extract the archive and add its bin directory to the **PATH**. 

Detailed steps to install Maven:

1. Download the Apache Maven binary distribution archive.

https://maven.apache.org/download.cgi

<img width="1919" height="968" alt="image" src="https://github.com/user-attachments/assets/b2363dec-8d60-4234-80de-a9904407953a" />

https://maven.apache.org/install.html

2. Extract the distribution archive in any directory and copy and paste into the ProgramFiles folder.

<img width="1193" height="504" alt="image" src="https://github.com/user-attachments/assets/308f1b7a-0724-43c5-92c5-f8e5939dc340" />

3. Add the **bin** directory of the created directory apache-maven-3.9.11 to the **PATH environment variable**

<img width="827" height="773" alt="image" src="https://github.com/user-attachments/assets/50df4322-8e90-4478-af1b-6b714a9e2b7e" />

4. Confirm with **mvn -v** in a new shell.

<img width="1479" height="422" alt="image" src="https://github.com/user-attachments/assets/c8127ac8-1fcb-4b59-b846-661ef8374dab" />

## 4. Install Extesion "Extension Pack for Java" in VSCode

<img width="1919" height="1015" alt="image" src="https://github.com/user-attachments/assets/e1d3dafb-dd80-44f1-b5e5-a0e9b0894e2e" />

## 5. Install Extension "Gemini Code Assist" in VSCode

This is an AI programmer agent:

<img width="1525" height="608" alt="image" src="https://github.com/user-attachments/assets/61479a13-0cf9-48c7-92f8-3d86054fb3ec" />

## 5. (Optional) Install Extension "Codex"

This is an AI programmer agent:

<img width="1536" height="557" alt="image" src="https://github.com/user-attachments/assets/927a265e-884e-4ca5-bb8d-24e075786a7e" />

## 6. Create a new Java Project with Maven

We first press the following Keyword combination "Ctrl+Shift+P" and select the menu option "Java: Create Java Project..."

<img width="1455" height="552" alt="image" src="https://github.com/user-attachments/assets/fa2941d7-46f4-436e-9a93-f2ab0548f7d9" />

We can review the new Java project folders and files structure

<img width="518" height="619" alt="image" src="https://github.com/user-attachments/assets/7d11ba23-d6a0-4887-bd4a-cbfc99a40aa4" />

We also can see the code (Main.java):

<img width="714" height="335" alt="image" src="https://github.com/user-attachments/assets/96066f0f-7219-4121-af4d-9194eeba451e" />

Also we review the dependencies (pom.xml):

<img width="1911" height="633" alt="image" src="https://github.com/user-attachments/assets/a3b21873-2573-4c68-8ab4-46e956129d78" />

## 7. Run the application with VSCode

<img width="650" height="639" alt="image" src="https://github.com/user-attachments/assets/6ae80ae1-adcc-4fc3-ba04-7306080bbda8" />

## 8. We can create a "launch.json" file for Debugging the Java Project with VSCode

We click on the "create a launch.json file" link


And we select the debugger "Java"



We review the "launch.json" file content:

```json
{
    "version": "0.2.0",
    "configurations": [
        
        {
            "type": "java",
            "name": "Current File",
            "request": "launch",
            "mainClass": "${file}"
        },
        {
            "type": "java",
            "name": "Main",
            "request": "launch",
            "mainClass": "com.example.Main",
            "projectName": "demo"
        }
    ]
}
```

## 9. We debugg the Java Project

We set the debugging breakpoint in the code:


We start debugging 

We chech the result

## 10. Running the application with Gemini

Prompt: "please run the java project"


## 11. Running the application with Copilot


## 12. How to Execute the Java Application with Maven

We are going to use two plugins:

**Apache Maven JAR Plugin**: Builds a Java Archive (JAR) file from the compiled project classes and resources.

https://mvnrepository.com/artifact/org.apache.maven.plugins/maven-jar-plugin



**Exec Maven Plugin**: A plugin to allow execution of system and Java programs

https://mvnrepository.com/artifact/org.codehaus.mojo/exec-maven-plugin

<img width="1502" height="735" alt="image" src="https://github.com/user-attachments/assets/e9912cdc-bf2a-4d61-b34b-ee344f033db1" /

We modify the pom.xml file to invoke these two plugins:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>
    <artifactId>demo</artifactId>
    <version>1.0-SNAPSHOT</version>

    <properties>
        <maven.compiler.source>25</maven.compiler.source>
        <maven.compiler.target>25</maven.compiler.target>
    </properties>

        <build>
        <plugins>
            <plugin>
                <!-- Maven JAR Plugin Configuration -->
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-jar-plugin</artifactId>
                <version>3.4.2</version>
                <configuration>
                    <archive>
                        <manifest>
                            <mainClass>com.example.Main</mainClass>
                        </manifest>
                    </archive>
                </configuration>
            </plugin>

            <plugin>
                <!-- Exec Maven Plugin Configuration -->
                <groupId>org.codehaus.mojo</groupId>
                <artifactId>exec-maven-plugin</artifactId>
                <version>3.5.1</version>
                <configuration>
                    <mainClass>com.example.Main</mainClass>
                </configuration>
                <executions>
                    <execution>
                        <goals>
                            <goal>java</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
        </plugins>
    </build>

</project>
```

Now we run these command to build and execute the Java project with Maven:

```
mvn clean install
```


```
mvn exec:java 
```




Or this command:

```
mvn -f demo/pom.xml compile exec:java
```

<img width="750" height="359" alt="image" src="https://github.com/user-attachments/assets/6ef0100f-ae61-4ad1-8e19-12f6d2f38d60" />

