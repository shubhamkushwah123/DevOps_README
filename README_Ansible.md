Ansible Installation on Linux
1. Install EPEL Repo
> sudo yum install epel-release

Note : Ansible needs python to be installed.

2. Install Ansible
> sudo yum install python
> sudo  yum install -y ansible

3. Install Ansible on Mac
> pip install ansible

4. Create a directory 
> mkdir /etc/ansible

5. Create a configuration file named "hosts"
> vi hosts

6. Add the following line
> [server]
> 18.222.176.34  ansible_ssh_private_key_file=/Users/shubham/Documents/aws-keys/devops-ec2.pem

Note : 18.222.176.34 is the ip address of the aws ec2 machine and devops-ec2.pem is the key file that you have downloaded 
while launching the ec2 instance.

7. Run the below command to check the connectivity.

> ansible all -m ping -u ec2-user

8. Running Ansible playbook
In order to run ansible playbook, please make sure you have installed the python boto package in your system. it offers
the packages for aws connectivity.

To Install Boto3
 > pip Install boto3
 
9 Post installation of boto, go to user home directory /Users/<UserName Directory>/ and create a file as below.
> vi .boto

10. Add the following linds and credentials provided by AWS and save.

> [Credentials]
> aws_access_key_id=Access key provided by AWS
> aws_secret_access_key=Access key secret provided by AWS

# Ansible Playbooks 
 11. Go to the directory /etc/ansible/
 
 > cd /etc/ansible/
 
 12 Create a ansible playbook file using below command.
 
 > vi task.yml
 
 13 To run the ansible playbook, execute below command.
 
 > ansible-playbook task.yml
  
this will create an ec2 instance for us and install the necessary softwares like docker.
 
