# Git Installation
To install git follow the instructions mentioned in the below url for Windows, Linux and Mac OS.
 ```bash
 https://www.atlassian.com/git/tutorials/install-git
```
Once the installation is done please follow the basic configuration as mentioned below.
```bash
1) check git version > git --version
2) configure username > git config --global user.name = "your name"
3) configure email > git config --global user.email = "your email"
```
You are ready to go !!!

# Git Commands and Descriptions

## git --version
this commands gives you the installed version of the git in your machine.

## Creating a git repository
> To create a directory
 ```bash
  mkdir <directory name>
  
```
> To Change the directory
```bash
cd <directory name>

 ``` 
## Git Commands 
> Converts a directory into a local git repository.
  ```bash
  git init      - converts a directory into a git repository
 ```
 
 > To add a single or muiltiple files to staging area
  ```bash
  git add fileName or git add .  
  
 ```
 
 > To commit the changes in the local repository.
  ```bash
  git commit -m "commit message" 
 ```

> To list the status of the files in staging area.
```bash
 git status  
 ```


> To configure the global username and email id

  ```bash
   git config --global user.name = "Shubham"
   git config --global user.email - "Shubham@gmail.com"
   
   git config user.name = "Shubham"
   git config user.email = "shubham@gmail.com"
 ```
 
### Connect and add Remote Repository.
 > To connect a local repository to a specific remote repository.
 ```bash
 git remote add origin <ssh url>
 git remote add origin https://github.com/shubhamkushwah123/DevOps.git
```
 
> To Clone a remote git repository into a local git repository.
```bash
 git clone <repo name> 
 git clone https://github.com/shubhamkushwah123/DevOps.git
```

> To Pull the changes from master branch of the remote git repository.
```bash
git pull origin master 
```
 
> To Push the changes to master branch of the remote git repository.
```bash
git push origin master 
```
  
### Branching 

> To List all the branches
```bash
git branch
```

> To create a new branch
```bash
git branch $branchName
```

> To delete an existing branch 
```bash
git branch -d $branchName
```

> To merge a child branch to master
```bash
git merge $branchName
```
  
### Advance git commands
> To save the changes, when they are not in state of commit.
```bash
git stash
```

> To stash changes and clearing up the directory
```bash
git stash -u
```

> To List the stashes created.
```bash
git stash list
```

> To get the stashed work back.
```bash
git stash apply
```

> To get the context and history of logs of a repository
```bash
git log
```
 
 > To Copy and Store a set of commit outside of our repository.
 ```bash
git rebase
```

> To revert back to the previous version of the file.
```bash
git revert
```

 
 

 
