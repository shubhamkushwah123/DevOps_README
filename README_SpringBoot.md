# Instructions to create a SpringBoot Application

### Pre-requisite : 
Eclipse Neon or above , Java 1.8 and Maven 3.x needs to installed and path variable must be configured.

1. Create a Maven Project in Eclipse > Skip Archetype Selection > Provide Archetype details manually.
```bash
<groupId>org.devops</groupId>
<artifactId>devops-test-app</artifactId>
<version>0.0.1-SNAPSHOT</version>
 ```

2. open the pom.xml and add the following lines.
```bash
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
```


3. Create a class named Application in root package as mentioned below : 
> Application class needs to be annotated with @SpringBootApplication annotation.

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

4. Create a file index.html in webapp directory of application and paste the below content.

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

5. Right click on Application class and Run as Java Application.
> open your browser and type http://localhost:8080
