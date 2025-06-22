---
title: "Java 9 Module Internals Explained in Brief"
date: "2020-02-04"
categories: 
  - "java-9"
tags: 
  - "java9"
  - "java9modules"
---

One of the new features added by Java 9 is the module system. This article is the second part in a 3 part article. In [Part 1](https://learnjava.co.in/java-9-modules-introduction/), I gave a high level introduction to modules and the advantages that they provide. In this part, I will dive more into the details of what exactly a module is, what it consists of and other module internals.

See also [Module Introduction](https://learnjava.co.in/java-9-modules-introduction/) and [Creating a Module](https://learnjava.co.in/creating-a-java-9-module/).

## What is a module

As explained in the introductory article on modules, modules are basically groups of packages. Modules help to organize the code better and to achieve the Single Responsibility Principle(SRP). Also, a module can be deployed by itself. So if there is a large application, you can break it down into modules. Each module can be built into a separate jar file and deployed as required instead of deploying a big fat jar file for the whole application.

## Module Descriptor

Along with very module, you need to provide a module descriptor. The module descriptor needs to be present at the root of the module. An important point to note is that the module descriptor is not an XML or text configuration file. It is a java file with the name module-info.java. It contains the following information:

- **Name** - This specifies the name of the module
- **exports** - This specifies the packages within the module that will be available to other modules
- **requires** - This specifies the modules that the current module depends on
- **uses** -This specifies the services that the current module consumes.
- **provides** - This specifies the services that the current module provides
- **open** - This specifies that the classes in the currently module can be accessed via Java reflection

## Conclusion

So in this article, we examined modules in a bit more detail. We understood what is a module descriptor and the information that can be specified in a module descriptor. In the [last part](https://learnjava.co.in/creating-a-java-9-module/) of this article, we will see how to create a Java 9 module.
