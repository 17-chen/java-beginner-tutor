# Beginner Java Code Tracing Guide

Code tracing means following a program in execution order and recording how important values change. Use small inputs so the learner can see every meaningful step.

## Basic tracing workflow

1. Write down the input.
2. Identify variables whose values can change.
3. Start at the first executed statement, usually inside `main`.
4. Evaluate conditions as `true` or `false`.
5. Record assignments, counter changes, output, and method calls.
6. For loops, make one row per iteration.
7. Compare the final state and output with the requirement.

Do not trace imports, braces, or declarations that do not affect understanding.

## Variable table template

| Step | Executed code | Variable values after the step | Output |
|---:|---|---|---|
| 1 | `int total = 0;` | `total = 0` | — |
| 2 | `total = total + 4;` | `total = 4` | — |
| 3 | `System.out.println(total);` | `total = 4` | `4` |

## Trace a `for` loop

Code:

```java
int total = 0;
for (int i = 1; i <= 3; i++) {
    total = total + i;
}
```

Trace:

| Iteration | `i` | Condition `i <= 3` | New `total` |
|---:|---:|---|---:|
| start | 1 | true | 0 |
| 1 | 1 | true | 1 |
| 2 | 2 | true | 3 |
| 3 | 3 | true | 6 |
| stop | 4 | false | 6 |

Explain the four loop parts separately:

```text
initialization → int i = 1
condition      → i <= 3
body           → total = total + i
update         → i++
```

## Trace an array traversal

Code:

```java
int[] numbers = {4, 7, 2};
int evenCount = 0;

for (int i = 0; i < numbers.length; i++) {
    if (numbers[i] % 2 == 0) {
        evenCount++;
    }
}
```

First map indexes to values:

```text
index:   0   1   2
value:   4   7   2
```

Then trace:

| `i` | `numbers[i]` | `numbers[i] % 2 == 0` | `evenCount` |
|---:|---:|---|---:|
| 0 | 4 | true | 1 |
| 1 | 7 | false | 1 |
| 2 | 2 | true | 2 |

Keep the difference visible:

- `i` is the index.
- `numbers[i]` is the value stored at that index.

## Trace `if` / `else`

Code:

```java
if (score >= 60) {
    System.out.println("pass");
} else {
    System.out.println("fail");
}
```

For `score = 60`:

```text
score >= 60
60 >= 60
true
→ execute the if block
→ output: pass
```

Use boundary values such as `59`, `60`, and `61` to verify whether equality belongs in the condition.

## Trace a `while` loop

Code:

```java
int number = 3;
while (number > 0) {
    System.out.println(number);
    number--;
}
```

| Check | `number > 0` | Printed | `number` after `number--` |
|---:|---|---:|---:|
| 1 | true | 3 | 2 |
| 2 | true | 2 | 1 |
| 3 | true | 1 | 0 |
| 4 | false | — | 0 |

Always include the final false condition; it explains why the loop stops.

## Trace a method call

Code:

```java
public static int doubleNumber(int value) {
    int result = value * 2;
    return result;
}

int answer = doubleNumber(4);
```

Trace:

```text
argument 4 is copied into parameter value
value = 4
result = 4 * 2 = 8
return 8
answer = 8
```

Separate the caller's variables from the method's local variables.

## Trace objects and constructors

Code:

```java
Student student = new Student("Mia");
```

Trace:

```text
new Student("Mia")
        ↓
constructor receives name = "Mia"
        ↓
this.name = name
        ↓
object field name becomes "Mia"
        ↓
student refers to that object
```

## Trace recursion

Code:

```java
public static int factorial(int n) {
    if (n == 1) {
        return 1;
    }
    return n * factorial(n - 1);
}
```

Trace calls going down:

```text
factorial(3)
→ 3 * factorial(2)
     → 2 * factorial(1)
          → 1   base case
```

Then trace returns coming up:

```text
factorial(1) returns 1
factorial(2) returns 2 * 1 = 2
factorial(3) returns 3 * 2 = 6
```

Always identify:

- base case;
- smaller subproblem;
- call direction;
- return direction.

## Trace input and output

Record which input operation consumes which value:

```text
input: 5 blue

nextInt() → consumes 5
next()    → consumes "blue"
```

When `nextLine()` is involved, note whether a newline remains after `nextInt()` or `next()`.

## Choose good trace inputs

Use inputs that expose the important behavior:

- A normal case where the condition is true.
- A normal case where the condition is false.
- A boundary case such as exactly 50% or exactly the minimum allowed value.
- A small array with 3–5 elements.
- A recursion input small enough to show every call.

Avoid tracing a 100-element array row by row. Trace a representative small example and summarize the repeated pattern.

## Final explanation template

After tracing, explain:

```text
Initial state → what values exist before execution
Repeated process → what changes each iteration or call
Stopping rule → why the loop or recursion ends
Final state → the values after execution
Requirement link → why that final state answers the problem
```

Tracing is complete only when the learner can connect the variable changes to the program's final result.
