# How to create a new Java25 Project with VSCode and MavenSample

## 1. Install VSCode

<img width="1485" height="381" alt="image" src="https://github.com/user-attachments/assets/4d69469e-a2f7-4af9-a7eb-c7e84321976e" />

## 2. Install Java

<img width="1552" height="603" alt="image" src="https://github.com/user-attachments/assets/abff68f5-624e-4456-b764-f155f7c220aa" />

## 3. Install Maven

<img width="1547" height="618" alt="image" src="https://github.com/user-attachments/assets/23786dd0-6253-4f55-b327-d98bb5867a9f" />

## 4. Install Extesion "Extension Pack for Java" in VSCode

<img width="1046" height="177" alt="image" src="https://github.com/user-attachments/assets/a6a2f175-15cf-47e0-9c7a-d50ebe78cff3" />

## 5. Install Extension "Gemini Code Assist" in VSCode

<img width="716" height="177" alt="image" src="https://github.com/user-attachments/assets/cda6eb57-74b6-481b-834a-765cc9798f18" />

## 6. Create a new Java Project with Maven

<img width="1919" height="738" alt="image" src="https://github.com/user-attachments/assets/ec275940-4dab-4a37-9022-5a1c6b612f2d" />

<img width="1337" height="738" alt="image" src="https://github.com/user-attachments/assets/ef8db14e-4935-49eb-b318-5da919379602" />

<img width="767" height="112" alt="image" src="https://github.com/user-attachments/assets/41899546-f028-4da9-bb6a-0e587e1c218e" />

<img width="757" height="114" alt="image" src="https://github.com/user-attachments/assets/61601c6f-fbd5-4e91-8c38-709457268804" />

<img width="1067" height="730" alt="image" src="https://github.com/user-attachments/assets/91aadb8a-abb3-46b5-879d-2706466efed7" />

<img width="569" height="117" alt="image" src="https://github.com/user-attachments/assets/8f2e51e8-f8fc-446f-9d93-649f9c4a6f62" />

We can review the new Java project folders and files structure

<img width="444" height="396" alt="image" src="https://github.com/user-attachments/assets/3ae98296-f620-4a36-882e-c2750e7219fe" />

We also can see the code (Main.java):

<img width="1184" height="513" alt="image" src="https://github.com/user-attachments/assets/be892cb2-4129-47b8-b468-8fea167d27a6" />

Also we review the dependencies (pom.xml):

<img width="1715" height="509" alt="image" src="https://github.com/user-attachments/assets/3e985c00-bcc3-410f-9696-796f9504765d" />

## 7. Run the application with VSCode

<img width="1916" height="745" alt="image" src="https://github.com/user-attachments/assets/8d4459de-1cf0-47d7-a0b5-e3fdb4247b0f" />

## 8. We can create a "launch.json" file for Debugging the Java Project with VSCode

We click on the "create a launch.json file" link

<img width="511" height="457" alt="image" src="https://github.com/user-attachments/assets/e24e739e-1223-4473-8b11-72f23d4b4774" />

And we select the debugger "Java"

<img width="762" height="321" alt="image" src="https://github.com/user-attachments/assets/9b941267-8c25-4925-874c-76a2c7068bf9" />

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

<img width="1134" height="533" alt="image" src="https://github.com/user-attachments/assets/755e82ae-dfea-464d-8c38-4e67dae926b3" />

We start debugging 

<img width="678" height="169" alt="image" src="https://github.com/user-attachments/assets/c626f585-c9a6-4224-83c9-5388f45d1955" />

We chech the result

<img width="1171" height="492" alt="image" src="https://github.com/user-attachments/assets/31352f2a-e587-4156-b75f-6b5913c75685" />

## 10. Running the application with Gemini

Prompt: "please run the java project"

<img width="473" height="450" alt="image" src="https://github.com/user-attachments/assets/fbf92ec0-55a5-4aef-a5f2-f567092604e7" />

## 11. Running the application with Copilot


## 12. How to Execute the Java Application with Maven

We are going to use two plugins:

**Apache Maven JAR Plugin**: Builds a Java Archive (JAR) file from the compiled project classes and resources.

https://mvnrepository.com/artifact/org.apache.maven.plugins/maven-jar-plugin

<img width="1509" height="780" alt="image" src="https://github.com/user-attachments/assets/baaf0f95-05a9-4019-925e-6caaa3d57344" />

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

<img width="1480" height="379" alt="image" src="https://github.com/user-attachments/assets/4f031bd5-bbb8-4f4a-a02f-77c3f4251089" />

```
mvn exec:java 
```

<img width="786" height="352" alt="image" src="https://github.com/user-attachments/assets/89270c2d-c771-48c8-b6ae-b838d29182d1" />


Or this command:

```
mvn -f demo/pom.xml compile exec:java
```

<img width="750" height="359" alt="image" src="https://github.com/user-attachments/assets/6ef0100f-ae61-4ad1-8e19-12f6d2f38d60" />

