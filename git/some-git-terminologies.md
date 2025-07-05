---
title: "Some Git Terminologies Explained in Brief"
date: "2021-12-26"
categories: 
  - "git-and-github"
coverImage: "3H21KUXVT4.jpg"
---

In this article, I will try to explain some of the important terminologies associated with Git.

## Some Git Terms

### Working Directory

Working directory refers to a project folder on the file system. It may or may not be tracked by Git.

### Staging Area

A staging area represents the files that are ready to be added to a repository. Typically, projects include dynamically generated files like class files, test reports, etc. These are not added to a repository, only the source code/configuration files are added to a repository. Thus, whenever you want to add some code to a repository, it first needs to be added to the staging area, from where it can be committed to the repository. The process of adding code to the staging area is known as **indexing**.

### Local Repository

As explained in my [Git v/s Github](git-and-github-differences-explained-in-short.md) article, Git maintains a local repository where it keeps track of all the changes made to the project on the local system.

### Remote Repository

The repository on your repository hosting system like GitHub is known as the remote repository. Creating a remote repository not only enables developers to work on their projects from anywhere, but also allows collaborating with different developers.

### Branch

A branch represents a line of development. Often, developers use different branches for production releases, bug fixes, etc. Having code in different branches enables developers to make changes to code without messing up the main line of development.

### Fork

Forking is the process of copying someone else's repository into your own account. So, when you fork a repository, a copy of the entire repository is available in your own account. Forking is typically used when developers want to make changes to someone else's repository for their own purpose. Forking does not in any way affect the original repository. Developers can however submit their changes to the project owner by creating a pull request.

### Commit

The process of adding code to your local Git repository is called committing. Git has a `git commit` command that performs a commit.

### Push

The process of adding code to a remote repository is called pushing. Git has a `git push` command that performs a push.

### Pull

The process of retrieving code from a remote repository is called pulling. Git has a `git pull` command that performs a pull. This command fetches the latest code from the remote repository and merges it with the local code.

### Pull Request

A pull request is a way for developers to request a project owner to review the changes that they want to merge into the project. So once a developer makes the necessary code changes (either in a branch of the project or within a fork), they can submit a pull request. The project owner can then review and merge the submitted changes.

## Further Reading

- [Git and Github Masterclass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fgit-and-github-masterclass%2F)
- [Git and Github for Beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fgit-and-github-crash-course%2F)

## Conclusion

So, in this article, we took a look at some of the important terminologies associated with git like commit, push, fork, and so forth.
