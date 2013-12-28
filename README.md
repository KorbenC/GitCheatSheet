# Git Cheat Sheet

*All you need to know about git*

## <a name='TOC'> Table of Contents</a>

 1. [Overview](#overview)
 1. [Basic Git Workflow Example](#basic)
 1. [Setup & Init](#setup)
 1. [Stage & Snapshot](#stage)
 1. [Branch & Merge](#branch)
 1. [Share & Update](#share)
 1. [Inspect & Compare](#inspect)
 1. [Contributing on Github](#contributing)
 1. [Deploying to Heroku with Git](#heroku)

## <a name='overview'>Overview</a>

-When you first setup Git, set up your user name and email address so your first commits record them properly.
```
git config --global user.name "My Name"
git config --global user.email "user@email.com"
```
<<<<<<< HEAD

**About Git, GitHub, and Heroku**
-Git is a free and open source, distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

-GitHub is the best way to collaborate around your code. Fork, send pull requests, and manage all your public and private repositories.

-Heroku is a cloud application platform that supports a number of different programming languages including Java, Ruby, Node.js, and Clojure. It's a new way of building and deploying web apps.

## < name='basic'>Basic Git Workflow Example</a>

-Initialize a new git repository, then stage all the files in the directory and finally commit the initial snapshot.
```
$ git init
$ git add *
$ git commit -m 'initial commit'
```
-Create a new branch named featureA, then check it out so it is the active branch. then edit and stage some files and finally commit the new snapshot.
```
$ git branch featureA
$ git checkout featureA
$ (edit files)
$ git add (files)
$ git commit -m 'add feature A'
```
-Switch back to the master branch, reverting the featureA changes you just made, then edit some files and commit your new changes directly in the master branch context.
```
$ git checkout master
$ (edit files)
$ git commit -a -m 'change files'
```
-Merge the featureA changes into the master branch context, combining all your work. Finally delete the featureA branch.
```
$ git merge featureA
$ git branch -d featureA

## < name='setup'>Setup & Init</a>

*Git configuration, and repository initialization and cloning.*
-set a config value int his repository
```
git config [key][value]
```
-set a config value globally for this user
```
git config --global [key][value]
```
-initialize an existing directory as a Git repository
```
git init
```
-clone a git repository from a URL
```
git clone [url]
```
-get help on any Git command
```
git help [command]
```

## < name='stage'>Stage & Snapshot</a>

*Working with snapshots and the Git staging area*
-Show the status of what is staged for your next commit and what is modified in your working directory
```
git status
```
-add a file as it looks now to your next commit(stage)
```
git add [file]
```
-reset the staging area for a file so that the change is not in your next commit (unstage)
```
git reset [file]
```
-diff of what is changed but not staged
```
git diff
```
-diff of what is staged but not yet committed
```
git diff --staged
```
-commit your staged content as a new commit snapshot
```
git commit
```
-remove a file from your working directory and unstage
```
git rm [file]
```
-tcl/tk GUI program to make all of these commands simpler
```
git gui
```

## < name='branch'>Branch & Merge</a>