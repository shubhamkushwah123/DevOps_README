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
        <version>2.1.7.RELEASE</version>
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

> 6. Create a directory named "static" in src/main/resources folder and then create index.html file inside static folder and then paste the below content.

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
