---
title: "How to create a Maven web project in Eclipse"
date: "2019-06-15"
categories: 
  - "eclipse_and_maven"
tags: 
  - "eclipse"
  - "maven"
  - "web-project"
---

In this blog post, I will be explaining how to create a web project in Eclipse with Maven support.

# Create a Dynamic web project

Step 1 -Click on "File --> New --> Other"

[![](images/1-1-300x198.png)](images/1-1.png)

Step 2 - Click on Dynamic Web Project

[![](images/2-1-300x204.png)](images/2-1.png)

Step 3 - Type some project name

[![](images/3-1-300x212.png)](images/3-1.png)

Step 4 - Click on Next

[![](images/4-1-300x217.png)](images/4-1.png)

Step 5 - Click on "Next"

[![](images/5-1-300x222.png)](images/5-1.png)

Step 6 - "Click on Finish". This will create a project as follows:

[![](images/6-1-300x225.png)](images/6-1.png)

# Create web.xml

Sometimes, Eclipse may not automatically create the web.xml file. So if this file is not present in your web-inf folder, you need to follow these steps.

Step 1 - Right click on project --> Java JEE Tools --> Generate Deployment Descriptor Stub

[![](images/w1-300x291.png)](images/w1.png)

This will create a web.xml file as follows:

[![](images/w2-300x236.png)](images/w2.png)

# Add Maven Support

Step 1 - Right-click on Project --> Configure --> Convert to Maven Project![](images/m1-300x268.png)

Step 2 - Click Finish

![](images/m2-300x184.png)

This will add a pom file to the project as follows:

![](images/m3-300x223.png)

Now you can add the necessary dependencies to your pom file. So for example, if you are creating a Spring application, you can add Spring dependencies.

You can also use this as a template to create any web application with Maven support.

**Further Reading**

- [Apache Maven Beginner to Guru](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fapache-maven-beginner-to-guru%2F)
- [Maven Crash Course](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fmavencrashcourse%2F)
- [Java Programming in Eclipse](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Feclipse-the-basic-java-programming-course%2F)
