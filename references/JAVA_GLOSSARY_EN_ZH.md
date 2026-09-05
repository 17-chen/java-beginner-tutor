# Java English–Chinese Beginner Glossary

Use this glossary to preserve the English terminology used by instructors while explaining each term in clear Chinese. Do not translate Java keywords inside code.

## Program structure

| English term | 中文解释 | Beginner meaning |
|---|---|---|
| program | 程序 | A set of instructions executed by the computer. |
| source code | 源代码 | The Java code written by the programmer. |
| statement | 语句 | One instruction in a program, commonly ending with `;`. |
| block | 代码块 | Statements grouped inside `{ }`. |
| class | 类 | A blueprint that describes data and behavior. |
| object / instance | 对象 / 实例 | A concrete value created from a class with `new`. |
| main method | 主方法 | The usual starting point of a Java application. |
| data field / instance variable | 数据字段 / 实例变量 | A variable stored inside an object. |
| local variable | 局部变量 | A variable declared inside a method or block. |
| scope | 作用域 | The part of the program where a name can be used. |

## Values and types

| English term | 中文解释 | Beginner meaning |
|---|---|---|
| variable | 变量 | A named place used to store a value. |
| data type | 数据类型 | Describes what kind of value a variable can hold. |
| primitive type | 基本数据类型 | A built-in simple type such as `int`, `double`, or `boolean`. |
| integer | 整数 | A whole number with no decimal part. |
| floating-point number | 浮点数 | A number that can contain a decimal part. |
| boolean | 布尔值 | A value that is either `true` or `false`. |
| character | 字符 | One character stored with `char`, such as `'A'`. |
| String | 字符串 | Text such as `"hello"`; `String` is a class. |
| declaration | 声明 | Introduces a variable and its type: `int age;`. |
| initialization | 初始化 | Gives a variable its first value: `int age = 18;`. |
| assignment | 赋值 | Stores or replaces a value using `=`. |
| constant | 常量 | A value intended not to change, often declared with `final`. |
| cast / type casting | 类型转换 | Converts a value from one type to another. |

## Conditions and loops

| English term | 中文解释 | Beginner meaning |
|---|---|---|
| condition | 条件 | An expression that becomes `true` or `false`. |
| comparison operator | 比较运算符 | Operators such as `==`, `!=`, `<`, and `>=`. |
| logical operator | 逻辑运算符 | Combines or reverses conditions with `&&`, `||`, or `!`. |
| branch / selection | 分支 / 选择结构 | Chooses which code runs, commonly with `if`/`else`. |
| loop / iteration | 循环 / 迭代 | Repeats code while a condition allows it. |
| for loop | `for` 循环 | A loop often used when the number of repetitions is known. |
| while loop | `while` 循环 | A loop that repeats while its condition is true. |
| loop variable | 循环变量 | A variable such as `i` that changes each iteration. |
| iteration | 一轮循环 | One complete execution of a loop body. |
| counter | 计数器 | A variable that counts events, often updated with `++`. |
| accumulator | 累加器 | A variable that builds a total, such as `sum += value`. |
| infinite loop | 无限循环 | A loop whose stopping condition is never reached. |

## Arrays and strings

| English term | 中文解释 | Beginner meaning |
|---|---|---|
| array | 数组 | A fixed-size group of values with the same type. |
| element | 元素 | One value stored in an array. |
| index | 下标 / 索引 | The position of an element; Java indexes begin at `0`. |
| length | 长度 | Number of elements in an array; use `array.length`. |
| traverse | 遍历 | Visit each element, usually with a loop. |
| populate an array | 填充数组 | Put values into the array's positions. |
| substring | 子字符串 | A smaller piece of a string. |
| concatenate | 拼接 | Join strings with `+` or another string method. |
| compare strings | 比较字符串 | Normally compare content with `.equals()`. |

## Methods and object-oriented programming

| English term | 中文解释 | Beginner meaning |
|---|---|---|
| method | 方法 | A named block of code that performs a task. |
| parameter | 参数（形参） | A variable listed in a method definition. |
| argument | 参数值（实参） | The actual value passed when calling a method. |
| return value | 返回值 | The result sent back by a method. |
| return type | 返回类型 | The type of result a method returns; `void` means no returned value. |
| method call | 方法调用 | Runs a method, such as `object.printResult()`. |
| constructor | 构造器 | Special code used to initialize an object when `new` is used. |
| getter / accessor | 获取方法 | Returns a field's value. |
| setter / mutator | 设置方法 | Changes a field's value. |
| encapsulation | 封装 | Keeps fields controlled through a class's methods. |
| inheritance | 继承 | Creates a new class based on another class. |
| this | 当前对象 | Refers to the object whose method or constructor is running. |
| static | 属于类本身 | Belongs to the class rather than one individual object. |

## Input, output, and errors

| English term | 中文解释 | Beginner meaning |
|---|---|---|
| input | 输入 | Data supplied to a program. |
| output | 输出 | Information produced by a program. |
| Scanner | 输入读取工具 | A Java class commonly used to read keyboard input. |
| compile | 编译 | Check and translate Java source code before execution. |
| compile error | 编译错误 | An error that prevents the program from compiling. |
| runtime error / exception | 运行时错误 / 异常 | A failure that occurs while the program is running. |
| logic error | 逻辑错误 | The program runs but produces the wrong result. |
| debugging | 调试 | Finding, understanding, and fixing errors. |
| test case | 测试用例 | A chosen input and expected result used to check a program. |
| edge case | 边界情况 | An unusual or limiting input such as an empty array. |
| code tracing | 代码追踪 | Following execution step by step while recording state changes. |

## Common assignment phrases

| Assignment wording | 中文意思 |
|---|---|
| at least | 至少；大于或等于 |
| at most | 至多；小于或等于 |
| greater than | 大于，不包含相等 |
| less than | 小于，不包含相等 |
| prompt the user | 提示用户输入 |
| read user input | 读取用户输入 |
| display / print the result | 显示 / 输出结果 |
| initialize the object | 初始化对象 |
| return the value | 返回这个值 |
| iterate through the array | 遍历数组 |
| determine whether | 判断是否 |
| calculate the total | 计算总和 |
| count the occurrences | 统计出现次数 |
| write a method that | 编写一个方法来…… |
| create an instance of | 创建……的一个对象 / 实例 |

## Distinctions learners often confuse

- `=` assigns a value; `==` compares primitive values.
- `.equals()` normally compares `String` content; `==` compares whether references point to the same object.
- A parameter appears in the method definition; an argument is supplied at the call site.
- `array.length` is a field; `text.length()` is a method.
- A class is the blueprint; an object is a concrete instance of that class.
- A compile error prevents execution; a runtime error happens during execution; a logic error produces an incorrect result.
