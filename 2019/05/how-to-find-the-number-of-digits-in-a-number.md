---
title: "How to find the number of digits in a number"
date: "2019-05-13"
categories: 
  - "java-examples"
---

This blog post demonstrates how to count the number of digits in a String.

**Method 1 - Using division**

````

private static int countDigits(int input){ int count = 1;

if(input > 10){ int quotient = 0; do{ count ++; quotient = input/10; input = quotient;

}while(quotient > 9); } return count; }

````

The code checks if the number is greater than 10. If so, it divides the number by 10 and checks the quotient. It continues doing this as long as the quotient is greater than 9.

Method 2 - Using Strings

````

private static int countDigits(int input){ 
  String str = String.valueOf(input); 
  return str.length();
}
````

Here, the input number is converted to a String and then its length is used to find the number of digits.
