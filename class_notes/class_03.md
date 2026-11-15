# ১. Variable কী? (What is a Variable?)

Variable হলো কম্পিউটারের Memory-তে Data সংরক্ষণ করার জন্য ব্যবহৃত একটি Named Storage Location।

সহজ ভাষায়, Variable-কে একটি Container বা পাত্রের সঙ্গে তুলনা করা যায়। যেমন একটি পাত্রের মধ্যে আমরা পানি বা অন্য কিছু রাখতে পারি, তেমনি Variable-এর মধ্যে আমরা বিভিন্ন ধরনের Data সংরক্ষণ করতে পারি।

**উদাহরণ:** একজন শিক্ষার্থীর বয়স, নামের প্রথম অক্ষর, পরীক্ষার নম্বর ইত্যাদি Variable-এর মাধ্যমে সংরক্ষণ করা যায়।

```c
int age = 21;
float marks = 85.5;
char grade = 'A';
```

এখানে:
- `age` Variable-এর মধ্যে 21 সংরক্ষিত আছে।
- `marks` Variable-এর মধ্যে 85.5 সংরক্ষিত আছে।
- `grade` Variable-এর মধ্যে A সংরক্ষিত আছে।

**মনে রাখবে:** Variable-এর Value প্রোগ্রাম চলাকালীন পরিবর্তন করা যায়।

---

# ২. Variable Declaration ও Initialization

C Programming-এ Variable ব্যবহার করার আগে সাধারণত সেটিকে Declare করতে হয়।

### ১. Variable Declaration

Variable Declaration হলো একটি Variable তৈরি করার জন্য তার Data Type এবং নাম নির্ধারণ করা।

**Syntax:**

```c
data_type variable_name;
```

**উদাহরণ:**

```c
int age;
float marks;
char grade;
```

এখানে আমরা তিনটি Variable Declare করেছি।

### ২. Variable Initialization

Variable তৈরি করার সময়ই অথবা তৈরি করার পরে প্রথমবার কোনো Value প্রদান করাকে Initialization বলা হয়।

**উদাহরণ:**

```c
int age = 21;
float marks = 85.5;
char grade = 'A';
```

এখানে Variable তৈরি করার সময়ই Value দেওয়া হয়েছে।

### Declaration এবং Initialization-এর পার্থক্য

**Declaration:**

```c
int age;
```

এখানে শুধু Variable তৈরি করা হয়েছে।

**Initialization:**

```c
int age = 21;
```

এখানে Variable তৈরি করার পাশাপাশি Value-ও দেওয়া হয়েছে।

### Variable-এর Value পরিবর্তন করা

```c
#include <stdio.h>

int main()
{
    int age = 20;

    printf("%d\n", age);

    age = 21;

    printf("%d", age);

    return 0;
}
```

**Output:**

```text
20
21
```

দেখা যাচ্ছে, প্রথমে `age`-এর Value ছিল 20। পরে আমরা সেটিকে 21 করেছি।

---

# ৩. Variable Naming Rules (Variable-এর নামকরণের নিয়ম)

C Programming-এ Variable-এর নাম দেওয়ার সময় কিছু নির্দিষ্ট নিয়ম অনুসরণ করতে হয়।

### Variable-এর নামকরণের নিয়মগুলো:

১. Variable-এর নাম Alphabet (A-Z, a-z) অথবা Underscore (`_`) দিয়ে শুরু হতে হবে।

২. Variable-এর নামের শুরুতে Number ব্যবহার করা যাবে না।

৩. Variable-এর নামের মধ্যে Alphabet, Number এবং Underscore ব্যবহার করা যায়।

৪. Variable-এর নামের মধ্যে Space ব্যবহার করা যাবে না।

৫. Variable-এর নামের মধ্যে Special Characters যেমন `@`, `#`, `$`, `%` ব্যবহার করা যাবে না।

৬. C Programming-এর Reserved Keyword-কে Variable-এর নাম হিসেবে ব্যবহার করা যাবে না।

৭. C Programming Case-Sensitive। অর্থাৎ `age`, `Age` এবং `AGE` তিনটি আলাদা নাম।

### সঠিক ও ভুল Variable Name

| Valid Name (সঠিক) | Invalid Name (ভুল) |
|---|---|
| `age` | `2age` |
| `student_name` | `student name` |
| `marks1` | `marks@1` |
| `_number` | `float` |
| `totalMarks` | `total-marks` |
| `myAge` | `my age` |

**মনে রাখবে:** Variable-এর নাম এমন হওয়া উচিত, যা দেখেই বোঝা যায় Variable-টি কী ধরনের Data সংরক্ষণ করছে।

যেমন: `studentAge`, `totalMarks`, `phoneNumber` ইত্যাদি।

---

# ৪. Basic Data Types এবং তাদের Size & Range

Data Type নির্ধারণ করে Variable-এর মধ্যে কী ধরনের Data রাখা যাবে এবং সাধারণত কতটুকু Memory প্রয়োজন হবে।

C Programming-এর কয়েকটি গুরুত্বপূর্ণ Basic Data Type হলো:

১. Integer (`int`)

২. Float (`float`)

৩. Double (`double`)

৪. Character (`char`)

### ১. Integer (int)

পূর্ণসংখ্যা সংরক্ষণের জন্য `int` ব্যবহার করা হয়।

**উদাহরণ:**

```c
int age = 21;
int number = 100;
int temperature = -5;
```

সাধারণ 32-bit Integer-এর ক্ষেত্রে:

- Size: 4 Bytes বা 32 Bits
- Signed Range: -2,147,483,648 থেকে 2,147,483,647

### ২. Float (float)

দশমিক সংখ্যা সংরক্ষণের জন্য `float` ব্যবহার করা হয়।

**উদাহরণ:**

```c
float height = 5.6;
float price = 99.50;
```

সাধারণত:

- Size: 4 Bytes বা 32 Bits
- Range: প্রায় -3.4 × 10³⁸ থেকে +3.4 × 10³⁸
- Precision: প্রায় 6–7 Decimal Digits

### ৩. Double (double)

অধিক Precision বা নির্ভুলতার সঙ্গে দশমিক সংখ্যা সংরক্ষণের জন্য `double` ব্যবহার করা হয়।

**উদাহরণ:**

```c
double pi = 3.1415926535;
double value = 12345.678901;
```

সাধারণত:

- Size: 8 Bytes বা 64 Bits
- Range: প্রায় -1.7 × 10³⁰⁸ থেকে +1.7 × 10³⁰⁸
- Precision: প্রায় 15–16 Decimal Digits

### ৪. Character (char)

একটি Character বা অক্ষর সংরক্ষণের জন্য `char` ব্যবহার করা হয়।

**উদাহরণ:**

```c
char grade = 'A';
char section = 'B';
```

সাধারণত:

- Size: 1 Byte বা 8 Bits
- Signed Char Range: -128 থেকে 127
- Unsigned Char Range: 0 থেকে 255

### Basic Data Types-এর Size ও Range

| Data Type | সাধারণ Size | সাধারণ Range / Precision |
|---|---:|---|
| `char` | 1 Byte | -128 থেকে 127 (Signed) |
| `int` | 4 Bytes | -2³¹ থেকে 2³¹-1 |
| `float` | 4 Bytes | প্রায় 6–7 Digits Precision |
| `double` | 8 Bytes | প্রায় 15–16 Digits Precision |

**বিশেষ দ্রষ্টব্য:**

- 1 Byte = 8 Bits।
- উপরের Size ও Range সাধারণ আধুনিক GCC/Windows Environment-এর প্রচলিত মান।
- C Language-এ সব Data Type-এর Size প্রতিটি কম্পিউটারে একই হবে এমন নিশ্চয়তা নেই। Compiler ও System Architecture অনুযায়ী কিছু Size পরিবর্তিত হতে পারে।
- `char`-এর Size সবসময় 1 Byte হলেও একটি Byte-এ কত Bit থাকবে তা System-এর ওপর নির্ভরশীল।

### Data Type-এর Size কীভাবে বের করব?

C Programming-এ `sizeof()` Operator ব্যবহার করে কোনো Data Type বা Variable-এর Memory Size জানা যায়।

**Example:**

```c
#include <stdio.h>

int main()
{
    printf("Size of int: %zu bytes\n", sizeof(int));
    printf("Size of float: %zu bytes\n", sizeof(float));
    printf("Size of double: %zu bytes\n", sizeof(double));
    printf("Size of char: %zu bytes\n", sizeof(char));

    return 0;
}
```

**Output (সাধারণ System-এ):**

```text
Size of int: 4 bytes
Size of float: 4 bytes
Size of double: 8 bytes
Size of char: 1 bytes
```

---

# ৫. Format Specifiers in C

Format Specifier হলো বিশেষ কিছু Symbol, যা `printf()` এবং `scanf()` Function-কে বলে দেয় কোন ধরনের Data Print বা Input করতে হবে।

### গুরুত্বপূর্ণ Format Specifiers

| Format Specifier | Data Type | কাজ |
|---|---|---|
| `%d` | int | Integer |
| `%f` | float | Decimal Number |
| `%lf` | double | scanf()-এ Double Input |
| `%c` | char | Character |
| `%s` | String | Text |
| `%u` | unsigned int | Positive Integer Range |
| `%ld` | long int | Long Integer |
| `%lld` | long long int | Long Long Integer |

### Example: একসঙ্গে বিভিন্ন Data Print করা

```c
#include <stdio.h>

int main()
{
    int age = 21;
    float marks = 85.5;
    double pi = 3.141592;
    char grade = 'A';

    printf("Age: %d\n", age);
    printf("Marks: %f\n", marks);
    printf("Pi: %f\n", pi);
    printf("Grade: %c\n", grade);

    return 0;
}
```

**Output:**

```text
Age: 21
Marks: 85.500000
Pi: 3.141592
Grade: A
```

**মনে রাখবে:**

- `printf()`-এ `float` এবং `double` উভয়ের জন্য `%f` ব্যবহার করা যায়।
- `scanf()`-এ `float`-এর জন্য `%f` এবং `double`-এর জন্য `%lf` ব্যবহার করতে হয়।

---

# ৬. Keywords in C Programming

Keyword হলো C Programming-এর কিছু Reserved Word, যেগুলোর নির্দিষ্ট অর্থ ও কাজ রয়েছে।

এই শব্দগুলো Compiler-এর জন্য আগে থেকেই নির্ধারিত। তাই এগুলোকে সাধারণ Variable Name বা Identifier হিসেবে ব্যবহার করা যায় না।

### C Language-এর প্রচলিত 32টি Keywords (C90 Standard)

| No. | Keyword | No. | Keyword |
|---:|---|---:|---|
| 1 | `auto` | 17 | `int` |
| 2 | `break` | 18 | `long` |
| 3 | `case` | 19 | `register` |
| 4 | `char` | 20 | `return` |
| 5 | `const` | 21 | `short` |
| 6 | `continue` | 22 | `signed` |
| 7 | `default` | 23 | `sizeof` |
| 8 | `do` | 24 | `static` |
| 9 | `double` | 25 | `struct` |
| 10 | `else` | 26 | `switch` |
| 11 | `enum` | 27 | `typedef` |
| 12 | `extern` | 28 | `union` |
| 13 | `float` | 29 | `unsigned` |
| 14 | `for` | 30 | `void` |
| 15 | `goto` | 31 | `volatile` |
| 16 | `if` | 32 | `while` |

**উদাহরণ:**

```c
int age = 21;
```

এখানে `int` একটি Keyword এবং `age` একটি Variable Name।

নিচের উদাহরণটি ভুল:

```c
int float = 50;
```

কারণ `float` একটি Reserved Keyword। তাই এটিকে Variable Name হিসেবে ব্যবহার করা যাবে না।

**বিশেষ দ্রষ্টব্য:** এখানে প্রচলিত 32টি Keyword-এর তালিকা দেওয়া হয়েছে, যা C90 Standard-এর। পরবর্তী C Standard-গুলোতে নতুন Keyword যুক্ত হয়েছে।

---

# ৭. Escape Sequences in C

Escape Sequence হলো কিছু বিশেষ Character Combination, যেগুলো ব্যবহার করে Output-এ নতুন লাইন, Tab Space, Quotation Mark এবং অন্যান্য বিশেষ Character প্রদর্শন করা যায়।

Escape Sequence সাধারণত Backslash (`\`) দিয়ে শুরু হয়।

### গুরুত্বপূর্ণ Escape Sequences

| Escape Sequence | কাজ |
|---|---|
| `\n` | New Line |
| `\t` | Horizontal Tab |
| `\v` | Vertical Tab |
| `\b` | Backspace |
| `\r` | Carriage Return |
| `\\` | Backslash Print |
| `\'` | Single Quote Print |
| `\"` | Double Quote Print |
| `\0` | Null Character |

### ১. New Line (\n)

একটি নতুন লাইনে Output দেখানোর জন্য `\n` ব্যবহার করা হয়।

```c
printf("Hello\nWorld");
```

**Output:**

```text
Hello
World
```

### ২. Horizontal Tab (\t)

Output-এর মধ্যে Horizontal Tab বা অতিরিক্ত ফাঁকা জায়গা তৈরি করতে `\t` ব্যবহার করা হয়।

```c
printf("Name\tAge");
```

**Output:**

```text
Name    Age
```

### ৩. Vertical Tab (\v)

Vertical Tab তৈরি করার জন্য `\v` ব্যবহার করা হয়।

```c
printf("Hello\vWorld");
```

এটি Output-এ Vertical Tab Space তৈরি করে। এর দৃশ্যমান ফলাফল Terminal অনুযায়ী পরিবর্তিত হতে পারে।

### ৪. Backspace (\b)

Backspace Character ব্যবহার করে Output-এর আগের একটি Character মুছে ফেলার মতো আচরণ তৈরি করা যায়।

```c
printf("Helloo\b");
```

সাধারণ Terminal-এ Output:

```text
Hello
```

### ৫. Single Quote Print (\')

Single Quotation Mark Print করার জন্য `\'` ব্যবহার করা হয়।

```c
printf("It\'s C Programming");
```

**Output:**

```text
It's C Programming
```

### ৬. Double Quote Print (\")

Double Quotation Mark Print করার জন্য `\"` ব্যবহার করা হয়।

```c
printf("He said, \"Hello!\"");
```

**Output:**

```text
He said, "Hello!"
```

### ৭. Backslash Print (\\)

Backslash Character Print করার জন্য `\\` ব্যবহার করা হয়।

```c
printf("C:\\Users\\Student");
```

**Output:**

```text
C:\Users\Student
```

---

# ৮. Constants in C Programming

Constant হলো এমন একটি Value, যা প্রোগ্রাম চলাকালীন পরিবর্তন করা যাবে না।

সাধারণ Variable-এর Value পরিবর্তন করা যায়, কিন্তু Constant-এর Value পরিবর্তন করার চেষ্টা করলে Compiler Error দেয়।

C Programming-এ `const` Keyword ব্যবহার করে Constant Variable তৈরি করা যায়।

### Syntax:

```c
const data_type variable_name = value;
```

### Example:

```c
#include <stdio.h>

int main()
{
    const int age = 21;

    printf("%d", age);

    return 0;
}
```

**Output:**

```text
21
```

এখন যদি আমরা `age`-এর Value পরিবর্তন করার চেষ্টা করি:

```c
#include <stdio.h>

int main()
{
    const int age = 21;

    age = 25;

    printf("%d", age);

    return 0;
}
```

**Result:** Compilation Error।

কারণ `const` ব্যবহার করে Variable-টিকে Read-Only করা হয়েছে।

### Variable এবং Constant-এর পার্থক্য

| Variable | Constant |
|---|---|
| Value পরিবর্তন করা যায় | Value পরিবর্তন করা যায় না |
| সাধারণত `const` ছাড়া Declare করা হয় | `const` ব্যবহার করে তৈরি করা যায় |
| যেমন: `int age = 20;` | যেমন: `const int age = 20;` |

**মনে রাখবে:** `const` দিয়ে তৈরি Object-কে প্রোগ্রামের মাধ্যমে পরিবর্তন করার অনুমতি থাকে না।

---

# ৯. scanf() Function কী?

`scanf()` হলো C Programming-এর একটি Standard Input Function।

এটি ব্যবহার করে আমরা User-এর কাছ থেকে Keyboard-এর মাধ্যমে Data Input নিতে পারি।

সহজ ভাষায়, `printf()` দিয়ে আমরা Output দেখাই এবং `scanf()` দিয়ে User-এর কাছ থেকে Input গ্রহণ করি।

### scanf() Function-এর Syntax

```c
scanf("format_specifier", &variable_name);
```

এখানে:

- `scanf()` হলো Input Function।
- Format Specifier বলে দেয় কী ধরনের Data Input নেওয়া হবে।
- `&` হলো Address-of Operator, যা Variable-এর Memory Address নির্দেশ করে।
- `variable_name` হলো যে Variable-এ Input রাখা হবে।

### ১. Integer Input নেওয়া

```c
#include <stdio.h>

int main()
{
    int age;

    printf("Enter your age: ");
    scanf("%d", &age);

    printf("Your age is %d", age);

    return 0;
}
```

**Input:**

```text
21
```

**Output:**

```text
Enter your age: 21
Your age is 21
```

### ২. Float Input নেওয়া

```c
#include <stdio.h>

int main()
{
    float marks;

    printf("Enter your marks: ");
    scanf("%f", &marks);

    printf("Your marks: %f", marks);

    return 0;
}
```

**Input:**

```text
85.5
```

**Output:**

```text
Your marks: 85.500000
```

### ৩. Character Input নেওয়া

```c
#include <stdio.h>

int main()
{
    char grade;

    printf("Enter your grade: ");
    scanf(" %c", &grade);

    printf("Your grade is: %c", grade);

    return 0;
}
```

**Input:**

```text
A
```

**Output:**

```text
Your grade is: A
```

এখানে `%c`-এর আগে একটি Space দেওয়া হয়েছে, যাতে আগের Input-এর Newline Character সমস্যা তৈরি না করে।

### ৪. Double Input নেওয়া

```c
#include <stdio.h>

int main()
{
    double price;

    printf("Enter price: ");
    scanf("%lf", &price);

    printf("Price: %f", price);

    return 0;
}
```

**Input:**

```text
125.75
```

**Output:**

```text
Price: 125.750000
```

### ৫. String Input নেওয়া

একটি Word বা Space ছাড়া Text Input নেওয়ার জন্য `%s` ব্যবহার করা যায়।

```c
#include <stdio.h>

int main()
{
    char name[30];

    printf("Enter your name: ");
    scanf("%29s", name);

    printf("Hello %s", name);

    return 0;
}
```

**Input:**

```text
Joy
```

**Output:**

```text
Hello Joy
```

এখানে String-এর জন্য সাধারণভাবে `&` ব্যবহার করা হয়নি। কারণ Array-এর নাম বেশিরভাগ Expression-এ প্রথম Element-এর Address হিসেবে ব্যবহৃত হয়।

**বিশেষ দ্রষ্টব্য:** `%s` সাধারণত প্রথম Whitespace বা Space পর্যন্ত Input নেয়। সম্পূর্ণ নাম বা Sentence Input নেওয়ার জন্য পরবর্তীতে `fgets()` শিখব।

### গুরুত্বপূর্ণ scanf() Format Specifiers

| Data Type | Format Specifier |
|---|---|
| `int` | `%d` |
| `float` | `%f` |
| `double` | `%lf` |
| `char` | `%c` |
| `char array` (String) | `%s` |

---

# ১০. Arithmetic Operators in C

Arithmetic Operators হলো এমন কিছু Operator, যেগুলো ব্যবহার করে C Programming-এ গাণিতিক হিসাব করা যায়।

C Programming-এ পাঁচটি Basic Arithmetic Operator রয়েছে।

### ১. Addition (+)

দুটি সংখ্যা যোগ করার জন্য `+` Operator ব্যবহার করা হয়।

```c
int a = 10;
int b = 20;

int result = a + b;

printf("%d", result);
```

**Output:**

```text
30
```

### ২. Subtraction (-)

একটি সংখ্যা থেকে অন্য একটি সংখ্যা বিয়োগ করার জন্য `-` Operator ব্যবহার করা হয়।

```c
int a = 20;
int b = 10;

int result = a - b;

printf("%d", result);
```

**Output:**

```text
10
```

### ৩. Multiplication (*)

দুটি সংখ্যা গুণ করার জন্য `*` Operator ব্যবহার করা হয়।

```c
int a = 10;
int b = 5;

int result = a * b;

printf("%d", result);
```

**Output:**

```text
50
```

### ৪. Division (/)

একটি সংখ্যাকে অন্য একটি সংখ্যা দিয়ে ভাগ করার জন্য `/` Operator ব্যবহার করা হয়।

```c
int a = 20;
int b = 5;

int result = a / b;

printf("%d", result);
```

**Output:**

```text
4
```

**গুরুত্বপূর্ণ:** দুটি Integer-কে ভাগ করলে Integer Result পাওয়া যায়। অর্থাৎ দশমিক অংশ বাদ পড়ে যায়।

উদাহরণ:

```c
printf("%d", 10 / 3);
```

**Output:**

```text
3
```

দশমিক ফলাফল পেতে Floating-Point ব্যবহার করতে হবে।

```c
printf("%f", 10.0 / 3.0);
```

**Output:**

```text
3.333333
```

### ৫. Modulus (%)

ভাগশেষ বের করার জন্য `%` Operator ব্যবহার করা হয়।

```c
int a = 10;
int b = 3;

int result = a % b;

printf("%d", result);
```

**Output:**

```text
1
```

কারণ 10-কে 3 দিয়ে ভাগ করলে ভাগফল 3 এবং ভাগশেষ 1।

**মনে রাখবে:** `%` Operator Integer-এর ক্ষেত্রে ব্যবহার করা হয়; Floating-Point Number-এর জন্য এটি ব্যবহার করা যায় না।

### Arithmetic Operators-এর তালিকা

| Operator | নাম | কাজ |
|---|---|---|
| `+` | Addition | যোগ |
| `-` | Subtraction | বিয়োগ |
| `*` | Multiplication | গুণ |
| `/` | Division | ভাগ |
| `%` | Modulus | ভাগশেষ |

---

# ১১. Complete Practical Example

এবার আমরা আজকের শেখা কয়েকটি বিষয় একসঙ্গে ব্যবহার করে একটি ছোট C Program তৈরি করব।

### দুইটি সংখ্যার যোগফল নির্ণয়

```c
#include <stdio.h>

int main()
{
    int num1, num2, sum;

    printf("Enter first number: ");
    scanf("%d", &num1);

    printf("Enter second number: ");
    scanf("%d", &num2);

    sum = num1 + num2;

    printf("The sum is: %d", sum);

    return 0;
}
```

**Input:**

```text
Enter first number: 10
Enter second number: 20
```

**Output:**

```text
The sum is: 30
```

এখানে আমরা শিখেছি:

- Variable Declaration
- User Input নেওয়া
- `scanf()` ব্যবহার
- Arithmetic Operator ব্যবহার
- `printf()` দিয়ে Output দেখানো

---

# ১২. Quick Revision (গুরুত্বপূর্ণ বিষয়গুলো একনজরে)

| বিষয় | মনে রাখার বিষয় |
|---|---|
| Variable | Data সংরক্ষণের Named Location |
| Declaration | Variable তৈরি করা |
| Initialization | Variable-এ প্রথম Value দেওয়া |
| `int` | পূর্ণসংখ্যা |
| `float` | দশমিক সংখ্যা |
| `double` | অধিক Precision-এর দশমিক সংখ্যা |
| `char` | Character |
| `sizeof()` | Memory Size বের করা |
| Keyword | Reserved Word |
| Format Specifier | Data-এর ধরন নির্ধারণকারী Format |
| Escape Sequence | বিশেষ Character প্রদর্শনের পদ্ধতি |
| `const` | Value পরিবর্তন রোধ করে |
| `scanf()` | Input নেওয়ার Function |
| `printf()` | Output দেখানোর Function |
| `&` | Address-of Operator |
| `+` | যোগ |
| `-` | বিয়োগ |
| `*` | গুণ |
| `/` | ভাগ |
| `%` | ভাগশেষ |

---

# ১৩. অনুশীলনী (Practice Questions)

## Part A: Short Questions

১. Variable কী? উদাহরণসহ লেখো।

২. Variable Declaration এবং Initialization-এর মধ্যে পার্থক্য কী?

৩. Variable Naming-এর পাঁচটি নিয়ম লেখো।

৪. `int`, `float`, `double` এবং `char`-এর সাধারণ Memory Size কত?

৫. 1 Byte সমান কত Bit?

৬. Format Specifier কী? `%d`, `%f`, `%c` এবং `%s`-এর ব্যবহার লেখো।

৭. C90 Standard অনুযায়ী 32টি Keyword কী কী?

৮. Escape Sequence কী? পাঁচটি Escape Sequence-এর নাম লেখো।

৯. Constant কী? `const` Keyword-এর কাজ কী?

১০. `printf()` এবং `scanf()`-এর মধ্যে পার্থক্য কী?

১১. `scanf()`-এ `&` কেন ব্যবহার করা হয়?

১২. Arithmetic Operator কী? পাঁচটি Arithmetic Operator-এর নাম লেখো।

১৩. Integer Division এবং Floating-Point Division-এর মধ্যে পার্থক্য কী?

১৪. Modulus Operator-এর কাজ কী?

## Part B: Practical Tasks

**১. Personal Information Program**

একটি C Program লেখো, যেখানে নিজের নাম, বয়স, Department এবং University-এর নাম Print করতে হবে।

**২. User Input Program**

একটি C Program লেখো, যেখানে User-এর কাছ থেকে বয়স Input নিয়ে সেটি Print করতে হবে।

**৩. Marks Calculator**

একজন শিক্ষার্থীর তিনটি বিষয়ের নম্বর Input নিয়ে মোট নম্বর নির্ণয় করতে হবে।

**৪. Arithmetic Calculator**

User-এর কাছ থেকে দুটি Integer Input নিয়ে তাদের যোগ, বিয়োগ, গুণ, ভাগ এবং ভাগশেষ নির্ণয় করতে হবে।

**৫. Area of Rectangle**

User-এর কাছ থেকে Rectangle-এর Length এবং Width Input নিয়ে Area নির্ণয় করতে হবে।

Formula:

Area = Length × Width

**৬. Constant Practice**

`const` ব্যবহার করে একটি Constant Variable তৈরি করো এবং সেটির Value পরিবর্তন করার চেষ্টা করে Compiler Error পর্যবেক্ষণ করো।

