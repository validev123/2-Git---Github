How many environments?
—--------------------------------

Dev branch —> development
Stg branch  —-> QA
Master branch      —-> prod
Release branch —-----> prod
Feature branch  


NOTE: By default we have master branch, we are not suppose to push code directly into the master branch.

git branch —-> List the branches, create, delete and rename the branches.

How to list branch names?

git branch

How to  create a branch?

git branch <branch name>

How to switch from one branch to another branch?

git checkout <branch name>

Explain the merging concept
=======================

Step 1: go to development branch from master, git checkout development.
  NOTE: By default all the files of master branch moved to development branch becz we created dev branch from master branch.

Step 2: Take one file and update in the dev branch and do the commit.

Step 3: come back to master and check the file is updated or not, It will not updated.

Step 4: from master —> git diff development
Step 5: from master —> git merge development
Step 6: see the file is merged or not.


What is merge conflict?

When two developers are updating same file and same line, Then we are getting merge conflict.

Step 1: update the file in master branch and commit the changes.

Step 2: update the same file in development branch and commit the changes.

Step 3: goto master , apply git merge development

Step 4: remove the unused lines and then commit the changes.


How to switch a branch, while creating it self?

Git checkout -b stage

How to push all branches from local repo to remote repo?

Git push <alis name> branch1 branch2
Git push <alias name> –all

How to create a branch in a remote repo?

Ans: Go and create in remote repo


How to get updated code from remote branch?

Git pull <alias name> branch name

How to see the remote branches?

Git branch -r


How to see all the branches(local and remote)?

Git branch -a



How to rename branch?

git branch -m old new

How to delete a branch in local repo?

Git branch -d <branchname>  —-> Current pointing branch will not be deleted.


How to delete remote repo branch from local?

Git push <alisas name>  : <branch name>
