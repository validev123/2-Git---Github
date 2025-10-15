✅ Day 2 - Git Commands & Concepts
🔧 Step-by-Step Git Setup
Step 0: Install Git Bash

    Download from: https://git-scm.com/

Step 1: Check Git Version

git --version
# or
git -v

Step 2: Create Project Folder

cd ~/OneDrive/Desktop
mkdir jio
cd jio

Step 3: Initialize Git Repo

git init

Step 4: View Hidden Files

ls -la

Step 5: Explore .git Directory

cd .git
ls -lrth
cd ..

❓ Why DevOps Engineers Need Git?

As a DevOps Engineer, version control is crucial because:

    We often work with scripts, YAML files, Terraform, etc.
    Team collaboration needs code versioning and rollback options.
    Git enables CI/CD integration using tools like Jenkins, GitHub Actions, etc.

🧠 IDEs (Integrated Development Environments)

Some common IDEs used:

    Eclipse
    MyEclipse
    IntelliJ
    NetBeans
    VS Code ✅
    PyCharm
    Atom

🔁 Git Stages Overview

Untracked → Staging → Local Repo

Billing.java   -------->
Test.java     [git add .]  ------>   git commit -m "initial commit"

📌 Important Git Commands
1. Check File Status

git status

2. Create a New File

vi Test3.java

3. Configure Git Identity

git config --global --list

git config --global user.name "kkdevopsonline"
git config --global user.email "prasanthdevops123@gmail.com"

4. Add Files to Staging

git add .                # Add all files
git add *                # Add all files (excluding hidden ones)
git add Filename1 Filename2
git add *.java
git add *.py

🧾 View Commit History

git log
git log -2         # Last 2 commits
git log -n 2

🌐 Git Remote Management
Check Connected Remotes

git remote -v

Add Remote Repository

git remote add jio https://github.com/kkdevopsonline/test.git

Push Code to Remote Repo

git push jio master

✅ Note: You must generate a PAT (Personal Access Token) from GitHub for secure push.
❓ Interview Q&A
Q1: Can you remove a Git remote alias?

Ans: Yes

git remote remove jio

Q2: How to skip git add for modified files?

Ans: Use:

git commit -a -m "Updated code"

🔴 Note: This works only for tracked files, not new ones.
Q3: Where are credentials stored?

    Windows: Credential Manager
    macOS: Keychain Access

Q4: How to view files changed in a specific commit?

git show --pretty="" --name-only <commit_id>

🧠 Example:

git show --pretty="" --name-only 93bc19a84166ce6ff1ad4e230f990ca05caf0150

