---
title: "Java 9 Module creation with code samples"
date: "2020-03-17"
categories: 
  - "java-9"
---

One of the new features added by Java 9 is the module system. This article is the last part in a 3 part article. In[Part 1](java-9-modules-introduction.md), I gave a high level introduction to modules and the advantages that they provide. In [Part 2](java-9-module-internals.md), I covered the details of what exactly a module is, what it consists of and other module internals. In this part, I will be explaining how to create and use a module in Eclipse.

See also [Module Introduction](java-9-modules-introduction.md) and [Module Internals](java-9-module-internals.md)

## Creating a Module

As covered in my [earlier](java-9-module-internals.md) article, a module is a group of packages that helps to organize code better. Let us first create a Java project that has a module.

**Step 1** - Ensure that Java 9 is installed and configured in Eclipse.

**Step 2** - Create a new Java project. Enter a project name. Ensure that JDK 9 is selected.

[![](images/module-creation/1-300x281.png)](images/module-creation/1.png)

**Step 3** - Click Next. The following screen is shown:

[![Creating a Java 9 Module in Eclipse](images/module-creation/2-300x278.png)](images/module-creation/2.png)

**Step 4**: Click "Finish". A screen for entering module name is shown as below:

[![Creating a Java 9 Module in Eclipse](images/module-creation/3-300x279.png)](images/module-creation/3.png)

**Step 5** - Enter the module name as "**com.learnjava.calculatormodule**"

[![Creating a Java 9 Module in Eclipse](images/module-creation/4-300x280.png)](images/module-creation/4.png)

**Step 6** - Click "Create". The Java project is created successfully with the project structure as shown below. The **module-info.java** file is created. As covered in my [earlier](java-9-module-internals.md) article, the "module-info.java" file contains information about the packages required by the module, exported by the module, etc.

[![Creating a Java 9 Module in Eclipse](images/module-creation/5-1-300x174.png)](images/module-creation/5-1.png)

**Step 7** - Create new package "**com.learnjava.calculator**" in the project:

[![Creating a Java 9 Module in Eclipse](images/module-creation/6-300x217.png)](images/module-creation/6.png)

**Step 8** - Create a class called Calculator in the package:

[![Creating a Java 9 Module in Eclipse](images/module-creation/7-274x300.png)](images/module-creation/7.png)

**Step 9**: Add the following code in the Calculator class:

```java
public class Calculator {
  
  public int add(int a,int b) {
    return a+b;
  }

}
```

**Step 10** - Specify the package to be exported in the module-info file:

[![Creating a Java 9 Module in Eclipse](images/module-creation/8-300x101.png)](images/module-creation/8.png) So now, we have created a Java project with a module "**com.learnjava.calculatormodule"**. This module exports the **com.learnjava.calculator** that has the Calculator.java class.

## Creating a Module Client

A module client is a separate module that uses code from another module. So let us write some code that uses the Calculator class.

**Step 1** - Follow steps 1-5 above and create a new project "**CalculatorClient"** with a module "**com.learnjava.calculatorclient**" as follows:

[![Creating a Java 9 Module Client](images/module-creation/c1-300x109.png)](images/module-creation/c1.png)

**Step 2** - Create a new package "**com.learnjava.client**" and a class "**CalculatorClient**" within that package:

[![Creating a Java 9 Module Client](images/module-creation/c2-300x117.png)](images/module-creation/c2.png)

**Step 3** - Specify the required package in the module-info file:

[![Creating a Java 9 Module Client](images/module-creation/c3-1-300x80.png)](images/module-creation/c3-1.png)

So this means that the **com.learnjava.calculatorclient** module requires the **com.learnjava.calculatormodule.** If this requires attribute is not specified here, the **com.learnjava.calculatorclient** module will not be able to access the **com.learnjava.calculatormodule.**

The above step will cause a compilation error since the **com.learnjava.calculatormodule**is not present on the build path**.** So we need to fix the project setup as follows:

**Step 4a**: Right click on the project --> properties:

[![Creating a Java 9 Module Client](images/module-creation/c4-300x162.png)](images/module-creation/c4.png)

**Step 4b**: Click on "Add".

[![Creating a Java 9 Module Client](images/module-creation/c5-300x166.png)](images/module-creation/c5.png)

**Step 4c**: Select CalculatorModule. Click OK

[![Creating a Java 9 Module Client](images/module-creation/c6-212x300.png)](images/module-creation/c6.png)

**Step 4d:** This adds the calculator module to the path. Click on "Apply And Close":

[![Creating a Java 9 Module Client](images/module-creation/c7-300x162.png)](images/module-creation/c7.png)

Now the compilation error will go away.

**Step 5:** Add the following code to the CalculatorClient class:

```java
package com.learnjava.client;

import com.learnjava.calculator.Calculator;

public class CalculatorClient {
  
  public static void main(String args[]) {
    Calculator calculator = new Calculator();
    int result = calculator.add(5, 10);
    System.out.println("Result is:"+result);
  }

}

```

So this code invokes the **Calculator.add** method from the **com.learnjava.calculatormodule**

**Step 6:** Run the CalculatorClient class. This will print the following output:

```
17
```

## Conclusion

So in this article, we saw how to create and use a Java 9 module in Eclipse. This article is the final article in the Java 9 series.
