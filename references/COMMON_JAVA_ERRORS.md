# Common Java Beginner Errors

Use this guide to diagnose the smallest relevant problem first. Always connect the correction to the learner's code and suggest a quick test.

## Error categories

| Category | What happens | Typical example |
|---|---|---|
| Compile error | Java cannot build the program. | Missing `;`, wrong type, undefined variable. |
| Runtime error | The program starts and then fails. | Invalid array index, invalid input. |
| Logic error | The program runs but gives the wrong answer. | Incorrect condition or counter placement. |

## Arrays

### Going past the final index

Problem:

```java
for (int i = 0; i <= numbers.length; i++) {
    System.out.println(numbers[i]);
}
```

Fix:

```java
for (int i = 0; i < numbers.length; i++) {
    System.out.println(numbers[i]);
}
```

Reason: an array of length 5 has valid indexes `0` through `4`. Index `5` is outside the array.

### Creating an array but not filling it

```java
int[] scores = new int[5];
```

This creates five positions initialized to `0`; it does not read or generate five scores automatically.

### Confusing array length and last index

```text
length = 5
last valid index = 4
```

## Strings

### Comparing text with `==`

Problem:

```java
if (color == "blue")
```

Fix:

```java
if (color.equals("blue"))
```

Safer when `color` might be `null`:

```java
if ("blue".equals(color))
```

Reason: `.equals()` compares text content. `==` compares references for objects.

### Case differences

`"Blue"` and `"blue"` are different strings. Use this only when the assignment allows case-insensitive input:

```java
color.equalsIgnoreCase("blue")
```

## Scanner input

### `nextInt()` followed by `nextLine()`

Problem:

```java
int age = input.nextInt();
String name = input.nextLine();
```

The remaining newline may be consumed as the name.

Fix:

```java
int age = input.nextInt();
input.nextLine();
String name = input.nextLine();
```

### Input type does not match

If `nextInt()` receives `hello`, Java can throw `InputMismatchException`. For beginner assignments, first explain that the input must match the expected type. Add validation only if required.

## Loops and counters

### Counter declared or reset inside the loop

Problem:

```java
for (int i = 0; i < colors.length; i++) {
    int blueCount = 0;
    if (colors[i].equals("blue")) {
        blueCount++;
    }
}
```

Fix: declare the counter before the loop so it keeps its value between iterations.

```java
int blueCount = 0;
for (int i = 0; i < colors.length; i++) {
    if (colors[i].equals("blue")) {
        blueCount++;
    }
}
```

### Loop variable never changes

```java
int i = 0;
while (i < 5) {
    System.out.println(i);
}
```

Add `i++;` when appropriate, or the condition may remain true forever.

### Off-by-one condition

Translate the boundary words carefully:

- “less than 5” → `value < 5`
- “at most 5” → `value <= 5`
- “at least 5” → `value >= 5`

## Arithmetic

### Integer division

```java
double result = 3 / 5;
```

`3 / 5` is calculated as integer division first, producing `0`.

Use:

```java
double result = 3.0 / 5;
```

For “at least half” counting, this often avoids division:

```java
count * 2 >= total
```

### Assignment instead of comparison

`=` stores a value. `==` compares primitive values. Java rejects some accidental assignments in conditions, but learners should still identify their different purposes.

## Methods and constructors

### Return type does not match

```java
public int getName() {
    return name;
}
```

If `name` is a `String`, the return type must be `String`.

### Missing return value

A non-`void` method must return a compatible value on every possible path.

### Constructor incorrectly has a return type

Problem:

```java
public void Student(String name) {
    this.name = name;
}
```

Fix:

```java
public Student(String name) {
    this.name = name;
}
```

A constructor has the same name as the class and no return type, including `void`.

### Field and parameter confusion

```java
public void setName(String name) {
    this.name = name;
}
```

`this.name` is the object's field; `name` is the method parameter.

## Classes and files

### Public class name does not match filename

```java
public class Student
```

should normally be saved in `Student.java`.

### Calling an instance method from a static context

`main` is normally `static`. Create an object before calling its instance method:

```java
Student student = new Student("Ana");
student.printInfo();
```

Do not solve this automatically by making every field and method `static`.

## Recursion

Check both requirements:

1. A base case stops the recursion.
2. Each call moves toward the base case.

```java
public static int sumTo(int n) {
    if (n == 1) {
        return 1;
    }
    return n + sumTo(n - 1);
}
```

If `n` can be `0`, the base case and input assumptions must be adjusted.

## Debugging checklist

1. Read the first meaningful error message and line number.
2. Classify the problem as compile, runtime, or logic.
3. Compare expected behavior with actual behavior.
4. Trace the smallest input that reproduces the problem.
5. Change one relevant thing at a time.
6. Compile and rerun the same test.
7. Test a normal case and a boundary case.

Avoid rewriting the whole program before understanding the cause.
