# DevOps
DevOps Tools, Instructions.. etc

## git --version
this commands gives you the installed version of the git in your machine.

## Creating a git repository
 ```bash
  mkdir <directory name>    - To create a directory
```
```bash
cd <directory name>     - To change the directory
 ``` 
## Git Commands 
  ```bash
  git init      - converts a directory into a git repository
 ```
  ```bash
  git add fileName or git add .     - it Adds single file to staging area or add all the files to staging area
 ```
  ```bash
  git commit -m "commit message"    - It commits the changes with the message.
 ```

```bash
 git status     - gives the list of changes, which are staged but not commited.
 ```



  ## git config: This command is used to configure the user details like username and email, which will be used during commit.
  
  ```bash
   git config --global user.name = "Shubham"
   git config --global user.email - "Shubham@gmail.com"
   
   git config user.name = "Shubham"
   git config user.email = "shubham@gmail.com"
 ```
 
 
 # Branching 
 ## git branch : Checkout your current branch
 ```bash
    git branch    - List all the branches
    
    git branch <branch name>  - > Creates the new branch
    
    git branch -D <branch name>   - > Deletes the branch
    
    git checkout <branch name>  - > Switch the branch from one branch to another
    
    git merge <branch name>  - > it has to run from master, it merges the another branch to master branch.

 ```
 
 ## Connect and add Remote Repository.
 ```bash
 git remote add origin <ssh url>
 git remote add origin
 
 
 
 ```
 
 

 
