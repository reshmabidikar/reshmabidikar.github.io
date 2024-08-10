---
title: "Java Protected Keyword explained With Code Samples"
date: "2019-08-16"
categories: 
  - "core-java"
  - "java_language_features"
tags: 
  - "protected-keyword"
---

In this article, I will be covering the Java Protected Keyword.

## Introduction

Just like private and public, **protected** is an access specifier. When the protected access specifier is used for a field or method, it becomes accessible in all the subclasses of the class in which the field is defined. The protected access specifier also makes the member accessible in other classes which are in the same package as the class having the protected member.

 

## Accessing a protected field from a sub-class

The following code snippet demonstrates how you can access a protected field in a sub-class:

```
package demo;

public class Base {




private int a;

protected int b;




}

public class Sub extends Base {




public void subMethod() {

super.a=4; //this causes compilation error

super.b=9;




}

}
```

- The class **Base** has a private field **a** and a **protected** field **b**
- The class **Sub** extends **Base**
- It has a method **subMethod** which assigns some values to **a** and **b**
- a=4; - This causes a compilation error since **a** is **private**
- b=9 – This does not cause compilation error since **b** is **protected**
- If the field **a** in **Base** is made protected, the compilation error goes away

## Accessing a protected field from another class in the same package

The following code snippet demonstrates how you can access a protected field from another class in the same package:

```
package demo;

public class AnotherClass {




public void myMethod() {

Base base = new Base();

base.b=6;

System.out.println("In another class in the same package, the value of the protected field is "+base.b);

}

}
```

- A class called **AnotherClass** is defined, it is **not** a subclass of **Base**
- It is in the same package as **Base** i.e. **demo**
- In **myMethod**, a **Base** object **base** is created
- The protected field **b** in **Base** is assigned the value **6**
- There is no compilation error because **AnotherClass** is in the same package as **Base**.

## Accessing a protected field from a different package

The following code snippet demonstrates how you can access a protected field from a different package:

```
package demo2;

import demo.Base;

public class AnotherClass2 {

public void myMethod() {

Base base = new Base();

base.b=7; //will cause compilation error

}

}
```

- **AnotherClass2** is defined in a different package **demo2**
- In **myMethod**, the **protected** field **b** is assigned the value **7**
- This causes a compilation error since **AnotherClass2** is neither a sub-class of **Base** nor is it in the same package

## Accessing a protected field from a sub-class in a different package

The following code snippet demonstrates how you can access a protected field from a sub-class from a different package:

 

```
package demo2;


import demo.Base;


public class AnotherClass3 extends Base{


public void myMethod() {

super.b=8;

}

}
```

 

- **AnotherClass3** is defined in a different package i.e. **demo2** but is a sub-class of **Base**
- In **myMethod**, the protected field **b** is assigned **8**
- This does not cause a compilation error because **AnotherClass3** is a sub-class of **Base**

## Conclusion

So in this article, you saw how the Java protected keyword can be used in various scenarios.
