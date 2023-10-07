The Java Math class has many methods that allows you to perform mathematical tasks on numbers.

---

## Math.max(_x,y_)

The `Math.max(_x_,_y_)` method can be used to find the highest value of _x_ and _y_:

### Example

```java
Math.max(5, 10);
```

---

## Math.min(_x,y_)

The `Math.min(_x_,_y_)` method can be used to find the lowest value of _x_ and _y_:

### Example

```java
Math.min(5, 10);
```

---

## Math.sqrt(_x_)

The `Math.sqrt(_x_)` method returns the square root of _x_:

### Example

```java
Math.sqrt(64);
```

---

---

## Math.abs(_x_)

The `Math.abs(_x_)` method returns the absolute (positive) value of _x_:

### Example

```java
Math.abs(-4.7);
```

---

## Random Numbers

`Math.random()` returns a random number between 0.0 (inclusive), and 1.0 (exclusive):

### Example

```java
Math.random();
```

To get more control over the random number, for example, if you only want a random number between 0 and 100, you can use the following formula:

### Example

```java
int randomNum = (int)(Math.random() * 101);  // 0 to 100
```

---
For more Math Class See Below
[[More Math]]