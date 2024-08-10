---
title: "Compile time polymorphism vs Runtime polymorphism"
date: "2019-04-24"
categories: 
  - "core-java"
  - "java-interview-questions"
tags: 
  - "overidding"
  - "overloading"
  - "polymorphism-en"
---

Polymorphism is the process where the same action can be performed in a number of different ways. Java supports 2 types of polymorphism – Compile time and runtime.

<iframe style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//ws-in.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&amp;OneJS=1&amp;Operation=GetAdHtml&amp;MarketPlace=IN&amp;source=ac&amp;ref=qf_sp_asin_til&amp;ad_type=product_link&amp;tracking_id=learnjava0d-21&amp;marketplace=amazon&amp;region=IN&amp;placement=9390491622&amp;asins=9390491622&amp;linkId=fd93ec30bf91424ed803ca0809ccf5ee&amp;show_border=false&amp;link_opens_in_new_window=false&amp;price_color=333333&amp;title_color=0066c0&amp;bg_color=ffffff"></iframe>

# Compile time polymorphism

Java supports compile-time polymorphism via method overloading.Method overloading allows us to define two or more methods with the same name within a class but with different parameter declarations.

Consider the following code snippet:

\[java\]

public class AdditionService {

int add() { return 3+5; }

int add(int i) { return i+i; }

int add(int i,int j) { return i+j; }

double add(double i,double j) { return i+j; }

}

\[/java\]

This class has 4 methods with the name add. All four add methods differ in the parameters, so there is no compilation error. 1st add method does not have any parameters, the 2nd add method takes two integer parameters, the 3rd add method takes one integer parameter and the 4th add method takes two double parameters. So the add method is said to be “overloaded” four times.

Since the same action can be performed in a number of different ways, method overloading is an example of polymorphism. It is known a compile-time polymorphism because the version of an overloaded method to be invoked is determined at compile time by the compiler based on the parameters being passed in. So even before Java executes the program, the compiler determines which version of the method to invoke.

# Runtime polymorphism

Java achieves Runtime polymorphism via method overriding. In a class hierarchy, when a method in a subclass has the same name and type signature as a method in its superclass, then the method in the subclass is said to override the method in the superclass.

Consider the following code:

\[java\] public class Vehicle { public void printVehicleType() { System.out.println("This is a vehicle"); } }

public class Car extends Vehicle { public void printVehicleType() { System.out.println("This is a car"); } }

public class Bicycle extends Vehicle {

public void printVehicleType() { System.out.println("This is a bicyle"); }

} \[/java\]

 

Car and Bicycle are both sub classes of Vehicle. Both have a method called printVehicleType.

Now consider the following code:

\[java\] public class VehiclesDemo {

public static void main(String\[\] args) {

Vehicle vehicle = new Vehicle(); Car car = new Car(); vehicle = car; System.out.println("Invoking method with car object:"); vehicle.printVehicleType();

Bicycle bike = new Bicycle(); vehicle=bike; System.out.println("Invoking method with bicycle object:"); vehicle.printVehicleType();

}

} \[/java\]

First, we are creating a vehicle object. We are then creating a car object and assigning it to vehicle. We are then invoking the printVehicleType method using the vehicle variable. This will invoke the method in the car class.

Next, we are creating a bicycle object and assigning it to vehicle. We are then invoking the printVehicleType method again using the vehicle variable. This will invoke the method in the bicycle class.

This is how Java achieves runtime polymorphism. Since the same method call i.e. vehicle.printVehicleType prints different values based on the object assigned to it, this is an example of polymorphism. It is called runtime polymorphism because the version of the overridden method to be invoked is determined at runtime.

# Summary

The following table summarises the differences between compile-time polymorphism and runtime polymorphism.

\[table id=14 /\]
