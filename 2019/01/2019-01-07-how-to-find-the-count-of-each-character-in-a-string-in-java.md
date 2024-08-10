---
title: "How to find the count of each character in a String in Java"
date: "2019-01-07"
categories: 
  - "java-string-examples"
  - "strings"
tags: 
  - "java-string-handling"
---

In this blog post, I will be demonstrating how you can determine the number of occurrences of each character in a String. Consider the following code snippet:

\[java\]

package learnjava.strings;

import java.util.HashMap; import java.util.Map;

public class CountCharactersDemo {

public static void main(String\[\] args) { String str = "Hello World"; Map&lt;Character,Integer&gt; characterCountMap = new HashMap&lt;Character,Integer&gt;(); //map stores each character and its count char\[\] charsInStr = str.toCharArray(); for(char c:charsInStr){ if(characterCountMap.containsKey(c)){ //if the character is already in the map, just increment its count int count = characterCountMap.get(c); count++; characterCountMap.put(c, count); } else{ //if the character is not in the map, add it to the map characterCountMap.put(c, 1); }

} for(Character c:characterCountMap.keySet()){ System.out.println("Character "+c+" occurs "+characterCountMap.get(c)); }

}

}

\[/java\]

 

The _characterCountMap_ defines a HashMap that stores each character as a key and its count as a value. A for loop then iterates through the characters in the input String. It checks if the character is already in the map. If so, it just increments the count. If the character is not in the map, it adds it to the Map. So when you run this program, you will get the following output:

```
Character occurs 1
Character r occurs 1
Character d occurs 1
Character e occurs 1
Character W occurs 1
Character H occurs 1
Character l occurs 3
Character o occurs 2
```
