# Class 06: Variable Scope, ASCII, Relational Operators & Temperature Conversion

---

## 01. Variable Scope (Local & Global Variables)

Variable Scope বলতে বোঝায়, একটি Variable প্রোগ্রামের কোন অংশ থেকে Access বা ব্যবহার করা যাবে।

C Programming-এ Variable কোথায় Declare করা হয়েছে তার উপর নির্ভর করে সেটি Local অথবা Global হতে পারে।

### A. Local Variable

যে Variable কোনো Function বা নির্দিষ্ট Block-এর ভিতরে Declare করা হয়, তাকে **Local Variable** বলে।

- এটি শুধুমাত্র যে Block-এর ভিতরে Declare করা হয়েছে, সেই Block-এর মধ্যেই ব্যবহার করা যায়।
- Block-এর বাইরে এটি Access করা যায় না।
- Block শেষ হলে এর Lifetime শেষ হয়।

**Example:**

```c
#include <stdio.h>

int main()
{
    int a = 10;

    printf("%d", a);

    return 0;
}
```

**Output:**

```text
10
```

এখানে `a` Variable-টি `main()`-এর ভিতরে Declare করা হয়েছে। তাই এটি `main()`-এর Local Variable।

### Local Variable-এর Scope Example

```c
#include <stdio.h>

int main()
{
    int a = 10;

    {
        int b = 20;
        printf("B = %d\n", b);
    }

    printf("A = %d\n", a);

    return 0;
}
```

**Output:**

```text
B = 20
A = 10
```

এখানে `b` একটি Inner Block-এর Local Variable। এটি ওই Block-এর ভিতরে ব্যবহার করা যায়, কিন্তু Block-এর বাইরে ব্যবহার করা যাবে না।

### B. Global Variable

যে Variable কোনো Function-এর বাইরে Declare করা হয়, তাকে **Global Variable** বলে।

- এটি Function-এর বাইরে Declare করা হয়।
- একই Source File-এর মধ্যে Declaration-এর পর থেকে উপযুক্ত Scope-এ বিভিন্ন Function থেকে ব্যবহার করা যায়।
- কোনো Function-এর Local Variable না থাকলে Global Variable ব্যবহার করা সম্ভব।

**Example:**

```c
#include <stdio.h>

int a = 100;

int main()
{
    printf("%d", a);

    return 0;
}
```

**Output:**

```text
100
```

এখানে `a` Variable-টি `main()`-এর বাইরে Declare করা হয়েছে। তাই এটি Global Variable।

### Local vs Global Variable

| বিষয়          | Local Variable                                | Global Variable                      |
| ------------- | --------------------------------------------- | ------------------------------------ |
| Declaration   | Function/Block-এর ভিতরে                       | Function-এর বাইরে                    |
| Scope         | নির্দিষ্ট Block                               | Declaration-এর পর উপযুক্ত File Scope |
| Access        | নির্দিষ্ট Block-এর ভিতরে                      | একাধিক Function থেকে                 |
| Lifetime      | Block-এর Execution চলাকালীন                   | পুরো Program-এর Execution চলাকালীন   |
| Default Value | Uninitialized হলে Garbage/Indeterminate Value | স্বয়ংক্রিয়ভাবে 0 হয়               |

> **মনে রাখবে:** Local Variable-এর Value Initialize না করলে সেটিকে ব্যবহার করা নিরাপদ নয়। Global Variable স্বয়ংক্রিয়ভাবে Zero Initialize হয়।

---

## 02. Arithmetic Operations with Characters

C Programming-এ `char` Data Type ব্যবহার করে Character সংরক্ষণ করা হয়।

প্রতিটি Character-এর একটি নির্দিষ্ট Numeric Code থাকে। এই Code-কে Character Encoding বলা হয়। ASCII Encoding-এ English Letters, Digits এবং বিভিন্ন Symbol-এর জন্য নির্দিষ্ট Numeric Value রয়েছে।

তাই Character-এর উপর Arithmetic Operation করা সম্ভব।

### Character-এর সাথে Addition

```c
#include <stdio.h>

int main()
{
    char ch = 'A';

    printf("%c\n", ch);
    printf("%c\n", ch + 1);
    printf("%c\n", ch + 2);

    return 0;
}
```

**Output:**

```text
A
B
C
```

### কীভাবে কাজ করে?

ASCII অনুযায়ী:

- `'A'` এর Value = 65
- `'B'` এর Value = 66
- `'C'` এর Value = 67

তাই:

- `'A' + 1` → 66 → `'B'`
- `'A' + 2` → 67 → `'C'`

অর্থাৎ, Character-এর সাথে 1 যোগ করলে তার পরবর্তী ASCII Value-তে যাওয়া হয়।

### Character-এর সাথে Subtraction

```c
#include <stdio.h>

int main()
{
    char ch = 'D';

    printf("%c\n", ch);
    printf("%c\n", ch - 1);
    printf("%c\n", ch - 2);

    return 0;
}
```

**Output:**

```text
D
C
B
```

এখানে `'D'` থেকে 1 বিয়োগ করলে `'C'` এবং 2 বিয়োগ করলে `'B'` পাওয়া যায়।

### Character-এর Numeric Value দেখা

```c
#include <stdio.h>

int main()
{
    char ch = 'A';

    printf("%d", ch);

    return 0;
}
```

**Output:**

```text
65
```

এখানে `%d` ব্যবহার করার কারণে Character-এর Numeric Value Print হয়েছে।

---

## 03. ASCII Code

ASCII-এর পূর্ণরূপ হলো **American Standard Code for Information Interchange**।

ASCII হলো একটি Character Encoding Standard, যার মাধ্যমে বিভিন্ন Character-কে Numeric Value দিয়ে Represent করা হয়।

কম্পিউটার মূলত Numeric Data নিয়ে কাজ করে। ASCII-এর মাধ্যমে English Letter, Digit এবং বিভিন্ন Symbol-কে নির্দিষ্ট Number-এর সাথে যুক্ত করা হয়।

### কিছু গুরুত্বপূর্ণ ASCII Value

| Character | ASCII Value |
| --------- | ----------: |
| `A`       |          65 |
| `B`       |          66 |
| `C`       |          67 |
| `Z`       |          90 |
| `a`       |          97 |
| `b`       |          98 |
| `z`       |         122 |
| `0`       |          48 |
| `1`       |          49 |
| `9`       |          57 |
| Space     |          32 |

### Uppercase ও Lowercase-এর পার্থক্য

ASCII-তে Uppercase এবং Lowercase Letter-এর Numeric Value আলাদা।

উদাহরণ:

- `A` = 65
- `a` = 97

তাই:

```c
'a' - 'A' = 32
```

### Practical Example: Character থেকে ASCII

```c
#include <stdio.h>

int main()
{
    char ch;

    printf("Enter a character: ");
    scanf("%c", &ch);

    printf("ASCII Value = %d", ch);

    return 0;
}
```

**Input:**

```text
A
```

**Output:**

```text
ASCII Value = 65
```

---

## 04. Relational Operators

Relational Operator ব্যবহার করে দুটি Value-এর মধ্যে সম্পর্ক বা তুলনা করা হয়।

যেমন:

- একটি সংখ্যা অন্য সংখ্যার চেয়ে বড় কি না?
- দুটি সংখ্যা সমান কি না?
- একটি সংখ্যা অন্য সংখ্যার চেয়ে ছোট বা সমান কি না?

Relational Operation-এর Result হয়:

- `1` → True (সত্য)
- `0` → False (মিথ্যা)

### Relational Operators in C

| Operator | Meaning               | Example    |
| -------- | --------------------- | ---------- |
| `>`      | Greater than (বড়)    | `10 > 5`   |
| `<`      | Less than (ছোট)       | `5 < 10`   |
| `>=`     | Greater than or equal | `10 >= 10` |
| `<=`     | Less than or equal    | `5 <= 10`  |
| `==`     | Equal to (সমান)       | `5 == 5`   |
| `!=`     | Not equal to (অসমান)  | `5 != 10`  |

### Example 1

```c
#include <stdio.h>

int main()
{
    int a = 10, b = 5;

    printf("%d\n", a > b);
    printf("%d\n", a < b);
    printf("%d\n", a == b);
    printf("%d\n", a != b);

    return 0;
}
```

**Output:**

```text
1
0
0
1
```

### ব্যাখ্যা

| Expression | Result | কারণ              |
| ---------- | -----: | ----------------- |
| `10 > 5`   |      1 | 10 বড় 5 থেকে     |
| `10 < 5`   |      0 | 10 ছোট নয় 5 থেকে |
| `10 == 5`  |      0 | দুইটি সমান নয়    |
| `10 != 5`  |      1 | দুইটি অসমান       |

### Example 2: User Input দিয়ে Comparison

```c
#include <stdio.h>

int main()
{
    int a, b;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    printf("a > b = %d\n", a > b);
    printf("a < b = %d\n", a < b);
    printf("a == b = %d\n", a == b);

    return 0;
}
```

**Input:**

```text
10 20
```

**Output:**

```text
a > b = 0
a < b = 1
a == b = 0
```

### Important: `=` এবং `==` এর পার্থক্য

এটি C Programming-এর একটি খুব গুরুত্বপূর্ণ বিষয়।

| Operator | কাজ                                                   |
| -------- | ----------------------------------------------------- |
| `=`      | Assignment Operator – Value Assign করে                |
| `==`     | Relational Operator – দুটি Value সমান কি না Check করে |

Example:

```c
a = 10;
```

এখানে `a` এর মধ্যে 10 Assign করা হয়েছে।

```c
a == 10
```

এখানে Check করা হচ্ছে `a` এর Value 10 কি না।

---

## 05. Practical Problem Solving: Celsius to Fahrenheit

Temperature এক Unit থেকে অন্য Unit-এ Convert করা একটি গুরুত্বপূর্ণ Mathematical Problem।

আমরা জানি:

- Celsius (°C)
- Fahrenheit (°F)

দুটি ভিন্ন Temperature Scale।

### Conversion Formula

Celsius থেকে Fahrenheit-এ Convert করার Formula:

[
F = \frac{9}{5} \times C + 32
]

এখানে:

- `C` = Temperature in Celsius
- `F` = Temperature in Fahrenheit

### C Program

```c
#include <stdio.h>

int main()
{
    float celsius, fahrenheit;

    printf("Enter temperature in Celsius: ");
    scanf("%f", &celsius);

    fahrenheit = (celsius * 9.0 / 5.0) + 32.0;

    printf("Temperature in Fahrenheit = %.2f\n", fahrenheit);

    return 0;
}
```

**Input:**

```text
37
```

**Output:**

```text
Temperature in Fahrenheit = 98.60
```

### Step-by-Step Calculation

ধরা যাক, Celsius = 37

Formula:

[
F = \frac{9}{5} \times 37 + 32
]

প্রথমে:

[
37 \times 9 = 333
]

তারপর:

[
333 \div 5 = 66.6
]

শেষে:

[
66.6 + 32 = 98.6
]

তাই Fahrenheit Temperature হবে **98.60°F**।

---

## 06. Practical Problem Solving: Fahrenheit to Celsius

এবার Fahrenheit থেকে Celsius-এ Convert করব।

### Conversion Formula

[
C = \frac{5}{9} \times (F - 32)
]

এখানে:

- `F` = Temperature in Fahrenheit
- `C` = Temperature in Celsius

### C Program

```c
#include <stdio.h>

int main()
{
    float fahrenheit, celsius;

    printf("Enter temperature in Fahrenheit: ");
    scanf("%f", &fahrenheit);

    celsius = (fahrenheit - 32.0) * 5.0 / 9.0;

    printf("Temperature in Celsius = %.2f\n", celsius);

    return 0;
}
```

**Input:**

```text
98.6
```

**Output:**

```text
Temperature in Celsius = 37.00
```

### Step-by-Step Calculation

ধরা যাক, Fahrenheit = 98.6

Formula:

[
C = \frac{5}{9} \times (98.6 - 32)
]

প্রথমে:

[
98.6 - 32 = 66.6
]

তারপর:

[
66.6 \times 5 = 333
]

শেষে:

[
333 \div 9 = 37
]

তাই Celsius Temperature হবে **37°C**।

---

## 07. Quick Revision

| Topic                 | Key Point                                 |
| --------------------- | ----------------------------------------- |
| Local Variable        | নির্দিষ্ট Block-এর ভিতরে ব্যবহার করা যায় |
| Global Variable       | Function-এর বাইরে Declare করা হয়         |
| ASCII                 | Character-এর Numeric Representation       |
| `char + 1`            | পরবর্তী Numeric Character Code            |
| `char - 1`            | আগের Numeric Character Code               |
| `>`                   | বড় কি না Check                           |
| `<`                   | ছোট কি না Check                           |
| `>=`                  | বড় অথবা সমান                             |
| `<=`                  | ছোট অথবা সমান                             |
| `==`                  | সমান কি না                                |
| `!=`                  | অসমান কি না                               |
| True                  | 1                                         |
| False                 | 0                                         |
| `=`                   | Value Assign                              |
| `==`                  | Equality Check                            |
| Celsius to Fahrenheit | `C × 9 / 5 + 32`                          |
| Fahrenheit to Celsius | `(F - 32) × 5 / 9`                        |

---

## 08. Practice Questions

### Part A: Basic Questions

1. Variable Scope কী?
2. Local Variable এবং Global Variable-এর মধ্যে পার্থক্য লেখো।
3. ASCII Code কী?
4. ASCII অনুযায়ী `'A'` এবং `'a'` এর Value কত?
5. Relational Operator কী?
6. Relational Expression-এর Result True হলে C-তে কী Value পাওয়া যায়?
7. `=` এবং `==` এর মধ্যে পার্থক্য কী?

### Part B: Output Prediction

**Question 1**

```c
char ch = 'A';
printf("%c", ch + 2);
```

**Question 2**

```c
char ch = 'D';
printf("%d", ch);
```

**Question 3**

```c
int a = 10, b = 20;
printf("%d", a < b);
```

**Question 4**

```c
int a = 10, b = 10;
printf("%d", a != b);
```

### Part C: Programming Practice

1. একটি Character Input নিয়ে তার ASCII Value Print করো।
2. একটি Character Input নিয়ে তার পরবর্তী Character Print করো।
3. দুটি Integer Input নিয়ে কোনটি বড় তা Relational Operator ব্যবহার করে Check করো।
4. Celsius Temperature Input নিয়ে Fahrenheit-এ Convert করো।
5. Fahrenheit Temperature Input নিয়ে Celsius-এ Convert করো।

---

