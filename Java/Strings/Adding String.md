# Java Numbers and Strings

---

## Adding Numbers and Strings

WARNING!

Java uses the `+` operator for both addition and concatenation.

Numbers are added. Strings are concatenated.

If you add two numbers, the result will be a number:

### Example

```java
int x = 10;
int y = 20;
int z = x + y;  // z will be 30 (an integer/number)
```

If you add two strings, the result will be a string concatenation:

### Example

```java
String x = "10";
String y = "20";
String z = x + y;  // z will be 1020 (a String)
```

If you add a number and a string, the result will be a string concatenation:

### Example

```java
String x = "10";
int y = 20;
String z = x + y;  // z will be 1020 (a String)
```