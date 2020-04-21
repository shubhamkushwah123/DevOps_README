# CICD 
## Steps for End to End Pipeline Automation

> Pre-requisite : 
1. JDK1.8 or +
2. Eclipse Neon or +
3. Maven 3.3 or +
4. Jenkins latest

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
