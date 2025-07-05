---
title: "Introduction to Docker to get you started"
date: "2022-11-12"
categories: 
  - "docker"
coverImage: "Docker-scaled.jpg"
---

On a recent project, I got an opportunity to work with Docker. In this article, I will be giving an introduction to Docker and explaining some basic Docker concepts.

## What is Docker?

Docker is a container service that helps developers quickly package and run an application in any environment. It addresses the one problem that every developer has faced at least once in her life, "It works on my machine!"

For example, suppose there are multiple developers working in different environments like Linux/Windows and MacOS. Docker makes it easy to move the complete application setup from one environment to the other. Suppose the application being worked on is a Java application that requires different pieces of software like a web container like Tomcat, a database like MySQL, and so on. Without Docker, you would need to individually install each software in order to set up the development environment on a different machine. Not only that, but when you move from development to test/production, you would need to follow the setup procedure all over again. However, Docker makes it possible to move the complete setup to a different environment in minutes saving a lot of time and headache.

## How Does Docker Work?

Docker works on the concepts of "images". A Docker image is a template that contains a set of instructions that can be used to start/run a container. A container is a virtual environment that bundles all the software specified in the image. Thus, in OOP terminology, an image can be considered to be the equivalent of a class and a container can be considered to be the equivalent of an object of a class.

Thus, in order to Dockerize an application, you need to build a Docker image. This image can then be used to start a container that has all the necessary software running. Thus, other application developers get started with the application in a few minutes simply by using the same Docker image!

## Docker Terminology

There are a few terms that you will hear often when you start using Docker. I will try to cover some of them in this section.

### Docker Hub

DockerHub is a repository for Docker images. So, developers can push their Docker images to make them available to others. Developers can also "pull" other Docker images and use them as required.

### Docker Desktop

Docker Desktop is a front-end application for Docker. Thus, it provides a user interface to manage images/containers. It is available on all platforms, namely Windows, Linux, and MacOS.

### Dockerfile

A Dockerfile is a simple text file that you can use to build a Docker image. Within the Dockerfile, you need to specify instructions for building the image.

## Further Reading

- [Docker for the absolute Beginner](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Flearn-docker%2F)
- [Docker and Kubernates](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fdocker-kubernetes-the-practical-guide%2F)

## Conclusion

So, this article provides an introduction to Docker. It covers important concepts like what Docker is, how you can use it and some important Docker terms like Docker Desktop, Dockerfile, etc.
