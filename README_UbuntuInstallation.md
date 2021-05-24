# Maven project archetype : 

mvn archetype:generate -DgroupId=com.edureka.app -DartifactId=maven-demo -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4 -DinteractiveMode=false


# Jenkins installation on ubuntu

   1. Sudo apt update
   2. Sudo apt install default-are
   3. Sudo apt install maven
   4. Sudo  wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
   5. sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
   6. Sudo apt update
   7. Sudo apt install Jenkins
   8. Sudo sytemctl status Jenkins
   9. Sudo systemctl start Jenkins
  10. Goto the url - http://<IP address> : 8080/ as Jenkins runs on port 8080.
  11. sudo cat /var/lib/jenkins/secrets/initialAdminPassword

# Email Notification :   Do all these steps, otherwise the error will persists.
-You must have to log into just one gmail account (the one you are using to send email).
-Then go to https://www.google.com/settings/security/lesssecureapps and Turn On this feature.
-And last go to https://accounts.google.com/DisplayUnlockCaptcha and click Continue.


# Jenkins download agent.jar
wget http://ec2-3-22-234-221.us-east-2.compute.amazonaws.com:8080/jnlpJars/slave.jar


java -jar agent.jar -jnlpUrl http://ec2-18-217-44-60.us-east-2.compute.amazonaws.com:8080/computer/Jenkins-slave1/slave-agent.jnlp -secret d89ca0328c7c3f92973aa8793cfbc022ce967bd7d4b84a8b372e49df74f055cf 

java -jar agent.jar -jnlpUrl http://ec2-18-217-44-60.us-east-2.compute.amazonaws.com:8080/computer/jenkins-slave/slave-agent.jnlp -secret b9a39162860dc87b8f5669cd8183684592518b04ba38ac7a9d35329d2f9c9be9 -workDir "/var/lib/jenkins/"



# Install Tomcat 9
1. Apt update
2. Apt install tomcat9
3. Apt install tomcat9-admin
4. Configure user in /var/lib/tomcat9/conf/tomcat-users.xml
    <role rolename="manager-script"/>
    <role rolename="manager-jmx"/>
    <role rolename="manager-gui"/>
    <role rolename="manager-status"/>
    <user username="tomcat" password="password" roles="manager-gui, manager-status, manager-jmx, manager-script"/>
5. Configure http port  from 8080 to 8888 in /var/lib/tomcat9/conf/server.xml
6. Systemctl status tomcat9
7. Systemctl start tomcat9


# ***********Setting up User************

#Changing root password :
1. Sudo su
2. Passed root
#Creating new User
3. Adduser <username>
#Add user to Sudo group
5. Usermod -aG sudo <username>
#Add Jenkins to sudo group
6. Usermod -aG sudo Jenkins
## Make Jenkins to execute scripts with no password
7. Put in sudoers.d/jenkins
jenkins ALL=(ALL) NOPASSWD:ALL


# Setting up selenium in Ubuntu

- Install Chrome : 
1. sudo curl -sS -o - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add
2. sudo echo "deb [arch=amd64]  http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list
3. sudo apt-get -y update
4. sudo apt-get -y install google-chrome-stable

- Install Chrome Driver

5. wget https://chromedriver.storage.googleapis.com/88.0.4324.96/chromedriver_linux64.zip
6. unzip chromedriver_linux64.zip


# Steps to run selenium

1. Complete the CICD pipeline for address book project and ensure it is running on server.
2. Create a new maven project for Selenium.
3. Update pom.xml with selenium library, testng library and shade plugin.
4. Push it to the GitHub repository.
5. Create a job in Jenkins.
6. And build and package your application as jar.
7. Run jar to execute the selenium script.
Note : 
1. ensure —headless argument is added while running on ubuntu
2. Ensure that Jenkins user have given admin rights.

# Selenium Pipeline Job
node{
    stage('git checkout'){
       sh 'mvn clean'
       git 'https://github.com/shubhamkushwah123/sel-repo.git' 
    }
    
    stage('build'){
        sh 'mvn clean package'
    }
    
    stage('execute selenium test cases'){
        
    sh 'sudo su -c "java -jar /var/lib/jenkins/workspace/selenium-test/target/test-my-app-0.0.1-SNAPSHOT-shaded.jar"' 
    
    }
}


# Docker Installation 
1. Sudo su
2. Apt update
3. Apt install -y docker
4. Systemctl start docker
5. Systemctl status docker
6. Systemctl stop docker
7. Docker —version

## Dockerfile :
FROM ubuntu:latest
MAINTAINER Sahiti (email@domain.com)
RUN apt-get update
RUN apt-get install -y nginx
ENTRYPOINT ["/usr/sbin/nginx","-g","daemon off;"]
EXPOSE 80

Build the image : docker build .

Run the image : docker run -itd -p 8002:80 shubhamkushwah123/nginx:1.0
*************************************************************************************
## Docker Commands

Docker version
Docker build .
Docker ps
Docker ps -a
Ps -ef | grep docker
Docker run hello-world
Docker run -d hello-world
Docker run -d hello-world sleep 15
Docker run -itd ubuntu:latest
Docker run —name my-containewr ubuntu
Hostname -I
Hostname -a / hostname -f

Exit to come out from an attached container
-i : interactive = exit to come out CTRL+P+Q
-t : terminal  - CTRL+P+Q to come out
-d: detached – stop containerid to stop container

Attaching a container terminal again to interactive after coming out of it.
1. Docker exec -it <container_id> /bin/bash

## Removing Container : 
Docker rm -f <container_id>

## To run container with -itd
Docker ru -itd ubuntu:latest

## Attaching the terminal(standard input/output to the container)
Docker attach <container_id>

## To Start and Stop a container
Docker start < container_id>
Docker stop <container_id>
Docker pause <container_id>
Docker unpause <container_id>

## Specify resources to a docker container
Docker run -it —memory=“128M” —cpus=“1.0”


## Running tomcat as docker container
1. Docker run -itd tomcat:latest
2. Docker run -p 20000:8080 —name=my-tomcat tomcat:latest
3. Docker run -itd -p 20000:8080 —name=my-tomcat1 tomcat:latest
4. Docker run -itd -P —name=my-tomcat2 tomcat:latest
