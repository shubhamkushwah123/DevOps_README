# Implement Junit 5 Test Suite with Spring Boot

Note : Follow the instructions after completing the instructions of README_SpringBoot.md.

> 1. Alter pom.xml in order to import Spring Boot Junit5 Libraries.

```bash
 <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>org.devops</groupId>
  <artifactId>cicd-pipeline</artifactId>
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
             <exclusions>
		    <exclusion>
		      <groupId>junit</groupId>
		      <artifactId>junit</artifactId>
		    </exclusion>
	     </exclusions>
        </dependency>
	<dependency>
	  <groupId>org.junit.jupiter</groupId>
	  <artifactId>junit-jupiter-api</artifactId>
	  <version>5.3.2</version>
	  <scope>test</scope>
	</dependency>
	<dependency>
	  <groupId>org.junit.jupiter</groupId>
	  <artifactId>junit-jupiter-engine</artifactId>
	  <version>5.3.2</version>
	  <scope>test</scope>
	</dependency>
      </dependencies>

	<properties>
	    <maven.compiler.source>1.8</maven.compiler.source>
	</properties>
   
</project>
```

> 2. Create a Java class MessageService.java in src/main/java/com folder with the method as shown below.
```bash
package com;

import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class MessageService {
	
	@GetMapping("/hello")
	public String sayHello() {
		return "hello";
	}
}


```

> 3. Create a Java test class TestMessageService.java in src/test/java/com as shown below.

```bash
import org.junit.jupiter.api.Assertions;
import org.junit.jupiter.api.Test;
import org.junit.jupiter.api.extension.ExtendWith;
import org.springframework.boot.test.context.SpringBootTest;
import org.springframework.test.context.junit.jupiter.SpringExtension;

import com.MessageService;

@ExtendWith(SpringExtension.class)
@SpringBootTest
public class MessageServiceTest {

	@Test
	public void testMessage() {
		MessageService ms = new MessageService();
		System.out.println("hello");
		Assertions.assertEquals(ms.sayHello(), "hello");
	}
	
}


```


> 4. Run the Unit test cases with Maven.
```bash
mvn clean test
```
