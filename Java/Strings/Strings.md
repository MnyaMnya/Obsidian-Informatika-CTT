## Java Strings

Strings are used for storing text.

A `String` variable contains a collection of characters surrounded by double quotes:

### Example

Create a variable of type `String` and assign it a value:

```java
String greeting = "Hello";
```

---
Refer Below For More Explanation

[[Concatenation]]
[[Adding String]]
[[Special Char]]
## String Length

A String in Java is actually an object, which contain methods that can perform certain operations on strings. For example, the length of a string can be found with the `length()` method:

### Example

```java
String txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
System.out.println("The length of the txt string is: " + txt.length());
```

---

## More String Methods

There are many string methods available, for example `toUpperCase()` and `toLowerCase()`:

### Example

```java
String txt = "Hello World";
System.out.println(txt.toUpperCase());   // Outputs "HELLO WORLD"
System.out.println(txt.toLowerCase());   // Outputs "hello world"
```

---

## Finding a Character in a String

The `indexOf()` method returns the **index** (the position) of the first occurrence of a specified text in a string (including whitespace):

### Example

```java
String txt = "Please locate where 'locate' occurs!";
System.out.println(txt.indexOf("locate")); // Outputs 7
```

Java counts positions from zero.  
0 is the first position in a string, 1 is the second, 2 is the third ...