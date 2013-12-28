# Git Cheat Sheet

*All you need to know about Git*

## <a name='TOC'> Table of Contents</a>

 1. [Overview](#overview)
 1. [Basic Git Workflow Example](#basic)
 1. [Setup & Init](#setup)
 1. [Stage & Snapshot](#stage)
 1. [Branch & Merge](#branch)
 1. [Share & Update](#share)
 1. [Inspect & Compare](#inspect)
 1. [Contributing on GitHub](#github)
 1. [Deploying to Heroku with Git](#heroku)
 1. [License](#license)

## <a name='overview'>Overview</a>

- When you first setup Git, set up your user name and email address so your first commits record them properly.

```
git config --global user.name "My Name"
git config --global user.email "user@email.com"
```

##**About Git, GitHub, and Heroku**
 - Git is a free and open source, distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

 - GitHub is the best way to collaborate around your code. Fork, send pull requests, and manage all your public and private repositories.

 - Heroku is a cloud application platform that supports a number of different programming languages including Java, Ruby, Node.js, and Clojure. It's a new way of building and deploying web apps.

## <a name='basic'>Basic Git Workflow Example</a>

 - Initialize a new git repository, then stage all the files in the directory and finally commit the initial snapshot.

```bash
$ git init
$ git add *
$ git commit -m 'initial commit'
```
 - Create a new branch named featureA, then check it out so it is the active branch. then edit and stage some files and finally commit the new snapshot.

```bash
$ git branch featureA
$ git checkout featureA
$ (edit files)
$ git add (files)
$ git commit -m 'add feature A'
```
 - Switch back to the master branch, reverting the featureA changes you just made, then edit some files and commit your new changes directly in the master branch context.

```bash
$ git checkout master
$ (edit files)
$ git commit -a -m 'change files'
```
 - Merge the featureA changes into the master branch context, combining all your work. Finally delete the featureA branch.

```bash
$ git merge featureA
$ git branch -d featureA
```

**[[⬆]](#TOC)**

## <a name='setup'>Setup & Init</a>

**Git configuration, and repository initialization and cloning.**
 - set a config value int his repository

```bash
git config [key][value]
```
 - set a config value globally for this user

```bash
git config --global [key][value]
```
 - initialize an existing directory as a Git repository

```bash
git init
```
 - clone a git repository from a URL

```bash
git clone [url]
```
 - get help on any Git command

```bash
git help [command]
```
**[[⬆]](#TOC)**

## <a name='stage'>Stage & Snapshot</a>

**Working with snapshots and the Git staging area**
 - Show the status of what is staged for your next commit and what is modified in your working directory

```bash
git status
```
 - add a file as it looks now to your next commit(stage)

```bash
git add [file]
```
 - reset the staging area for a file so that the change is not in your next commit (unstage)

```bash
git reset [file]
```
 - diff of what is changed but not staged

```bash
git diff
```
 - diff of what is staged but not yet committed

```bash
git diff --staged
```
 - commit your staged content as a new commit snapshot

```bash
git commit
```
 - remove a file from your working directory and unstage

```bash
git rm [file]
```
 - tcl/tk GUI program to make all of these commands simpler

```bash
git gui
```
**[[⬆]](#TOC)**

## <a name='branch'>Branch & Merge</a>

**Working with Git branches and the stash**
- List your branches. a * will appear next to the currently active branch

```bash
git branch
```
 - Create a new branch at the current directory

```bash
git branch [branch-name]
```
 - Switch to another branch and check it out into your working directory

```bash
git checkout [branch]
```
 - Create a branch and immediately switch to it

```bash
git checkout -b [branch]
```
 - Merge another branch into your currently active one and record the merge as a commit

```bash
git merge [branch]
```
 - Show commit logs

```bash
git log
```
 - Stash away the currently uncommitted modifications in your working directory temporarily

```bash
git stash
```
 - re-apply the last stashed changes

```bash
git stash apply
```
**[[⬆]](#TOC)**

## <a name='share'>Share & Update</a>

**Fetching, merging, and working with updates from another repository.**
 - add a git URL as an alias

```bash
git remote add [alias] [url]
```
 - Fetch down all the branches from that Git remote

```bash
git fetch [alias]
```
 - Merge a branch on the server into your currently active branch to bring it up to date

```bash
git merge [alias]/[branch]
```
 - Push the work on your branch to update that branch on the remote git repository

```bash
git push [alias] [branch]
```
 - Fetch from the URL tracked by the current branch and immediately try to merge in the tracked branch

```bash
git pull
```
**[[⬆]](#TOC)**

## <a name='inspect'>Inspect & Compare</a>

**Examing logs, diffs, and object information**
 - Show the commit history for the currently active branch

```bash
git log
```
 - Show the commits on branchA that are not on branchB

```bash
git log branchB..branchA
```
 - Show the commits that changed file, even across renames

```bash
git log --follow [file]
```
 - Show the diff of what is in branchA that is not in branchB

```bash
git diff branchB...branchA
```
 - Show any object in Git in human-readable format

```bash
git show [SHA]
```
 - tcl/tk program to show the commit log in a GUI

```bash
gitx
```
**[[⬆]](#TOC)**

## <a name='github'>Contributing on GitHub</a>

**To contibute to a project hosted on GitHub you can fork the project on github.com, then clone your fork locally, make a change, push back to GitHub, and then send a pull request, which will email the maintainer.**
 - Fork project on github

```bash
$ git clone https://github.com/my-user/project
$ cd project
$ (edit files)
$ git add (files)
$ git commit -m 'Explain what I changed'
$ git push origin master
```
 - Go to github and click 'pull request' button

**[[⬆]](#TOC)**

## <a name='heroku'>Deploying to Heroku with Git</a>
 - Use the heroku command-line tool to create an application and git remote:

```bash
$ heroku create

[Creating glowing-dusk-965... done, stack is bamboo-mri-1.9.2
http://glowing-dusk-965.heroku.com/ <http://glowing-dusk-965.
heroku.com/> | git@heroku.com:glowing-dusk-965.git <x-msg://563/
git&heroku.com:glowing-dusk-965.git> Git remote heroku added]
```
 - Use git to deploy the application

```bash
$ git push heroku master
```
 - Create an additional Heroku app for staging, and name the git remote "staging".

```bash
$ heroku create my-staging-app --remote staging
```
 - Use git to deploy the application via the staging remote.

```bash
$ git push staging master
```
**[[⬆]](#TOC)**

## <a name='license'>License</a>

(The MIT License)

Copyright (c) 2014

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

**[[⬆]](#TOC)**
