# DevOps
DevOps Tools, Instructions.. etc

## git --version
this commands gives you the installed version of the git in your machine.

## Creating a git repository

  ### Create a Directory
 ```bash
  mkdir <directory name>
```
  
  ### Change the Directory
```bash
cd <directory name>
 ``` 
  ### Convert this directory into a empty git repository
  ```bash
  git init
 ```
  ## git add : it Adds single file to staging area or add all the files to staging area
  ```bash
  git add fileName or git add .
 ```
 
  ## git commit : it commits the changes from staging area to the local repository.
  ```bash
  git commit -m "commit message"
 ```

  # git status : command gives us the name of the branch and list of files in staging area, which are not commited.
```bash
 git status
 ```



  ## git config: This command is used to configure the user details like username and email, which will be used during commit.
  
  ```bash
   git config --global user.name = "Shubham"
   git config --global user.email - "Shubham@gmail.com"
   
   git config user.name = "Shubham"
   git config user.email = "shubham@gmail.com"
   
   
 ```
