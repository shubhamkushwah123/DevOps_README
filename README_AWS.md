# Commands for getting Amazon EC2 Instance Ready

1) SSH to your amazon ec2 instance
  > Go to the folder, where you have saved your key value pair and run below command

 ```bash
  ssh -i <key-pair.pem> ec2-user@<public/private ip address>
  ssh -i devops-ec2.pem ec2-user@10.20.233.343
```
