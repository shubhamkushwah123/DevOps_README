# CICD 
## Steps for End to End Pipeline Automation

> Pre-requisite : 
1. JDK1.8 or +
2. Eclipse Neon or +
3. Maven 3.3 or +
4. Jenkins latest

### 1. Create an Spring Boot Application
> Follow the instructions at below link to create an Spring Boot Application.

https://github.com/shubhamkushwah123/DevOps_README/blob/master/README_SpringBoot.md


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


### 4. Creating Jenkins Pipeline.


> 1. To Launch the Jenkins, Go to the folder, where jenkins.war is placed and run below command.
```bash
java -jar jenkins.war
```

> 2. Go the browser and open http://localhost:8080

> 3. Login with the admin user and password that you have created during first login after installation process.

Note : if not, please follow steps at > https://www.guru99.com/download-install-jenkins.html

> 4. Click on New Item > Choose Pipeline Project > Give any name (e.g. ci-pipeline) > hit Enter.

> 5. Click on configure > Click on the last tab Pipeline.
Note : Pipeline scripts needs to be written in groovy script. a template is shown below.

```bash
node{
	stage('git checkout'){
		// code for checkout
	}
	
	stage('mvn build'){
		// code for build
	}
	
	stage('mvn test'){
		// code for test
	}
	
	stage('mvn install'){
		// code for install
	}
}
```

> 6. Once the pipeline code is done, Please click on save and Build Now.

> 7. If it is a blue button, it means success, if it's a red button means fail. Click on the button to see the logs to identify errors.

