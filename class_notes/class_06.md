# 01. Logical Operators

Logical Operator ব্যবহার করে একাধিক Condition একসাথে যাচাই করা যায়। কোনো Condition True নাকি False, তা নির্ণয় করতে Logical Operator ব্যবহার করা হয়।

C Programming-এ প্রধান Logical Operator তিনটি:

| Operator | Name        | কাজ                                 |            |                                     |
| -------- | ----------- | ----------------------------------- | ---------- | ----------------------------------- |
| `&&`     | Logical AND | সব Condition True হলে True          |            |                                     |
| \`       |             | \`                                  | Logical OR | যেকোনো একটি Condition True হলে True |
| `!`      | Logical NOT | True-কে False এবং False-কে True করে |            |                                     |

C-তে কোনো Expression-এর Result True হলে `1` এবং False হলে `0` পাওয়া যায়।

### A. Logical AND (&&)

Logical AND-এর ক্ষেত্রে সব Condition True হতে হবে। একটি Condition False হলেই পুরো Expression False হবে।

| Condition 1 | Condition 2 | Result |
| ----------- | ----------- | ------ |
| True (1)    | True (1)    | 1      |
| True (1)    | False (0)   | 0      |
| False (0)   | True (1)    | 0      |
| False (0)   | False (0)   | 0      |

**Example:**

```c
#include <stdio.h>

int main()
{
    int a = 10, b = 20;

    printf("%d", a > 5 && b > 10);

    return 0;
}
```

**Output:**

```text
1
```

**ব্যাখ্যা:**

- `a > 5` → True (1)
- `b > 10` → True (1)

দুইটি Condition-ই True হওয়ায় Logical AND-এর Result `1`।

---

### B. Logical OR (||)

Logical OR-এর ক্ষেত্রে যেকোনো একটি Condition True হলেই পুরো Expression True হবে। শুধুমাত্র সব Condition False হলে Result False হবে।

| Condition 1 | Condition 2 | Result |
| ----------- | ----------- | ------ |
| True (1)    | True (1)    | 1      |
| True (1)    | False (0)   | 1      |
| False (0)   | True (1)    | 1      |
| False (0)   | False (0)   | 0      |

**Example:**

```c
#include <stdio.h>

int main()
{
    int a = 10, b = 20;

    printf("%d", a > 15 || b > 10);

    return 0;
}
```

**Output:**

```text
1
```

**ব্যাখ্যা:**

- `a > 15` → False (0)
- `b > 10` → True (1)

যেকোনো একটি Condition True হওয়ায় Logical OR-এর Result `1`।

---

### C. Logical NOT (!)

Logical NOT একটি Condition-এর Result উল্টে দেয়।

| Condition | NOT Result |
| --------- | ---------- |
| True (1)  | False (0)  |
| False (0) | True (1)   |

**Example:**

```c
#include <stdio.h>

int main()
{
    int a = 10;

    printf("%d\n", !(a > 5));
    printf("%d\n", !(a < 5));

    return 0;
}
```

**Output:**

```text
0
1
```

**ব্যাখ্যা:**

- `a > 5` True, তাই `!(a > 5)` False → `0`
- `a < 5` False, তাই `!(a < 5)` True → `1`

---

### Practical Example: Age Eligibility Check

ধরো, একটি পরীক্ষায় অংশগ্রহণ করার জন্য একজন শিক্ষার্থীর Age 18 বা তার বেশি এবং Registration সম্পন্ন থাকতে হবে।

```c
#include <stdio.h>

int main()
{
    int age = 20;
    int registered = 1;

    printf("%d", age >= 18 && registered == 1);

    return 0;
}
```

**Output:**

```text
1
```

এখানে দুইটি Condition-ই True, তাই Eligibility Result True।

### Logical Operator-এর ব্যবহার

- একাধিক Condition একসাথে যাচাই করা।
- Login System-এ Username ও Password উভয়ই সঠিক কি না যাচাই করা।
- Age বা Eligibility Check করা।
- কোনো নির্দিষ্ট Range-এর মধ্যে Value আছে কি না যাচাই করা।

---

# 02. Bitwise Operators

Bitwise Operator সরাসরি Binary Bit-এর উপর কাজ করে।

কম্পিউটার Number-কে Binary System-এ Represent করতে পারে। Binary System-এ শুধুমাত্র দুইটি Digit থাকে:

- `0`
- `1`

Bitwise Operator ব্যবহার করে এই Binary Bit-গুলোকে একে অপরের সাথে তুলনা বা পরিবর্তন করা হয়।

### Bitwise Operators in C

| Operator | Name        | কাজ                          |                                |
| -------- | ----------- | ---------------------------- | ------------------------------ |
| `&`      | Bitwise AND | দুই Bit-ই 1 হলে Result 1     |                                |
| \`       | \`          | Bitwise OR                   | যেকোনো একটি Bit 1 হলে Result 1 |
| `^`      | Bitwise XOR | Bit দুইটি ভিন্ন হলে Result 1 |                                |
| `~`      | Bitwise NOT | প্রতিটি Bit উল্টে দেয়       |                                |
| `<<`     | Left Shift  | Bit বাম দিকে সরায়           |                                |
| `>>`     | Right Shift | Bit ডান দিকে সরায়           |                                |

## Binary Number বোঝা

Decimal Number এবং Binary Number-এর কিছু উদাহরণ:

| Decimal | Binary (8-bit) |
| ------- | -------------- |
| 1       | `00000001`     |
| 2       | `00000010`     |
| 3       | `00000011`     |
| 5       | `00000101`     |
| 10      | `00001010`     |
| 15      | `00001111`     |

উদাহরণস্বরূপ, Decimal `5` এর Binary হলো `00000101`।

---

### A. Bitwise AND (&)

Bitwise AND-এ দুটি Bit-ই `1` হলে Result `1` হয়। অন্য সব ক্ষেত্রে Result `0`।

| Bit 1 | Bit 2 | Result |
| ----- | ----- | ------ |
| 0     | 0     | 0      |
| 0     | 1     | 0      |
| 1     | 0     | 0      |
| 1     | 1     | 1      |

**Example: 5 & 3**

```text
  00000101   (5)
& 00000011   (3)
-----------
  00000001   (1)
```

**C Program:**

```c
#include <stdio.h>

int main()
{
    int a = 5, b = 3;

    printf("%d", a & b);

    return 0;
}
```

**Output:**

```text
1
```

---

### B. Bitwise OR (|)

Bitwise OR-এ যেকোনো একটি Bit `1` হলে Result `1` হয়। শুধুমাত্র দুইটি Bit-ই `0` হলে Result `0`।

| Bit 1 | Bit 2 | Result |
| ----- | ----- | ------ |
| 0     | 0     | 0      |
| 0     | 1     | 1      |
| 1     | 0     | 1      |
| 1     | 1     | 1      |

**Example: 5 | 3**

```text
  00000101   (5)
| 00000011   (3)
-----------
  00000111   (7)
```

**C Program:**

```c
#include <stdio.h>

int main()
{
    int a = 5, b = 3;

    printf("%d", a | b);

    return 0;
}
```

**Output:**

```text
7
```

---

### C. Bitwise XOR (^)

XOR (Exclusive OR) Operator-এ দুইটি Bit ভিন্ন হলে Result `1` হয় এবং একই হলে Result `0` হয়।

| Bit 1 | Bit 2 | Result |
| ----- | ----- | ------ |
| 0     | 0     | 0      |
| 0     | 1     | 1      |
| 1     | 0     | 1      |
| 1     | 1     | 0      |

**Example: 5 ^ 3**

```text
  00000101   (5)
^ 00000011   (3)
-----------
  00000110   (6)
```

**C Program:**

```c
#include <stdio.h>

int main()
{
    int a = 5, b = 3;

    printf("%d", a ^ b);

    return 0;
}
```

**Output:**

```text
6
```

---

### D. Bitwise NOT (\~)

Bitwise NOT প্রতিটি Binary Bit উল্টে দেয়।

- `0` → `1`
- `1` → `0`

**Example:**

```text
  00000101   (5)
~ -----------
  11111010
```

**C Program:**

```c
#include <stdio.h>

int main()
{
    int a = 5;

    printf("%d", ~a);

    return 0;
}
```

**Output (সাধারণ 32-bit int সিস্টেমে):**

```text
-6
```

**কেন -6 আসে?**

Bitwise NOT সব Bit উল্টে দেয়। সাধারণ আধুনিক সিস্টেমে Signed Integer Two's Complement পদ্ধতিতে Represent করা হয়, তাই `~5` এর Result `-6` হয়।

এটি একটি গুরুত্বপূর্ণ বিষয়: Bitwise NOT শুধু Binary Bit উল্টায়, কিন্তু Signed Integer হিসেবে সেই Bit-এর Value Negative হতে পারে।

---

### E. Left Shift (<<)

Left Shift Operator Binary Bit-গুলোকে নির্দিষ্ট সংখ্যক Position বাম দিকে সরিয়ে দেয়।

**Example: 5 << 1**

```text
00000101   (5)
Left Shift by 1
00001010   (10)
```

**C Program:**

```c
#include <stdio.h>

int main()
{
    int a = 5;

    printf("%d", a << 1);

    return 0;
}
```

**Output:**

```text
10
```

Positive Integer-এর ক্ষেত্রে উপযুক্ত Range-এর মধ্যে Left Shift করলে এটি সাধারণত 2 দিয়ে গুণ করার সমতুল্য।

`5 << 1` → `5 × 2 = 10`

`5 << 2` → `5 × 4 = 20`

---

### F. Right Shift (>>)

Right Shift Operator Binary Bit-গুলোকে নির্দিষ্ট সংখ্যক Position ডান দিকে সরিয়ে দেয়।

**Example: 10 >> 1**

```text
00001010   (10)
Right Shift by 1
00000101   (5)
```

**C Program:**

```c
#include <stdio.h>

int main()
{
    int a = 10;

    printf("%d", a >> 1);

    return 0;
}
```

**Output:**

```text
5
```

Positive Integer-এর ক্ষেত্রে উপযুক্ত Range-এর মধ্যে Right Shift করলে এটি সাধারণত 2 দিয়ে Integer Division করার মতো Result দেয়।

`10 >> 1` → `10 / 2 = 5`

`10 >> 2` → `10 / 4 = 2`

\<text color="secondary" size="sm">Note: Shift Operation-এর ক্ষেত্রে Signed ও Unsigned Integer এবং Bit-এর সীমা অনুযায়ী কিছু নিয়ম রয়েছে। আপাতত Positive Integer-এর Basic Shift Operation বোঝাই আমাদের উদ্দেশ্য।\</text>

---

## 03. Logical Operators vs Bitwise Operators

Logical Operator এবং Bitwise Operator দেখতে কিছুটা একই রকম হলেও তাদের কাজ আলাদা।

| Logical Operator        | Bitwise Operator                             |    |    |    |
| ----------------------- | -------------------------------------------- | -- | -- | -- |
| `&&`                    | `&`                                          |    |    |    |
| \`                      |                                              | \` | \` | \` |
| `!`                     | `~`                                          |    |    |    |
| Condition যাচাই করে     | Binary Bit-এর উপর কাজ করে                    |    |    |    |
| Result সাধারণত 0 অথবা 1 | Result-এর Bit Pattern অনুযায়ী Integer Value |    |    |    |

### Example

```c
int a = 5, b = 3;

printf("%d", a && b);
```

Output:

```text
1
```

এখানে Logical AND দুইটি Non-zero Value-কে True হিসেবে বিবেচনা করে।

কিন্তু:

```c
int a = 5, b = 3;

printf("%d", a & b);
```

Output:

```text
1
```

এখানে Bitwise AND Binary Bit-এর উপর কাজ করে।

দুইটি Example-এর Output একই হলেও কাজ করার পদ্ধতি আলাদা।

**মনে রাখবে:**

- `&&` → Logical AND
- `&` → Bitwise AND

একটি অতিরিক্ত `&` বা `|` ভুল Operator নির্বাচন করলে Program-এর Result পরিবর্তন হয়ে যেতে পারে।

---

# 04. Assignment Operators

Assignment Operator ব্যবহার করে Variable-এর মধ্যে Value Assign করা হয়।

আমরা আগের ক্লাসে সাধারণ Assignment Operator `=` শিখেছি।

```c
int a = 10;
```

এখানে `10` Value-টি `a` Variable-এর মধ্যে Assign করা হয়েছে।

C Programming-এ Compound Assignment Operator ব্যবহার করে Calculation এবং Assignment একসাথে করা যায়।

### Assignment Operators List

| Operator | Example   | Equivalent      |       |         |     |
| -------- | --------- | --------------- | ----- | ------- | --- |
| `=`      | `a = 5`   | `a`-তে 5 Assign |       |         |     |
| `+=`     | `a += 5`  | `a = a + 5`     |       |         |     |
| `-=`     | `a -= 5`  | `a = a - 5`     |       |         |     |
| `*=`     | `a *= 5`  | `a = a * 5`     |       |         |     |
| `/=`     | `a /= 5`  | `a = a / 5`     |       |         |     |
| `%=`     | `a %= 5`  | `a = a % 5`     |       |         |     |
| `&=`     | `a &= 5`  | `a = a & 5`     |       |         |     |
| \`       | =\`       | \`a             | = 5\` | \`a = a | 5\` |
| `^=`     | `a ^= 5`  | `a = a ^ 5`     |       |         |     |
| `<<=`    | `a <<= 1` | `a = a << 1`    |       |         |     |
| `>>=`    | `a >>= 1` | `a = a >> 1`    |       |         |     |

### A. Addition Assignment (+=)

```c
int a = 10;

a += 5;

printf("%d", a);
```

**Output:**

```text
15
```

এটি:

```c
a = a + 5;
```

এর সমতুল্য।

### B. Subtraction Assignment (-=)

```c
int a = 10;

a -= 3;

printf("%d", a);
```

**Output:**

```text
7
```

### C. Multiplication Assignment (\*=)

```c
int a = 5;

a *= 3;

printf("%d", a);
```

**Output:**

```text
15
```

### D. Division Assignment (/=)

```c
int a = 20;

a /= 4;

printf("%d", a);
```

**Output:**

```text
5
```

### E. Modulus Assignment (%=)

```c
int a = 17;

a %= 5;

printf("%d", a);
```

**Output:**

```text
2
```

### Practical Example: Value Update

```c
#include <stdio.h>

int main()
{
    int balance = 1000;

    balance += 500;
    balance -= 200;
    balance *= 2;

    printf("Final Balance = %d", balance);

    return 0;
}
```

**Calculation:**

- Initial Balance = 1000
- `balance += 500` → 1500
- `balance -= 200` → 1300
- `balance *= 2` → 2600

**Output:**

```text
Final Balance = 2600
```

---

# 05. Ternary Operator (Conditional Operator)

Ternary Operator হলো একটি Conditional Operator, যা একটি Condition যাচাই করে দুইটি Value-এর মধ্যে একটি Value নির্বাচন করে।

এটি `if-else` এর একটি সংক্ষিপ্ত রূপ হিসেবে ব্যবহার করা যায়, যখন একটি Condition-এর উপর ভিত্তি করে দুইটি Expression-এর মধ্যে একটি নির্বাচন করতে হয়।

Ternary Operator-এ মোট তিনটি অংশ থাকে:

1. Condition
2. True হলে কোন Value হবে
3. False হলে কোন Value হবে

### Syntax

```c
condition ? expression1 : expression2;
```

**কাজের নিয়ম:**

- Condition True হলে `expression1` Execute হবে।
- Condition False হলে `expression2` Execute হবে।

### Example 1: Even or Odd

```c
#include <stdio.h>

int main()
{
    int number = 10;

    number % 2 == 0 ? printf("Even") : printf("Odd");

    return 0;
}
```

**Output:**

```text
Even
```

**ব্যাখ্যা:**

- `number % 2 == 0` Condition Check করা হচ্ছে।
- 10 কে 2 দিয়ে ভাগ করলে ভাগশেষ 0।
- Condition True হওয়ায় `Even` Print হবে।

### Example 2: Find the Larger Number

```c
#include <stdio.h>

int main()
{
    int a = 10, b = 20;

    int max = (a > b) ? a : b;

    printf("Maximum = %d", max);

    return 0;
}
```

**Output:**

```text
Maximum = 20
```

**ব্যাখ্যা:**

- `a > b` → False
- তাই `:` এর পরে থাকা `b` Value নির্বাচন হবে।
- `max` এর Value হবে 20।

### Example 3: User Input দিয়ে Positive or Negative

```c
#include <stdio.h>

int main()
{
    int number;

    printf("Enter a number: ");
    scanf("%d", &number);

    number >= 0 ? printf("Non-negative") : printf("Negative");

    return 0;
}
```

**Input:**

```text
-5
```

**Output:**

```text
Negative
```

---

# 06. Quick Revision

| Operator Type             | Operator | কাজ                               |                         |                                   |
| ------------------------- | -------- | --------------------------------- | ----------------------- | --------------------------------- |
| Logical AND               | `&&`     | সব Condition True হতে হবে         |                         |                                   |
| Logical OR                | \`       |                                   | \`                      | অন্তত একটি Condition True হতে হবে |
| Logical NOT               | `!`      | Condition-এর Result উল্টে দেয়    |                         |                                   |
| Bitwise AND               | `&`      | দুই Bit-ই 1 হলে 1                 |                         |                                   |
| Bitwise OR                | \`       | \`                                | যেকোনো একটি Bit 1 হলে 1 |                                   |
| Bitwise XOR               | `^`      | Bit ভিন্ন হলে 1                   |                         |                                   |
| Bitwise NOT               | `~`      | Bit উল্টে দেয়                    |                         |                                   |
| Left Shift                | `<<`     | Bit বাম দিকে সরায়                |                         |                                   |
| Right Shift               | `>>`     | Bit ডান দিকে সরায়                |                         |                                   |
| Assignment                | `=`      | Value Assign                      |                         |                                   |
| Addition Assignment       | `+=`     | যোগ করে Assign                    |                         |                                   |
| Subtraction Assignment    | `-=`     | বিয়োগ করে Assign                 |                         |                                   |
| Multiplication Assignment | `*=`     | গুণ করে Assign                    |                         |                                   |
| Division Assignment       | `/=`     | ভাগ করে Assign                    |                         |                                   |
| Modulus Assignment        | `%=`     | ভাগশেষ Assign                     |                         |                                   |
| Ternary                   | `?:`     | Condition অনুযায়ী Value নির্বাচন |                         |                                   |

---

# 07. Practice Questions

### Part A: Logical Operators

1. Logical Operator কী? কয়টি Logical Operator রয়েছে?
2. Logical AND এবং Logical OR-এর মধ্যে পার্থক্য কী?
3. Logical NOT কীভাবে কাজ করে?
4. `10 > 5 && 5 < 2` এর Result কত?
5. `10 > 5 || 5 < 2` এর Result কত?
6. `!(10 == 10)` এর Result কত?

### Part B: Bitwise Operators

1. Bitwise Operator কী?
2. Binary Number কী?
3. `5 & 3` এর Result কত?
4. `5 | 3` এর Result কত?
5. `5 ^ 3` এর Result কত?
6. `5 << 1` এর Result কত?
7. `10 >> 1` এর Result কত?
8. Logical AND `&&` এবং Bitwise AND `&` এর পার্থক্য লেখো।

### Part C: Assignment Operators

1. `a += 5` কোন Statement-এর সমতুল্য?
2. `a -= 3` এর কাজ কী?
3. `a *= 2` এর কাজ কী?
4. `a /= 5` এর কাজ কী?
5. `a %= 3` এর কাজ কী?

### Part D: Ternary Operator

1. Ternary Operator কী?
2. Ternary Operator-এর Syntax লেখো।
3. Ternary Operator ব্যবহার করে Even অথবা Odd নির্ণয় করো।
4. Ternary Operator ব্যবহার করে দুটি সংখ্যা থেকে বড় সংখ্যাটি বের করো।
5. Ternary Operator ব্যবহার করে একটি সংখ্যা Positive অথবা Negative নির্ণয় করো।


