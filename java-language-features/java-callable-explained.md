---
title: "Java Callable Interface Explained with Code Samples"
date: "2019-12-10"
categories: 
  - "core-java"
  - "java_language_features"
tags: 
  - "java-callable"
---

In this article, I will be explaining the Callable interface in Java. I will be explaining what is Runnable and Callable in Java and what is the use of the Callable interface.

## Runnable Interface

Right from the start, the Runnable interface has been associated with multi-threaded programming. The Runnable interface provides a run method that executes code in a separate thread. The following code demonstrates this:

```java
public class RunnableDemo {

  public static void main(String[] args) {
    System.out.println("Creating new thread in main");
    Runnable r = () -> System.out.println("Executing thread body....");
    Thread myThread = new Thread(r);
    myThread.start();
    System.out.println("Completed main");

  }

}
```

So this code first creates a new Runnable interface and uses a lambda expression to implement the run method. The code then creates a new Thread and invokes the start method which spawns a new Thread and executes the code in the Runnable implementation.

The downside of this approach is that you have no way of knowing when the Thread completes. Also, there is no way of returning a value from the run method.

## What is Java Callable Interface?

Java 5 introduced a new interface called Callable to overcome the limitations of the Runnable interface. This interface is similar to Runnable and you can use it to spawn a new Thread. It has a method called "call". In addition to executing code in a new Thread, you can also use this interface to return a value. The following code demonstrates this:

```java
public class CallableDemo {

  public static void main(String[] args) throws InterruptedException, ExecutionException {
    System.out.println("Creating new thread in main");
    Callable<String> callable = () -> {System.out.println("Executing thread body....");
                        return "Hello World";
                       };
    FutureTask<String> task = new FutureTask<String>(callable);
    Thread myThread = new Thread(task);
    myThread.start();
    String result = task.get();
    System.out.println("Result:"+result);
    System.out.println("Completed main");

  }

}
```

So this code creates a Callable which returns a result of type String. The call method is implemented via a lambda expression that returns the String "Hello World".

Java 5 has added a FutureTask class to the concurrency API. This accepts as parameter a Callable instance. The code then creates a new Thread and passes the FutureTask as a parameter. The code then starts the Thread. The FutureTask has a method get, the code invokes this to obtain the result from the Thread. So this code prints the following output:

```
Creating new thread in main
Executing thread body....
Result:Hello World
Completed main
```

## Callable With Executors

The Callable interface is mostly used with the Executor framework and uses a Future to obtain a result. The Executor framework is part of the Concurrency API added in Java 5. The following code demonstrates this:

```java
public class CallableWithExecutorDemo {

  public static void main(String[] args) throws InterruptedException, ExecutionException {
    Callable<String> callable = () -> {
      System.out.println("In Thread");
      return "Hello World";
    };

    System.out.println("Starting new Thread");
    ExecutorService executorService = Executors.newSingleThreadExecutor();
    Future<String> future = executorService.submit(callable);
    System.out.println("Retrieving Result...");
    String result = future.get(); // this blocks till result is available
    System.out.println("Result=" + result);

    executorService.shutdown();

  }

}
```

As before, this code creates a Callable which returns a result of type String. The call method is implemented via a lambda expression that returns the String "Hello World".

The code then creates a new ExecutorService. ExecutorService is part of the Executor framework, explaining it in detail here would be beyond the scope of this article. The code then invokes the ExecutorService.submit method with the Callable instance which spawns a new Thread. The ExecutorService.submit method returns a Future instance that holds the result of the computation. The Future interface has a method called get which waits for the thread to complete and then returns the result. So this code prints the following output:

```
Starting new Thread
Retrieving Result...
In Thread
Result=Hello World
```

## Conclusion

So in this article, we saw learned about the Java Callable interface and how you can use it to obtain the results of computation from a separate thread.
