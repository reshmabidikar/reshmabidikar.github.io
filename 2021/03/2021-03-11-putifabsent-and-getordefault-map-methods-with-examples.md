---
title: "putIfAbsent and getOrDefault Map methods with examples"
date: "2021-03-11"
categories: 
  - "java-8-examples"
coverImage: "Map-putIfAbsent-getOrDefault-scaled.jpg"
---

In my [earlier](https://learnjava.co.in/java-8-map-compute-map-computeifpresent-map-computeifabsent-method-examples/) article, I had explained the Map.compute, Map.computeIfPresent and Map.computeIfAbsent methods added by Java 8. In addition, Java 8 has added two other methods called **putIfAbsent** and **getOrDefault** to the Map interface.  In this article, I will be explaining the these methods. \[table id=24 /\]

## How putIfAbsent works

Prior to Java 8, the Map interface had a **put** method. This method accepts a key and a value as a parameter and adds the key-value pair to the Map. If the key passed to this method is present in the Map, its value gets overwritten with the new value. However, sometimes, we may wish to add the key-value pair only if the key is absent from the Map. The **putIfAbsent** method caters to such situations. Thus, it accepts a key and a value as a parameter and adds the key-value pair to the Map only if the specified key is not present in the Map. If the key is present in the Map, it does not do anything. The following code demonstrates the **put** and **putIfAbsent** methods:

```
Map<Integer,String> shapesMap = new HashMap<>();
shapesMap.put(1, "circle");
shapesMap.put(2, "square");
shapesMap.put(3, "triangle");
shapesMap.put(1, "rectangle");
System.out.println("Value for key 1:"+shapesMap.get(1));
shapesMap.putIfAbsent(2, "pentagon");
System.out.println("Value for key 2:"+shapesMap.get(2));
shapesMap.putIfAbsent(4, "pentagon");
System.out.println("Value for key 4:"+shapesMap.get(4));
```

- Line 1 creates a Map called **shapesMap** which has an Integer key and a String value
- Lines 2-4 add some values to it via the **put** method
- Line 6 again invokes put with the key-value pair **1, rectangle**. Since the key **1** is already present in the Map, this line overwrites its value with **rectangle**
- Line 9 invokes the **putIfAbsent** method with **2, pentagon**. Since the key **2** is already present in the Map, the **putIfAbsent** method does not overwrite its value.
- Line 12 again invokes the **putIfAbsent** method with **4, pentagon**. Since the key **4** is not present in the Map, the **putIfAbsent** method adds it to the map.

This code produces the following output:

```
Value for key 1:rectangle
Value for key 2:square
Value for key 4:pentagon
```

## How getOrDefault works

Prior to Java 8, the Map interface had a **get** method. This method accepts a key as a parameter and returns the value corresponding to the key. If the key passed to this method is not present in the Map, its returns a **null**. However, sometimes, we may wish to return a default value if the specified key is not present in the Map. The **getOrDefault** method caters to such situations. Thus, it accepts a key and a default value as a parameter. It returns the value corresponding to the key only if the key is present in the map. If the key is not present in the Map, it returns the specified default value. The following code demonstrates the **get** and **getOrDefault** methods:

```
Map<Integer,String> shapesMap = new HashMap<>();
shapesMap.put(1, "circle");
shapesMap.put(2, "square");
shapesMap.put(3, "triangle");
System.out.println("Value for key 1:"+shapesMap.get(1));
System.out.println("Value for key 5:"+shapesMap.get(5));
System.out.println("Value for key 2:"+shapesMap.getOrDefault(2,"pentagon"));
System.out.println("Value for key 5:"+shapesMap.getOrDefault(5,"pentagon"));
```

- Line 1 creates a Map called **shapesMap** which has an Integer key and a String value
- Lines 2-4 add some values to **shapesMap** via the **put** method
- Line 6 invokes **get** method with the key **1**. Since the key **1** is present in the Map, this returns its value that is **circle**
- Line 7 invokes **get** method with the key **5**. Since the key **5** is not present in the Map, this returns a **null**
- Line 9 then invokes the **getOrDefault** method with the key **2** and the value **pentagon**. Since the key **2** is present in the Map, the **getOrDefault** method returns the value corresponding to **2** that is **square**
- Line 10 then invokes the **getOrDefault** method with the key **5** and the value **pentagon**. Since the key **5** is not present in the Map, the **getOrDefault** method returns the default value that is **pentagon**.

This code produces the following output:

```
Value for key 1:circle
Value for key 5:null
Value for key 2:square
Value for key 5:pentagon
```

## Conclusion

So, in this article, we saw how the **putIfAbsent** and **getOrDefault** methods work. Just to summarize, the **putIfAbsent** adds the a key-value pair to the Map only if the key is absent in the Map. The **getOrDefault** returns the value corresponding to a key if the key is present in the Map. Otherwise, it returns a default value.
