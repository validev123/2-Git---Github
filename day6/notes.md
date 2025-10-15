git best practices
==================

--> Don't commit your code in middle of work

--> commit your code, once everything is ready

--> Test your code before you commit 

--> Give proper commit messages.


   "JIRA_ID: change message"
    165: updated pom.xml

--> avoid the merge conflicts [connect with team]

--> avoid the bind merging [always raise PR]

--> closely monitor the branches, If any branch is not requires pls delete that branch with proper approvals from lead.

--> Delete the stashes if  not required.




Git clone command
—----------------
The git clone command in Git is used to create a copy of an existing Git repository. This command not only copies the repository but also sets up a connection to the remote repository so that you can pull down updates and push your changes back to the original repository if you have the appropriate permissions.

Step 1:  create a folder in Desktop
Step 2: go inside that folder
Step 3: Git clone <url>  -> Along with code, git config also will come
Step 4: crate a staging branch, go there and start work .

NOTE: default alias name origin

git remote -v








Git Merging strategy
====================


1. Fast-Forward Merge:


Description: In a fast-forward merge, Git simply moves the pointer of the target branch forward to include the commits of the source branch. This happens when the target branch hasn't diverged since the source branch was created.
Scenario:
Assume we have a repository where master branch is the main branch and a feature branch was created from master. During the development on feature branch, no new commits were made to master.
Diagram:
Before Fast-Forward Merge:
mathematica
Copy code
      A --- B --- C  (master)
           \
            D --- E  (feature)
After Fast-Forward Merge (git merge feature):
mathematica
Copy code
      A --- B --- C --- D --- E  (master, feature)
Explanation:
Here, commits D and E from feature branch are simply added to the master branch in a linear fashion, as there were no new commits on master after branching off feature.




2. Recursive Merge (Three-Way Merge): [ORT merge strategy]


Description: Recursive merge (three-way merge) is used when changes have occurred on both the source (feature) and target (master) branches since they diverged. Git analyzes the changes and creates a new merge commit to reconcile the differences.
Scenario:
Suppose both master and feature branches have diverged with new commits.
Diagram:
Before Recursive Merge:
mathematica
Copy code
      A --- B --- C  (master)
           \
            D --- E  (feature)
After Recursive Merge (git merge feature):
mathematica
Copy code
      A --- B --- C --------- M  (master)
           \               /
            D --- E ------   (feature)

Explanation:
Git creates a new merge commit M that combines the changes from both branches (master and feature). Commits D and E are merged with master, preserving the history of both branches.




3. Merge and Rebase:

Description: While not strictly a merging technique, rebasing is an alternative approach to integrating changes from one branch (feature) into another (master). Rebase moves the entire branch onto a new base (typically the latest commit of master), rewriting the commit history.
Scenario:
Suppose you have a feature branch with several commits that you want to incorporate into master without creating a merge commit.
Diagram:
Before Rebase:
css
Copy code
      A --- B --- C  (master)
           \
            X --- Y --- Z  (feature)
After Rebase (git rebase master while on feature branch):
css
Copy code
      A --- B --- C --- X' --- Y' --- Z'  (master, feature)
Explanation:
Rebase moves the commits X, Y, and Z from feature branch on top of the latest commit (C) of master. This results in a linear history where the commits from feature branch (X', Y', Z') appear sequentially after C.





Git cherry-pick
=============
It will help us to merge only particular commits.







Git pull and git fetch
=======================

By using this commands , we will get an updated code from remote repo.



Git fetch
—---------
Git fetch —> local repo —> git merge —> working area
EX: git fetch origin test
     Git merge origin/test


Git pull
—--------
Git fetch + git merge.

EX: Git pull origin test


IQ: I want to change the recent commit message how?
ANS:
    git commit --amend -m "New commit message"
    git commit --amend —> editor will open
    git push --force —> push to remote to update the name
