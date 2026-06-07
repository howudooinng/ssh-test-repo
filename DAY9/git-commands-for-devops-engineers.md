Day - 11
  Git Commands useful for DevOps engineers.
 How to create or initialize a git repo - git init, ls -a, ls -ltra, .git is a key component for the git, as it provides the tools to track the changes made and also keep the passwords etc protected and protects them to get committed to the github

.git/hooks/pre-commit  To track the files - we need to use git add < file name >, due to tis git nows understands that it has to track this file now.  Git helps in versioning and tracking of the changes.  git add . —> adds all the untracked files to tracked state 

git commit -m “message” —> commits the changes, and using this we can go back to any change done is not required. git log —> shows the changes done i.e the commits done  git push —> end goal is to push the code from local to the distributed system, so that everyone can use that code  git workflow —> git add && git commit -m “” && git push  how to create a new repo from local to remote:  git remote add <github url/(repo name)>  so I decided to push my local change to an already existing git repo but I was facing issues while doing it, and it got resolved by using   git pull origin master --rebase && git push -u origin master  these 2 commands which asked me to give my github username and the PAT which I had to generate from the classic token generation option 

and it got rebased and the changes are reflecting fine 

I tried to use git push from local to remote(existing repo) and it gave error due to below:  Root cause
* Your remote repo already had a commit (usually README)
* Your local repo had different commits
* Git blocked push to prevent overwriting remote history. 
So I applied these commands which as as below :  git pull origin master --rebase
git push -u origin master  What it did
* Pulled remote changes
* Rebased your work on top
* Then pushed successfully
 Investigate more About rebase vs merge concepts for git repos.  How to create a Repo from cli? What is a git lifecycle? What is git clone ?
 git clone is used to pull the code from remote to local.
https and ssh
 Clone vs Fork —> git is a distributed version control system, so multiple replicas can be on different machines. so forking is a way you can collaborate on a repository by creating a copy of it, clone is used to download a specific repo 

main —> new branch   most of the times, people tend to work on different things, ex - calculator application is delivered, now their is new requirement, which needs to be added the calculator application which is very huge, for a new feature, create a new branch, so that we don’t touch the main branch in order to keep the existing application stable and running without any issues 


create a branch - git checkout -b <branch name>


 

























 
