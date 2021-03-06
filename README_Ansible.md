Ansible Installation on Linux
1. Install EPEL Repo
> sudo yum install epel-release

Note : Ansible needs python to be installed.

2. Install Ansible on Linux distribution
> sudo yum install python

> sudo  yum install -y ansible

3. Install Ansible on Mac OS.

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
 
 # Installation on Amazon EC2 - Ubuntu 18.04 LTS - execute the below command in sequence.
  ```bash
    >  scp -i <pem file>  <source pem file to to copied to master node> ubuntu@<ip of the master>:/home/ubuntu/
    >  ssh -i <pem file> ubuntu@<ip of the master node>
    >  sudo hostnamectl set-hostname master
    >  bash
    >  sudo service ssh start
    >  eval `ssh-agent -s`
    >  chmod 400 devops-ec2.pem 
    >  ssh-add devops-ec2.pem 
    >  ssh ubuntu@<private ip of node>
    >  ls -al
    >  sudo vi .bashrc. 
    -  add eval `ssh-agent -s` and ssh-add devops-ec2.pem towards the last of the file] [passsord less authentication]
    >  exit
    >  ssh ubuntu@172.31.37.230
    >  sudo apt update
    >	 sudo apt-add-repository ppa:ansible/ansible 
    >  sudo apt install ansible
    >  ansible --version
    >  sudo vi /etc/ansible/hosts 
    -  add the private IP address of the slave node in the last]
    >  ansible -m ping all
  ```

# Ansible Playbooks 
 11. Go to the directory /etc/ansible/
 
 > cd /etc/ansible/
 
 12 Create a ansible playbook file using below command.
 
 > vi task.yml
 ```bash
 - name : ec2-launcher
  hosts : localhost
  connection : local
  tasks :
  - name : launch ec2
    ec2 : 
     instance_type : t2.micro
     key_name : devops-ec2
     image : ami-097834fcb3081f51a
     region : us-east-2
     group : launch-wizard-1
     count : 1
     vpc_subnet_id : subnet-9f5562e5
     wait : yes
     assign_public_ip : yes
```
 
 13 To run the ansible playbook, execute below command.
 
 > ansible-playbook task.yml
  
this will create an ec2 instance for us and install the necessary softwares like docker.
 
 14 Create another ansible playbook to install softwares.
 
 > vi install-playbook.yml
 ```bash
---
- hosts: all
  become: true
  tasks:
  - name: install maven
    apt:
      pkg: maven
      state: present
    notify:
    - run update
  - name: install tomcat
    apt:
      pkg: tomcat9
      state: present
  - name: uninstall git
    apt:
      pkg: git
      state: absent
  - name: start tomcat service
    service:
      name: tomcat9
      state: started
      enabled: true
  - name: install docker
    apt:
      pkg: docker.io
      state: present
  - name: start docker service
    service:
      name: docker
      state: started
      enabled: true
  - name: run docker image
    command: sudo docker run -it -d -p 8085:8080 shubhamkushwah123/addressbook:1.0    
  handlers: 
  - name: run update
    apt:
      update_cache: yes
```
 15 To run the ansible playbook, execute below command.
 
 > ansible-playbook install-playbook.yml
  
this will install all the requested software and deploy the docker application on the nodes.
 
