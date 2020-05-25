# Pivotal Cloud Foundary (PCF) Installation

> Get Started : 
https://pivotal.io/platform/pcf-tutorials/getting-started-with-pivotal-cloud-foundry/introduction

> Install CF CLI : 
https://docs.cloudfoundry.org/cf-cli/install-go-cli.html

> Check Installation : 
cf --version

> Register and Create an account with Pivotal : 
https://run.pivotal.io/

> Configure CLI : 
cf login
  API End : https://api.run.pivotal.io
  email : xxx@gmail.com
  password : ********
  org : devops-project
  space : development
  

## Commands CF CLI : 
> cf apps  : To list all the  applications

> cf push <app_name> -p <jar/war name> : To push the application to Cloud Foundary Server.

> example : cf push my-test-app -p my-test-app-1.0.0-SNAPSHOT.jar
  
  
> cf delete -r <app_name> : To delete the app from Cloud Foundary Server

> cf push my-test-app-2.0.0 --docker-image shubhamkushwah123/my-test-app:2.0.0 : To Push a Docker image to CF Server



