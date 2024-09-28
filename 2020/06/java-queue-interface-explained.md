---
title: "Java Queue Interface Methods Explained With Code Samples"
date: "2020-06-19"
categories: 
  - "java_language_features"
---

One of the lesser known Collection interfaces in the java.util.Queue interface. In this article, I will be covering this interface in detail.

## What is the Java Queue interface?

The **java.util.Queue** interface extends the **java.util.Collection** interface. It provides a **First In First Out (FIFO)** behavior and you can use it to represent a Queue data structure. It has several implementations in the Collection API. The **java.util.LinkedList** and **java.util.PriorityQueue** are the most common implementations

## Java Queue Interface Operations

There are several methods available on the queue interface that help to perform various queue operations.

### add

The `add`method supports adding an element to the Queue. if for some reason the `add` method is unable to add the element, it throws an **Exception.**

**Sample Code (Without Exception)**

```
Queue<String> daysOfTheWeek = new LinkedList<String>();
daysOfTheWeek.add("Monday");
daysOfTheWeek.add("Tuesday");
daysOfTheWeek.add("Wednesday");

System.out.println(daysOfTheWeek);
```

- Line 1 creates a **daysOfTheWeek** queue. It uses the **LinkedList** implementation
- Lines 2-4 use the **add** method to add some values to the queue
- Line 6 prints the queue.

**Output**

```
[Monday, Tuesday, Wednesday]


```

**Sample Code (With Exception)**

As mentniod earlier, if the `add` method is unable to add the element, it throws an **Exception.** This behaviour is not evident when you use the **LinkedList** implementation of a Queue. However it is evident for the **ArrayBlockingQueue** implementation which has a capacity restriction.

```
	        Queue<String> daysOfTheWeek = new ArrayBlockingQueue<String>(1); 
		boolean added = daysOfTheWeek.add("Monday"); 
		System.out.println(added);
		added = daysOfTheWeek.add("Tuesday"); 
		System.out.println(added);
```

- Line 1 creates a **daysOfTheWeek** queue. It uses the **ArrayBlockingQueue** implementation and specifies the size as 1
- Line 2 uses the **add** method to add the value **Monday** which returns **true**
- Line 4 uses the **add** method to add the value **Tuesday** 
- Since this is a Queue with size 1, Line 4 causes an exception.

**Output:**

```
trueException in thread "main" 
java.lang.IllegalStateException: Queue full
at java.base/java.util.AbstractQueue.add(AbstractQueue.java:98)
at java.base/java.util.concurrent.ArrayBlockingQueue.add(ArrayBlockingQueue.java:326)
at demo.QueueDemo.main(QueueDemo.java:14)
```

### offer

The `offer` method is similar to `add`. So it adds an element at the head of the queue . The only difference is if for some reason the `offer` method is unable to add an element to the queue, it returns a false.

**Sample Code**

```
Queue<String> daysOfTheWeek = new ArrayBlockingQueue<String>(1); 
boolean added = daysOfTheWeek.offer("Monday"); 
System.out.println("Added Monday:"+added);
added = daysOfTheWeek.offer("Tuesday"); 
System.out.println("Added Tuesday:"+added);

```

- Line 1 creates a **daysOfTheWeek** queue. It uses the **ArrayBlockingQueue** implementation and specifies the size as 1
- Lines 2 uses the **offer** method to add the value **Monday** which returns **true**
- Lines 4 uses the **offer** method to add the value **Monday** which returns **false** since the queue is full

**Output:**

```
Added Monday:true
Added Tuesday:false
```

### remove

The `remove`methods helps removing a value from a Queue. It removes the element at the **head** of the queue. If the queue is empty, it throws a **NoSuchElementException**

**Sample Code (Non-empty Queue)**

```
Queue<String> daysOfTheWeek = new LinkedList<String>();
daysOfTheWeek.add("Monday");
daysOfTheWeek.add("Tuesday");
daysOfTheWeek.add("Wednesday");

String day = daysOfTheWeek.remove();
System.out.println(day);
```

- Line 1 creates a **daysOfTheWeek** queue. It uses the **LinkedList** implementation
- Lines 2-4 use the **add** method to add some values to the queue
- Line 5 uses the remove method to remove the head of the queue, in this case **Monday**
- Line 6 prints the removed value

**Output:**

```
Monday
```

**Sample Code (Empty Queue)**

As mentioned earlier, when you invoke `remove`on an empty queue, it throws a **NoSuchElementException**

```
Queue<String> daysOfTheWeek = new LinkedList<String>(); 
String day = daysOfTheWeek.remove(); 
System.out.println(day);
```

- Line 1 creates a **daysOfTheWeek** queue. It uses the **LinkedList** implementation
- Line 2 invokes the remove method
- Since the Queue is empty, it causes a **NoSuchElementException**

**Output:**

```
Exception in thread "main" java.util.NoSuchElementException
at java.base/java.util.LinkedList.removeFirst(LinkedList.java:274)
at java.base/java.util.LinkedList.remove(LinkedList.java:689)
at demo.QueueDemo.main(QueueDemo.java:11)
```

### poll

The `poll`method is similar to `remove`. So it removes the element at the head of the queue. The only difference is that if the queue is empty, the `poll`method returns a **null**. The `remove`method on the other hand throws a **NoSuchElementException** .

**Sample Code:**

```
Queue<String> daysOfTheWeek = new LinkedList<String>();
daysOfTheWeek.add("Monday");

String day = daysOfTheWeek.poll();
System.out.println(day);

day = daysOfTheWeek.poll();
System.out.println(day);
```

- Line 1 creates a **daysOfTheWeek** queue. It uses the **LinkedList** implementation
- Lines 2 uses the **add** method to add the value **Monday** to the queue
- Line 3 uses the **poll** method to remove the head of the queue, in this case **Monday**
- Line 4 again invokes the **poll** method which returns a null since the queue is empty

**Output:**

```
Monday
null
```

### element

The `element`method returns the head of the queue but does not remove it from the queue. It throws a **NoSuchElementException** if the queue is empty.

**Sample Code:**

```
		Queue<String> daysOfTheWeek = new LinkedList<String>(); 
		daysOfTheWeek.add("Monday"); 
		String day = daysOfTheWeek.element(); 
		System.out.println(day); 
		day = daysOfTheWeek.element(); 
		System.out.println(day);
		
		daysOfTheWeek = new LinkedList<String>(); 
		day = daysOfTheWeek.element(); 
		System.out.println(day);

```

- Line 1 creates a **daysOfTheWeek** queue. It uses the **LinkedList** implementation
- Lines 2 uses the **add** method to add the value **Monday** to the queue
- Line 3 uses the **element** method to retrieve the head of the queue, in this case **Monday.** It does not remove this value from the queue
- Line 5 again uses the **element** method again to retrieve the head of the queue. Since the call at Line 3 does not remove the value, this call also returns **Monday**
- Line 8 initializes the **daysOfTheWeek** Queue to a new empty Queue
- Line 9 uses the **element** method to retrieve the head of the queue
- Since the queue is empty, this causes a **NoSuchElementException**

**Output:**

```
Monday
Monday
Exception in thread "main" java.util.NoSuchElementException
at java.base/java.util.LinkedList.getFirst(LinkedList.java:248)
at java.base/java.util.LinkedList.element(LinkedList.java:667)
at demo.QueueDemo.main(QueueDemo.java:18)
```

### peek

The `peek`method is similar to `element`. So it returns the element at the head of the queue without removing it. The only difference is that if the queue is empty, the `peek`method returns a **null**. The `element`method on the other hand throws a **NoSuchElementException**.

**Sample Code:**

```
Queue<String> daysOfTheWeek = new LinkedList<String>();
daysOfTheWeek.add("Monday");

String day = daysOfTheWeek.peek();
System.out.println(day);

daysOfTheWeek = new LinkedList<String>();
day = daysOfTheWeek.peek();
System.out.println(day);
```

- Line 1 creates a **daysOfTheWeek** queue. It uses the **LinkedList** implementation
- Lines 2 uses the **add** method to add the value **Monday** to the queue
- Line 4 uses the **peek** method to retrieve the head of the queue, in this case **Monday.** It does not remove this value from the queue
- Line 7 initializes the **daysOfTheWeek** Queue to a new empty Queue
- Line 9 uses the **element** method to retrieve the head of the queue
- Since the queue is empty,it returns **null**

**Output:**

```
Monday
null
```

## Conclusion

So in this article, we understood the java.util.Queue interface. We also saw the various operations like peek, poll, add, remove and element on the Queue interface.
