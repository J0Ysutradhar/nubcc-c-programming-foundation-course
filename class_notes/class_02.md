# ১. Code::Blocks পরিচিতি (Introduction to Code::Blocks)

Code::Blocks হলো একটি জনপ্রিয় Integrated Development Environment (IDE)। এটি ব্যবহার করে Programmer সহজেই C এবং C++ Programming করতে পারে।

IDE (Integrated Development Environment) হলো এমন একটি Software Environment, যেখানে Code লেখা, Compile করা এবং Run করার সুবিধা একসঙ্গে পাওয়া যায়।

### Code::Blocks-এ C Program তৈরি করার নিয়ম

১. প্রথমে Code::Blocks Software Open করতে হবে।

২. File → New → Empty File নির্বাচন করতে হবে।

৩. এরপর প্রয়োজনীয় C Code লিখতে হবে।

৪. File → Save As-এ গিয়ে ফাইলের নাম দিতে হবে।

৫. C Programming File-এর Extension অবশ্যই `.c` হতে হবে।

**উদাহরণ:**

`hello.c`

**মনে রাখবে:** C Programming-এর Source File-এর Extension হলো `.c` এবং C++ Programming-এর Source File-এর Extension হলো `.cpp`।

---

# ২. আমাদের প্রথম C Program (Hello World)

চলো, আমরা একটি সাধারণ C Program দেখি, যা স্ক্রিনে একটি লেখা প্রদর্শন করবে।

### Example:

```c
#include <stdio.h>

int main()
{
    printf("Hello World!");

    return 0;
}
```

**Output:**

```text
Hello World!
```

এই প্রোগ্রামটি Run করলে স্ক্রিনে `Hello World!` লেখাটি দেখা যাবে।

### C Program-এর প্রতিটি লাইনের কাজ

**১. `#include <stdio.h>`**

এটি একটি Header File Include করার নির্দেশনা।

`stdio.h`-এর পূর্ণরূপ হলো Standard Input Output Header।

এতে `printf()` এবং `scanf()`-এর মতো Input ও Output সংক্রান্ত Function-এর Declaration রয়েছে।

**২. `int main()`**

`main()` হলো C Program-এর প্রধান Entry Point।

সাধারণভাবে C Program-এর Execution `main()` Function থেকে শুরু হয়।

এখন শুধু মনে রাখবে, `main()` হলো আমাদের প্রোগ্রামের মূল প্রবেশপথ। Function সম্পর্কে আমরা পরবর্তী ক্লাসে বিস্তারিত আলোচনা করব।

**৩. `{ }` (Curly Braces) or parentheses&#x20;**

Curly Braces দিয়ে একটি Block-এর শুরু এবং শেষ বোঝানো হয়।

`{` দিয়ে Block শুরু হয় এবং `}` দিয়ে Block শেষ হয়।

**৪. `printf("Hello World!");`**

`printf()` হলো C Programming-এর একটি Output Function।

এটি ব্যবহার করে আমরা Computer Screen-এ বিভিন্ন ধরনের লেখা, সংখ্যা এবং অন্যান্য Output প্রদর্শন করতে পারি।

**৫. `return 0;`**

এটি সাধারণত `main()` Function-এর মাধ্যমে Operating System-কে জানায় যে প্রোগ্রামটি সফলভাবে শেষ হয়েছে।

**৬. `;` (Semicolon)**

C Programming-এ সাধারণত প্রতিটি Statement-এর শেষে Semicolon (`;`) ব্যবহার করা হয়।

এটি একটি Statement-এর সমাপ্তি নির্দেশ করে।

---

# ৩. Comments in C Programming

Comment হলো প্রোগ্রামের মধ্যে লেখা এমন কিছু Text, যা Compiler সাধারণত উপেক্ষা করে।

Comments মূলত Code সম্পর্কে ব্যাখ্যা বা নির্দেশনা লেখার জন্য ব্যবহার করা হয়।

C Programming-এ দুই ধরনের Comment রয়েছে।

### ১. Single-Line Comment

একটি মাত্র লাইনে Comment লেখার জন্য Double Slash (`//`) ব্যবহার করা হয়।

**Example:**

```c
#include <stdio.h>

int main()
{
    // This is a single-line comment

    printf("Hello World!");

    return 0;
}
```

এখানে `//`-এর পরের লেখাটি Comment হিসেবে বিবেচিত হবে।

### ২. Multi-Line Comment

একাধিক লাইনে Comment লেখার জন্য `/*` এবং `*/` ব্যবহার করা হয়।

**Example:**

```c
#include <stdio.h>

int main()
{
    /*
       This is a multi-line comment.
       We can write multiple lines here.
       Compiler ignores this comment.
    */

    printf("Hello World!");

    return 0;
}
```

এখানে `/*` দিয়ে Comment শুরু হয় এবং `*/` দিয়ে Comment শেষ হয়।

**মনে রাখবে:**

- `//` = Single-Line Comment
- `/* ... */` = Multi-Line Comment

---

# ৪. printf() Function কী?

`printf()` হলো C Programming-এর একটি Standard Output Function।

এর মাধ্যমে আমরা Monitor বা Console Screen-এ বিভিন্ন ধরনের তথ্য প্রদর্শন করতে পারি।

`printf()`-এর মাধ্যমে সাধারণত Text, Character, Integer, Floating-Point Number ইত্যাদি Print করা যায়।

### ১. String Print করা

কোনো Sentence বা Text Print করার জন্য Double Quotation (`" "`) ব্যবহার করা হয়।

**Example:**

```c
#include <stdio.h>

int main()
{
    printf("Welcome to NUB Computer Club!");

    return 0;
}
```

**Output:**

```text
Welcome to NUB Computer Club!
```

### ২. Character Print করা

একটি Character Print করার জন্য `%c` Format Specifier ব্যবহার করা হয়।

**Example:**

```c
#include <stdio.h>

int main()
{
    printf("%c", 'A');

    return 0;
}
```

**Output:**

```text
A
```

এখানে Character লেখার জন্য Single Quotation (`' '`) ব্যবহার করা হয়েছে।

### ৩. Integer Print করা

পূর্ণসংখ্যা (যেমন: 10, 20, 100) Print করার জন্য `%d` Format Specifier ব্যবহার করা হয়।

**Example:**

```c
#include <stdio.h>

int main()
{
    printf("%d", 100);

    return 0;
}
```

**Output:**

```text
100
```

### ৪. Floating-Point Number Print করা

দশমিক সংখ্যা Print করার জন্য `%f` Format Specifier ব্যবহার করা হয়।

**Example:**

```c
#include <stdio.h>

int main()
{
    printf("%f", 10.50);

    return 0;
}
```

**Output:**

```text
10.500000
```

প্রয়োজনে দশমিকের পর কত ঘর দেখাবে তা নির্ধারণ করা যায়।

যেমন:

```c
printf("%.2f", 10.50);
```

**Output:**

```text
10.50
```

### গুরুত্বপূর্ণ Format Specifiers

| Format Specifier | ব্যবহার                                          |
| ---------------- | ------------------------------------------------ |
| `%d`             | Integer                                          |
| `%f`             | Floating-Point Number                            |
| `%c`             | Character                                        |
| `%s`             | String                                           |
| `%lf`            | `printf()`-এ Double-এর জন্যও `%f` ব্যবহার করা হয় |

**বিশেষ দ্রষ্টব্য:** `printf()`-এ `float` এবং `double` উভয়ের জন্য `%f` ব্যবহার করা যায়। তবে `scanf()`-এ `float`-এর জন্য `%f` এবং `double`-এর জন্য `%lf` ব্যবহার করতে হয়।

---

# ৫. Data Types in C Programming

Data Type হলো এমন একটি বিষয়, যা নির্ধারণ করে একটি Variable-এ কী ধরনের Data সংরক্ষণ করা যাবে।

সহজ ভাষায়, আমরা যখন কোনো তথ্য কম্পিউটারে সংরক্ষণ করি, তখন সেই তথ্যের ধরন অনুযায়ী Data Type ব্যবহার করি।

C Programming-এ কয়েকটি Basic Data Type রয়েছে।

### ১. Integer (int)

পূর্ণসংখ্যা সংরক্ষণের জন্য `int` ব্যবহার করা হয়।

**উদাহরণ:**

```c
int age = 21;
int number = 100;
```

এখানে `age` এবং `number` দুটি Integer Variable।

### ২. Float (float)

দশমিক সংখ্যা সংরক্ষণের জন্য `float` ব্যবহার করা হয়।

**উদাহরণ:**

```c
float height = 5.6;
float price = 99.50;
```

### ৩. Character (char)

একটি Character বা অক্ষর সংরক্ষণের জন্য `char` ব্যবহার করা হয়।

**উদাহরণ:**

```c
char grade = 'A';
char letter = 'B';
```

এখানে Character সংরক্ষণের জন্য Single Quotation (`' '`) ব্যবহার করা হয়েছে।

### ৪. Double (double)

Float-এর তুলনায় বেশি Precision বা নির্ভুলতা প্রয়োজন এমন দশমিক সংখ্যা সংরক্ষণের জন্য `double` ব্যবহার করা হয়।

**উদাহরণ:**

```c
double pi = 3.1415926535;
double price = 125.56789;
```

### ৫. Void (void)

`void` বলতে কোনো Value বা নির্দিষ্ট Return Type না থাকাকে বোঝায়। এটি সাধারণত Function-এর ক্ষেত্রে ব্যবহার করা হয়।

এ বিষয়ে আমরা Function অধ্যায়ে বিস্তারিত শিখব।

### Basic Data Types-এর তালিকা

| Data Type | ব্যবহার                        | উদাহরণ   |
| --------- | ------------------------------ | -------- |
| `int`     | পূর্ণসংখ্যা                    | 100      |
| `float`   | দশমিক সংখ্যা                   | 10.5     |
| `char`    | একটি Character                 | 'A'      |
| `double`  | অধিক Precision-এর দশমিক সংখ্যা | 3.141592 |
| `void`    | কোনো Value নেই                 | void     |

**মনে রাখবে:** Data Type অনুযায়ী কম্পিউটার বুঝতে পারে কী ধরনের Data সংরক্ষণ ও ব্যবহার করতে হবে।

---

# ৬. C Compiler কীভাবে কাজ করে? (Compilation Process)

আমরা জানি, C একটি Compiled Programming Language। অর্থাৎ C Program সরাসরি Source Code থেকে Execute হয় না। Compiler-এর মাধ্যমে এটি বিভিন্ন ধাপ অতিক্রম করে।

GCC Compiler ব্যবহার করে একটি C Program Compile করার সময় সাধারণত চারটি গুরুত্বপূর্ণ ধাপ সম্পন্ন হয়।

### Compilation-এর চারটি প্রধান ধাপ

**১. Preprocessing**

এটি Compilation-এর প্রথম ধাপ।

এই ধাপে Preprocessor `#include`, `#define` ইত্যাদি Directive নিয়ে কাজ করে এবং প্রয়োজনীয় পরিবর্তন করে একটি Expanded Source Code তৈরি করে।

Output File: `.i`

**২. Compilation**

এই ধাপে Preprocessed Code-কে Assembly Language Code-এ রূপান্তর করা হয়।

Output File: `.s`

**৩. Assembly**

এই ধাপে Assembly Code-কে Machine-Level Object Code-এ রূপান্তর করা হয়।

Output File: `.o`

**৪. Linking**

এটি শেষ ধাপ।

এই ধাপে Object File এবং প্রয়োজনীয় Library Code একত্রিত করে একটি Executable File তৈরি করা হয়।

Windows-এ Executable File-এর Extension সাধারণত `.exe`।

### সম্পূর্ণ Compilation Process

Source Code (.c)

↓

Preprocessing (.i)

↓

Compilation (.s)

↓

Assembly (.o)

↓

Linking (.exe)

↓

Execution (Program Run)

### GCC দিয়ে Compilation-এর চারটি ধাপ আলাদাভাবে দেখা

ধরা যাক, আমাদের C Source File-এর নাম `main.c`।

**Step 1: Preprocessing**

```bash
gcc -E main.c -o main.i
```

**Step 2: Compilation**

```bash
gcc -S main.i -o main.s
```

**Step 3: Assembly**

```bash
gcc -c main.s -o main.o
```

**Step 4: Linking**

```bash
gcc main.o -o main.exe
```

এবার প্রোগ্রামটি Run করতে পারি:

```bash
.\main.exe
```

**গুরুত্বপূর্ণ:** সাধারণভাবে আমরা শুধু `gcc main.c -o main.exe` Command ব্যবহার করলেও GCC নিজে থেকেই এই চারটি ধাপ সম্পন্ন করে। আলাদা Command ব্যবহার করে আমরা প্রতিটি ধাপের Intermediate File দেখতে পারি।

---

# ৭. গুরুত্বপূর্ণ বিষয়গুলো একনজরে (Quick Revision)

| বিষয়         | সংক্ষিপ্ত ধারণা            |
| ------------ | -------------------------- |
| Code::Blocks | C/C++ Programming-এর IDE   |
| `.c`         | C Source File Extension    |
| `.cpp`       | C++ Source File Extension  |
| `main()`     | Program-এর Entry Point     |
| `printf()`   | Output প্রদর্শনের Function |
| `//`         | Single-Line Comment        |
| `/* */`      | Multi-Line Comment         |
| `int`        | Integer Data Type          |
| `float`      | Floating-Point Data Type   |
| `char`       | Character Data Type        |
| `double`     | Double Precision Data Type |
| `GCC`        | GNU Compiler Collection    |
| `.i`         | Preprocessed File          |
| `.s`         | Assembly File              |
| `.o`         | Object File                |
| `.exe`       | Windows Executable File    |

---

# ৮. অনুশীলনী (Practice Questions)

নিজের শেখা যাচাই করতে নিচের প্রশ্নগুলোর উত্তর দেওয়ার চেষ্টা করো।

**সংক্ষিপ্ত প্রশ্ন:**

১. Code::Blocks কী?

২. C Programming-এর File Extension কী?

৩. `#include <stdio.h>` কেন ব্যবহার করা হয়?

৪. `main()` Function-এর কাজ কী?

৫. `printf()` Function কী কাজে ব্যবহার করা হয়?

৬. Single-Line এবং Multi-Line Comment কীভাবে লেখা হয়?

৭. Format Specifier কী?

৮. `%d`, `%f`, `%c` এবং `%s`-এর কাজ কী?

৯. Data Type কী? C Programming-এর চারটি Basic Data Type-এর নাম লেখো।

১০. Compiler কীভাবে Source Code-কে Executable File-এ রূপান্তর করে?

১১. GCC Compilation Process-এর চারটি ধাপের নাম লেখো।

**প্র্যাকটিক্যাল অনুশীলন:**

১. একটি C Program লিখে স্ক্রিনে `Hello Northern University!` Print করো।

২. একটি C Program লিখে নিজের নাম Print করো।

৩. একটি C Program লিখে নিজের নাম, Department এবং University-এর নাম আলাদা আলাদা লাইনে Print করো।

৪. একটি C Program লিখে `int`, `float`, `char` এবং `double`-এর উদাহরণ Print করো।

৫. একটি C Program লিখে Single-Line এবং Multi-Line Comment ব্যবহার করো।

---

## পরবর্তী ক্লাসের প্রস্তুতি

পরবর্তী ক্লাসে আমরা C Programming-এর আরও গুরুত্বপূর্ণ বিষয় নিয়ে আলোচনা করব। বিশেষ করে Variables, Constants, Identifiers, Keywords এবং Variable Declaration ও Initialization সম্পর্কে বিস্তারিত শিখব।

**Practice regularly, Keep Learning & Happy Coding!**

*NUB Computer Club | C Programming Foundation Course*
