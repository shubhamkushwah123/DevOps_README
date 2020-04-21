# Instructions to create a SpringBoot Application

### Pre-requisite : 
Eclipse Neon or above , Java 1.8 and Maven 3.x needs to installed and path variable must be configured.


### 1. Create an Spring Boot Application
> 1. Open Eclipse and Create an Workspace.

> 2. File > New > Maven Project > Check (Skip Archetype selection) > Next > 

> 3. Provide the below details and Click on Finish.
```bash
Group Id : org.devops
Artifact Id : cicd-pipeline
Version : <keep it same>
Packaging = jar
```
> 4. A project will be created, open pom.xml and make it like this.
```bash
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>org.devops</groupId>
  <artifactId>devops-test-app</artifactId>
  <version>0.0.1-SNAPSHOT</version>
  
    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>2.0.3.RELEASE</version>
        <relativePath />
    </parent>
  
<dependencies>
	 <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
        </dependency>
</dependencies>

<properties>
	 <java.version>1.8</java.version>
</properties>
  
</project>
```


### 2. Build and Test the Application using MAVEN.

> 1. Open the Command Prompt and check maven installation.

```bash
mvn --version
```

> 2. Navigate to the project folder, where pom.xml resides and run below command to build the application.

```bash
mvn clean test install
```

### 3. Upload the Code to the GitHub Repository.

> 1. Create an account on https://www.github.com

> 2. Login to the Account.

> 3. Create a public repository.

> 4. Copy the repository url to clone. (e.g. It looks like this : https://github.com/shubhamkushwah123/DevOps.git)

> 5. Open command prompt in your machine and navigate to the project folder, where pom.xml resides.

> 6. Initializes the local git repository. (Inside the project folder, run below command)

```bash
git init

git config --global user.name = "your name"

git config --global user.email - "your email address that you have used to login to github"

git add .

git commit -m "Code commited to local repository"

git remote add origion <the git repository url that you have copied into the above steps>
git remote add origin https://github.com/shubhamkushwah123/DevOps.git

git push origin master
```

Note : Check the repository in github.com, Your application code should be there in your github repository.


## Creating Jenkins Pipeline

> 1. To Launch the Jenkins, Go to the folder, where jenkins.war is placed and run below command.
```bash
java -jar jenkins.war
```

> 2. Go the browser and open http://localhost:8080

> 3. Login with the admin user and password that you have created during first login after installation process.

Note : if not, please follow steps at > https://www.guru99.com/download-install-jenkins.html

> 4. Click on New Item > Choose Pipeline Project > Give any name (e.g. ci-pipeline) > hit Enter.

> 5. Create a class named Application in root package as mentioned below : 

Note : Application class needs to be annotated with @SpringBootApplication annotation.

```bash

package com;

import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class Application {
	private static final Logger log = LoggerFactory.getLogger(Application.class);

	public static void main(String[] args) {
		log.info("Main method has been invoked");
		SpringApplication.run(Application.class,args);
	}
}
```

> 6. Create a file index.html in webapp directory of application and paste the below content.

```bash
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>DevOps World</title>

</head>
<body style="background-color:aqua;text-align:center">
<h1>Congratulations!!! Welcome to the World of DevOps</h1>
</body>
</html>
```

> 7. Right click on Application class and Run as Java Application.

Note : open your browser and type http://localhost:8080
