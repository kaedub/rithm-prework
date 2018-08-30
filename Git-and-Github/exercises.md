# <span style="color:blue">Git and Github</style>
---
##Git Basics

__1. Create a folder called `learn_git_again`.__  
`mkdir learn_git_again`  
__2. cd into the learn_git_again folder.__  
`cd learn_git_again`  
__3. Create a file called third.txt.__  
`touch third.txt`  
__4. Initialize an empty git repository.__  
`git init`  
__5. Add third.txt to the staging area.__  
`git add third.txt`  
__6. Commit with the message "adding third.txt".__  
`git commit -m "adding third.txt"`  
__7. Check out your commit with git log.__  
`git log`  
__8. Create another file called fourth.txt.__  
`touch fourth.txt`  
__9. Add fourth.txt to the staging area.__  
`git add fourth.txt`  
__10. Commit with the message "adding fourth.txt".__  
`git commit -m "adding fourth.txt`  
__11. Remove the third.txt file.__  
`rm third.txt`  
__12. Add this change to the staging area.__  
`git add -A`  
__13. Commit with the message "removing third.txt".__  
`git commit -m "removing third.txt"`  
__14. Check out your commits using git log.__  
`git log`  
__15. Change your global setting to core.pager=cat.__  
`git config --global core.pager cat`
__16. Write the command to list all of the global configurations for git on your machine. You can type git config --global to find out how to do this__  
`git config --global -l`

##Branching and Merging

####<span style="color:#6b6b6b">Part I</span>
__1. What does git clean do?__  
> `git clean` removes untracked or unmerged files from the working directory.  

__2. What do the -d and -f flags for git clean do?__  
> The `-d` flag removes directories, the `-f` flag forces the `git clean` to run. 
 
__3. What git command creates a branch?__  
> `git checkout -b <branch_name>`  

__4. What is the difference between a fast-forward and recursive merge?__  
> A *fast-forward* merge is when commits happen chronologically.  
> A *recursive* merge is when commits happen at different times on two branches.

__5. What git command changes to another branch?__  
> `git checkout <branch_name>`  

__6. How do you remove modified or deleted files from the working directory?__  
> `git checkout <filename>`  

__7. What git command deletes a branch?__  
> `git branch -D <branch_name>`  

__8. What does the git diff command do?)__  
> `git diff` shows changes between commits, or commits and working directory, etc.  

__9. How do you remove files from the staging area?__  
> `git rm --cached`  

__10. How do merge conflicts happen?__  
> When changes are made to the same file on different branches.

####<span style="color:#6b6b6b">Part II</span>
__Create your own merge conflict!__  
`git checkout -b new_branch` 
`echo Hola > greeting.txt`  
`git add .`  
`git commit -m "adding greeting.txt in spanish"`  
`git checkout master`  
`echo Hello > greeting.txt`  
`git add .`  
`git commit -m "adding greeting.txt in english"`  
`git merge new_branch` <span style="color:#6b6b6b">*#Causes merge conflict*</span>  
`nano greeting.txt` <span style="color:#6b6b6b">*#Removed all lines except "Hola"*</span>  
`git add .`  
`git commit -m "fixed merge conflict"`  

##Github Fundamentals

###<span style="color:#6b66b">Part I</span>
__1. Create a local repository and add and commit some files__  
`git init`  
`touch file.txt`  
`git add . && git commit -m "first commit"`  

__2. Create a remote repository and push your code from the local repo to the remote__  
> Created new repository named "shiny-garbanzo"  
`echo "# shiny-garbanzo" >> README.md`  
`touch file.txt`  
`git init`  
`git add .`  
`git commit -m "first commit"`  
`git remote add origin git@github.com:libellis/shiny-garbanzo.git`  
`git push -u origin master`  

__3. Fork the repo https://github.com/rithmschool/git_practice - clone it and submit a pull request__  
`git clone git@github.com:libellis/git_practice.git`  

__4. Create a new branch locally and push it to GitHub__  
`git checkout -b kevins_branch`  
`git push -u origin kevins_branch`  

__5. Submit a pull request with your new branch against the master branch on the git_practice repo.__  
> This should reflect on Github.
