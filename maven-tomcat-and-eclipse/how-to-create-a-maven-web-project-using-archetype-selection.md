---
title: "How to create a Maven web project using archetype selection"
date: "2022-02-19"
categories: 
  - "eclipse_and_maven"
---

In my [earlier](how-to-create-a-maven-web-project-in-eclipse.md) article, we learned how to create a Java web project in Eclipse and how to add Maven support to it. In this article, we will learn how to create a Maven web project using archetype selection.

## Create Maven Web Project In Eclipse

Step 1 - In Eclipse, Click on **File** > **New** > **Other**. Click on **Maven Project**. Click **Next**:

[![](images/maven-web-project-with-archetype/2-300x197.png)](images/maven-web-project-with-archetype/2.png)

Step 2 - The following screen is displayed. Click **Next**:

[![](images/maven-web-project-with-archetype/3-300x265.png)](images/maven-web-project-with-archetype/3.png)

Step 3 - In the Filter text box, type "**maven-archetype-webapp**". Select "**org.apache.maven.archetypes**". Click **Next**:

[![](images/maven-web-project-with-archetype/5-300x160.png)](images/maven-web-project-with-archetype/5.png)

Step 4 - Enter **Group Id** and **Artifact Id**. Click **Finish**:

[![](images/maven-web-project-with-archetype/6-1024x548.png)](images/maven-web-project-with-archetype/6.png)

This creates a web project with the required directory structure:

[![](images/maven-web-project-with-archetype/7-300x267.png)](images/maven-web-project-with-archetype/7.png)

Now you can add the necessary dependencies to your pom file as explained in [this](how-to-add-maven-dependencies-via-eclipse.md) post. So for example, if you are creating a Spring application, you can add Spring dependencies. You can also use this as a template to create any web application with Maven support.

## Further Learning

- [Apache Maven Beginner to Guru](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fapache-maven-beginner-to-guru%2F)
- [Maven Crash Course](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fmavencrashcourse%2F)
- [Java Programming in Eclipse](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Feclipse-the-basic-java-programming-course%2F)

## Conclusion

So, in this article, we understood how to create a Maven web project in Eclipse using archetype selection.
