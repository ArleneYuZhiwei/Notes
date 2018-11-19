### How to use git

**Official tutorial**

http://rogerdudler.github.io/git-guide/

**Workflow**

Working Directory-(add)->Index-(commit)->Head

###Initialization###

Create a new directory and copy its address #D#

**git init**

Tell the git where your barn is :

**git remote add origin #D#**

Initialize your information

**git config  --global user.name "your name"**

**git config  --global user.email "your email address"**

### Checkout a repository

Create a working copy of a local repository

**git clone /path/to/repository**

Or when using a remote server

**git clone username@host:/path/to/repositor**

### Add & Commit

**git add filename**

**git commit -m "A description of this commit"**

The file is committed to the **HEAD**, but not in your remote repository yet.

### Pushing Change
Send those changes to your remote repository and branch DB

**git push origin DB**

Now your changes have been pushed to the website and go to github.com:

**repository->branches->merge request**

you can deal with the requests now

before a check, all the commits on this branch will require an update

### Branching

Switch back to branch_a

**git checkout branch_a**

Create a new branch named "branch_x" and switch to it

**git checkout -b branch_x**

Delete the branch_x

**git branch -d branch_x**

Push the branch to your remote repository

**git push origin branch**

### Update & Merge

Update your local repository to the newest commit

**git pull**

have a check before mergin

**git diff source_branch target_branch**

to handle the conflicts

**git add filename**

### Replace local changes


Replace local changes with the last content in **HEAD**

**git checkout --filename**

OR Replace local changes with the last content in the server

**git fetch origin**

**git reset --hard origin/master**


### Tagging


**git tag name #the first 10 characters of the commit id#**


### Tips


Check the status

**git status**

Unify the format

**yapf -i name.py**

Give up the changes

**git reset**

See the log

**git log**

Pull the code from branch_a

It would be better to save the commits which have not been pushed before pull

**git stash**

a.**git checkout branch_a**

b.**git pull**

c.**git checkout branch_name**

d.**git rebase branch_a**

e.**git stash apply**

About git rebase

https://www.git-tower.com/learn/git/ebook/cn/command-line/advanced-topics/rebase

Changes not staged for commit:

git add (commit those changes) OR git checkout (give up the changes)

untracked files:

commit those files OR delete those files
