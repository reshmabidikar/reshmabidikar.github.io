---
title: "Java 9 Modules Introduction Explained in Brief"
date: "2020-01-03"
categories: 
  - "java-9"
tags: 
  - "java-9"
  - "java-9-modules"
---

Java 9 Modules are one of the new features added by Java 9. This is a 3 part article, in which I will be covering modules in detail. In part 1 of this article, I will be introducing you to modules.

See also [Modules Internals](https://learnjava.co.in/java-9-module-internals/) and [Creating a Module](https://learnjava.co.in/creating-a-java-9-module/).

## What are modules

Modules are basically **groups of packages**. Just like you put a set of related classes into a package, you can put a set of related packages into a module. This helps to organize code better and to follow the Single Responsibility Principle (SRP). So all the packages in a single module help to achieve a single functionality.

## Why they were added

Prior to Java 9, there was no concept of modules. So the core jar files related to JDK like rt.jar was very big in size and it was not possible to use them on smaller devices. Also, with JDK 9 and before, developers could access internal JDK files so security was an issue. Java 9 modules help to overcome both these issues. With modules, the JDK is now organised so that the internal JDK packages are no longer exposed to the outside world.

## Changes to JDK

Java 9 has made some fundamental changes which takes advantage of modules. Prior to Java 9, after installing the JDK a folder called **jre\\lib** was created with all the core jar files. When you installs Java 9, you will see a folder called **jmods**. This has all the Java 9 modules. So instead of having a big far rt.jar, JDK 9 has separate modules.

## Benefits of Modules

Modules offer several benefits.

### Smaller size applications

Unlike packages, a module can be deployed by itself. So if there is a large application, you can break it down into modules. Each module can be built into a separate jar file and deployed as required instead of deploying a big fat jar file for the whole application. So your Jar files become smaller. This allows using Java on smaller devices

### Better security

Prior to Java 9, all the public classes in a package were exposed to the outside world. With Java 9 modules, you can now control which packages are accessible outside the module. So this offers better security. The JDK itself uses this feature to restrict developers from accessing internal JDK jars.

### Easier testing

Since a module contains only a subset of the packages in an application, testing becomes much easier.

## Further Learning

- [Java 9 Modules and More](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fwhats-new-in-java-9%2F)
- [Java 9 New Features](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fjava-9-new-features-in-simple-way-jshell-jpms-and-more%2F)

## Conclusion

In this article, I have an introduction to modules as to what they are, why Java 9 added them and what benefits they provide. In the [next part](https://learnjava.co.in/java-9-module-internals/) of this article, I will be covering the internals of a module and in the [last part](https://learnjava.co.in/creating-a-java-9-module/) I will be explaining how to create a Java 9 module in Eclipse.
