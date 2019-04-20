These are my notes abut GIT

Terminal(or Bash)

$ git --version
Shows you which version of GIT is installed

$ git config --global user.name <Your Name>
This sets your name

$ git config --global user.username <UserName>
This sets your github username

$ git config --global user.email <youremail@example.com>
This sets your email




CREATING A REPOSITORY--------------
$ mkdir hello-world
mkdir means 'make directory'

$ cd somePath
cd is change directory

$ git init
This tells git to start tracking the folder I'm in

$ git status
The status of the repository

$ ls
Lists the items in the folder




COMMITING-----------------------
$ git status
The status of the repository (shows if files have been added or changed)

$ git add nameOfFile.txt
This adds the specific files changes to the commit you are going to make

$ git add .
This adds ALL file changes to the commit you are going to make

$ git commit -m "Commit message"
Commit those changes to the repository's history with a description message(m)




REMOTES------------------------
$ git remote add origin <URLFROMGITHUB>
You can have multiple remotes so each requires a name. The primary remote is typically named origin.
Your local repository now knows where your remote repository, named 'origin', lives on GitHub's servers. Think of it as adding a name and address on speed dial—now when you need to send something there, you can.

$ git remote add <REMOTENAME> <URL>
Add remote connections

$ git remote set-url <REMOTENAME> <URL>
Set a URL to a remote

$ git remote -v
View remote addresses




PUSH  & PULL FROM REMOTE----------------------------
$ git push origin master
you tell Git the branch name you want (master) and the name of the remote that it lives on (origin).
In this case, we'll send our branch named 'master' to our remote on GitHub named 'origin'.

$ git push <REMOTENAME> <BRANCH>
Push changes to your branch on git (REMOTENAME)

$ git pull <REMOTENAME> <BRANCHNAME>
Pull in changes from remote branch into the current checkedout folder

You will possibly push multiple commits (if you have made multiple commits)

$ git fetch --dry-run
See changes to the remote before you pull in






FORKS & CLONES------------------
$ cd someFolderProbablyCCode
cd is change directory. Now, in terminal, you'll clone the repository onto your computer. It will automatically create a new folder for the repository so there is no need to create one yourself. But make sure you aren't cloning it inside of another Git repository folder!

$ git clone <URLFROMGITHUB>
To clone your fork

$ cd NameOfFolderCreated
Now you've got a copy of the repository on your computer and it is automatically connected to the remote repository (your forked copy)

$ git remote -v
View remote addresses

$ git remote add upstream <URLFROMGITHUB>
What if the original repository you forked happens to change? You'll want to be able to pull in those changes too. So let's add another remote connection, this time to the original, github.com/jlord/patchwork, repository with its URL.

You can name this remote connection anything you want, but typically people use the name 'upstream'; let's use that for this.

$ git remote set-url <REMOTENAME> <URL>
This can change a remote url




BRANCHES-------------------------
$ git checkout -b <BRANCHNAME>
This creates, and switches to, a new branch
Git repositories use branches to isolate work when needed. It's common practice when working on a project or with others on a project to create a branch to keep your working changes in. This way you can do your work while the main, commonly named 'master', branch stays stable. When the work on your branch is finished you merge it back into the 'master' master branch.

The diagram below shows how you can branch off of your 'master' branch, do work and then merge those changes back into 'master'. You can even branch off of a branch if you need to, the 'master' branch doesn't have to be the base.

$ git branch <BRANCHNAME>
This just creates a new branch

$ git checkout <BRANCHNAME>
This moves onto the named branch

$ git branch
This lists all the branches

$ git branch -m <NEWBRANCHNAME>
This renames the branch you are currently on

$ git status
This verifies which branch you are on





PULLS-----------------------
$ git pull <REMOTENAME> <BRANCHNAME>
Pull in changes from a remote branch

$ git fetch --dry-run
See changes to the remote before you pull in




PULL REQUESTS-------------------------
Often when you make changes and improvements to a project you've forked, you'll want to send those changes to the maintainer of the original and request that they pull those changes into the original so that everyone can benefit from the updates—that's a pull request.





CLEANING UP---------------------------------
$ git checkout <BRANCHNAMEone>
First, move into the branch you want to merge into

$ git merge <BRANCHNAMEtwo>
merge a branch into the current branch

$ git branch -d <BRANCHNAMEtoDELETE>
Delete a local branch

$ git push <REMOTENAME> --delete <BRANCHNAMEtoDELETE>
Delete a remote branch

Once you don't need branches anymore you can delete them locally and remotely. This is helpful so that you don't end up with a pile of old branches.
