# Docker Instructions 

## Installation on Mac
To Install Docker on Mac, follow the instructions at below link.

https://docs.docker.com/docker-for-mac/install/

## Installation on Windows
To install Docker on Windows, follow the intructions at below link.

https://docs.docker.com/docker-for-windows/install/

## Installation on Linux Distribution
To install Docker on Linux, follow the instructions at below link.

Centos : https://docs.docker.com/engine/install/centos/

Ubantu : https://docs.docker.com/engine/install/ubuntu/

Debian : https://docs.docker.com/engine/install/debian/

Fedora : https://docs.docker.com/engine/install/fedora/


## Docker Hub
To access Docker Hub, Please visit below url

https://hub.docker.com/

## Docker Commands

 ```bash
  
 ```
> To check Docker Version :
 ```bash
  docker --version
 ```
> To Start the Docker on Linux : 
```bash
  docker service docker start
 ```
> To Stop the Docker on Linux : 
```bash
  docker service docker stop
 ```
> To check the running containers :
```bash
  docker ps
 ```
> To check all the containers (running and terminated)
```bash
  docker ps -a
 ```
> To check docker images : 
```bash
  docker image
 ```
> To remove an docker image :
```bash
  docker rmi $image_id
 ```
> To build a docker image from Dockerfile : 
```bash
  docker build 
  docker build -t $imageName:tagName
  docker build -t my-test-app:1.0.0
 ```
 > To Login to Docker Hub Repository : 
  ```bash
  docker login
 ```
 
 > To Push an image to DockerHub Repository
  ```bash
  docker push $dockerHubId/$imageId:$tagName
  docker push shubhamkushwah123/my-test-app:1.0.0
 ```
 
 > To Pull an image from DockerHub Repository
  ```bash
  docker pull $dockerHubId/$imageId:$tagName
  docker pull shubhamkushwah123/my-test-app:1.0.0
 ```
 
 > To Run an Docker image 
  ```bash
  docker run -p $entryPort:$PortToBeMapped -d $dockerId/$imageId:$tagName
  docker run -p 8888:8080 -d shubhamkushwah123/my-test-app:1.0.0
 ```
