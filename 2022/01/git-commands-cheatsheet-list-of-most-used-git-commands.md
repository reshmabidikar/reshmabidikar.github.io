---
title: "Git commands CheatSheet - List of most used Git commands"
date: "2022-01-14"
categories: 
  - "git-and-github"
coverImage: "gitcheatsheet-scaled.jpg"
---

In this article, I will be listing some of the important Git commands along with their syntax and examples. This article is aimed to be a Git commands cheatsheet for developers.

## Important Git Commands

### git init

The git init command creates a local repository. It creates a hidden .git folder that represents the [local repository](https://learnjava.co.in/some-git-terminologies/#Local_Repository).

**Syntax**

`git init`

**Examples**

`git init # Initializes the current directory as a git repository`

`git init <path> # Initializes the specified directory as a git repository`

### git add

The git add command adds files to the git [staging area](https://learnjava.co.in/some-git-terminologies/#Staging_Area)

**Syntax**

`git add <filename>`

**Examples**

`git add Hello.java # adds Hello.java`

`git add . # adds everything from the current directory recursively` OR

`git add -A # same as git add .`

### git commit

The git commit command adds files to the [local repository](https://learnjava.co.in/some-git-terminologies/#Local_Repository). You can use it to add a single file as well as a bunch of files.

**Syntax**

`git commit -m "<msg>"`

**Examples**

`git commit -m "Initial commit"`

`git commit -am "Initial commit" $ Combination of git add and git commit, can only be used for tracked files`

### git push

The git push command adds files from the [local Git repository](https://learnjava.co.in/some-git-terminologies/#Local_Repository) to the [remote repository](https://learnjava.co.in/some-git-terminologies/#Remote_Repository) on your Git hosting system like Github. Before executing this command, it is necessary for the remote repository to exist on the Git hosting platform.

**Syntax**

`git push <repository name> <branch name>`

**Examples**

`git push origin main # pushes the main branch`

`git push origin b1 # pushes the branch b1`

### git clone

The git clone command obtains a copy of a [remote repository](https://learnjava.co.in/some-git-terminologies/#Remote_Repository) on the local system. This is known as cloning a repository.

**Syntax**

`git clone <url>`

**Examples**

`git clone https://github.com/reshmabidikar/learnjava-springboot-flyway-example.git`

### git pull

The git pull command fetches the latest code from the remote repository and merges it with the local code. It is a combination of the `git fetch` and `git merge` commands. You can use it to synchronize your local repository with the remote repository. It is a best practice to always do a pull before doing a push.

**Syntax**

`git pull <repository name> <branch name>`

**Examples**

`git pull origin master # fetches the latest code from the master branch of the remote repository and merges it with the local repository`

### git status

The git status command returns the status of a git repository. It provides information about the current branch, whether there are untracked files, files to commit, and so on.

**Syntax**

`git status`

**Examples**

`git status`

This returns information like:

```
$ git status
On branch main
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   Hello.txt

no changes added to commit (use "git add" and/or "git commit -a")

```

### git branch

The git branch command executes branch-related actions like creating a new branch, renaming a branch, deleting a branch, and listing all branches.

**Syntax**

`git branch <options > <branch name>`

**Examples**

`git branch b1 # Creates branch b1`

`git branch -a # Lists available branches with an * around the active branch`

`git branch -m oldbranch newbranch # Renames oldbranch to newbranch`

`git branch -d branch1 # Deletes branch1`

### git merge

The git merge command can be used to merge a branch into the currently checked-out branch.

**Syntax**

`git merge <branch name>`

**Examples**

`git checkout master # switches to the master branch`

`git merge b1 # Merges b1 into master`

`git merge b1 --no-ff # Merges b1 into master by disabling fast forward merge`

### git reset

Removes a file from the [staging area](https://learnjava.co.in/some-git-terminologies/#Staging_Area).

**Syntax**

`git reset HEAD <filename>`

**Examples**

`git reset HEAD file.txt # Removes file from staging area`

### git checkout

Can be used to switch branches or restore files.

**Syntax**

`git checkout <filename>`

**Examples**

`git checkout Hello.txt # Reverts Hello.txt to the last version in Git, note that if the file is added to index, it should be first removed via the git reset command shown above`

`git checkout branch1 # used to switch to branch branch1`

`git checkout -b branch1 #creates branch branch1 and swtiches to it`


## Further Learning

- [Git and Github Masterclass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fgit-and-github-masterclass%2F)
- [Git and Github for Beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fgit-and-github-crash-course%2F)

## Conclusion

So, this article provides a Git commands cheatsheet. It explains the important Git commands and their syntax along with examples. Some of the commands covered include git init, git add, git push, git pull and so forth.
