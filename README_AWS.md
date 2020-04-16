# Commands for getting Amazon EC2 Instance Ready

1) SSH to your amazon ec2 instance from mac and Linux
  > Open your terminal and go to the folder, where you have saved your key value pair and run below command

 ```bash
  ssh -i <key-pair.pem> ec2-user@<public/private ip address>
  ssh -i devops-ec2.pem ec2-user@10.20.233.343
```
2) Connecting your amazon ec2 instance from windows using putty
  > Follow the instructions at below link.
  
  https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/putty.html
  
  
3) Run the below commands in sequence after connecting to amazon ec2 instance command line.
 ```bash
 sudo yum update
 
 sudo yum install docker
 
 sudo docker --version
 
 sudo service docker status
 
 sudo service docker start
 
 sudo service docker status
 
 sudo docker run -p 80:8888 shubhamkushwah123/my-test-app:1.0.0
```

