## hort Hand If...Else

There is also a short-hand [[If..Else]], which is known as the **ternary operator** because it consists of three operands.

It can be used to replace multiple lines of code with a single line, and is most often used to replace simple if else statements:

### Syntax

```java
variable = (condition) ? expressionTrue :  expressionFalse;
```

Instead of writing:

### Example

```java
int time = 20;
if (time < 18) {
  System.out.println("Good day.");
} else {
  System.out.println("Good evening.");
}
```

You can simply write:

### Example

```java
int time = 20;
String result = (time < 18) ? "Good day." : "Good evening.";
System.out.println(result);
```