NORTHERN UNIVERSITY BANGLADESH

NUB COMPUTER CLUB

C Programming Foundation Course

Class 05: Multiple Variables, Input, Arithmetic & Unary Operators

Lecture Notes | Beginner Friendly | C Programming

---

01. Multiple Variables in a Single Statement

C programming-এ একই Data Type-এর একাধিক Variable একই Statement-এ Declare করা যায়। প্রতিটি Variable-এর নাম কমা (,) দিয়ে আলাদা করতে হয়।

Syntax

data_type variable1, variable2, variable3;

Example

int a, b, c;
float x, y;

এখানে "a", "b", "c" তিনটি Integer Variable এবং "x", "y" দুটি Float Variable একই Statement-এ Declare করা হয়েছে।

Multiple Variables Initialization

একই Statement-এ একাধিক Variable-এর Value নির্ধারণ বা Initialize করাও সম্ভব।

int a = 10, b = 20, c = 30;

এখানে প্রতিটি Variable-এর জন্য আলাদা Value নির্ধারণ করা হয়েছে।

Output Example:

#include <stdio.h>

int main()
{
    int a = 10, b = 20, c = 30;

    printf("%d %d %d", a, b, c);

    return 0;
}

Output:

10 20 30

---

02. Taking Multiple Inputs in a Single Statement

আমরা আগের ক্লাসে "scanf()" ব্যবহার করে User-এর কাছ থেকে Input নেওয়া শিখেছি।

একই "scanf()" Statement ব্যবহার করে একাধিক Variable-এর Input নেওয়া যায়। এজন্য Format Specifier-গুলো পাশাপাশি লিখতে হয় এবং Variable-গুলো Comma দিয়ে আলাদা করতে হয়।

Syntax

scanf("%d %d %d", &a, &b, &c);

এখানে তিনটি Integer Input নেওয়া হচ্ছে। Input দেওয়ার সময় Space, Enter অথবা Tab ব্যবহার করে Value-গুলো আলাদা করা যায়।

Example

#include <stdio.h>

int main()
{
    int a, b, c;

    scanf("%d %d %d", &a, &b, &c);

    printf("A = %d\n", a);
    printf("B = %d\n", b);
    printf("C = %d\n", c);

    return 0;
}

Input:

10 20 30

Output:

A = 10
B = 20
C = 30

একই লাইনে একাধিক Input নেওয়ার সুবিধা

scanf("%d%d", &a, &b);

অথবা

scanf("%d %d", &a, &b);

দুটিই Integer Input নেওয়ার ক্ষেত্রে কাজ করে। সাধারণত আমরা Code পরিষ্কার রাখার জন্য Format Specifier-এর মধ্যে Space ব্যবহার করতে পারি।

---

03. Arithmetic Operators in C

Arithmetic Operator ব্যবহার করে আমরা বিভিন্ন গাণিতিক হিসাব করতে পারি।

C Programming-এ প্রধান Arithmetic Operator পাঁচটি।

Operator| Name| কাজ
"+"| Addition| যোগ করা
"-"| Subtraction| বিয়োগ করা
"*"| Multiplication| গুণ করা
"/"| Division| ভাগ করা
"%"| Modulus| ভাগশেষ বের করা

Example

#include <stdio.h>

int main()
{
    int a = 10, b = 3;

    printf("Addition = %d\n", a + b);
    printf("Subtraction = %d\n", a - b);
    printf("Multiplication = %d\n", a * b);
    printf("Division = %d\n", a / b);
    printf("Modulus = %d\n", a % b);

    return 0;
}

Output:

Addition = 13
Subtraction = 7
Multiplication = 30
Division = 3
Modulus = 1

Modulus (%) কী?

Modulus Operator দুটি Integer-কে ভাগ করার পর ভাগশেষ (Remainder) বের করে।

উদাহরণ:

10 % 3 = 1
15 % 4 = 3
20 % 5 = 0

যেহেতু 10 কে 3 দিয়ে ভাগ করলে ভাগশেষ 1 থাকে, তাই "10 % 3" এর Result হবে "1"।

Modulus-এর ব্যবহার:

- সংখ্যা জোড় (Even) নাকি বিজোড় (Odd) নির্ণয় করা।
- কোনো সংখ্যা অন্য সংখ্যা দ্বারা সম্পূর্ণ বিভাজ্য কি না তা পরীক্ষা করা।

---

04. Integer Division Problem

C Programming-এ Integer Variable দিয়ে Integer Division করলে Result-ও Integer হয়।

অর্থাৎ, ভাগফলে দশমিক অংশ থাকলেও C সেই দশমিক অংশ বাদ দিয়ে শুধু পূর্ণসংখ্যা রাখে।

Example

#include <stdio.h>

int main()
{
    int a = 5, b = 2;

    printf("%d", a / b);

    return 0;
}

Output:

2

কেন 2.5 আসে না?

Mathematically:

[
5 \div 2 = 2.5
]

কিন্তু C Programming-এ এখানে "a" এবং "b" দুটিই Integer।

তাই Integer Division হওয়ার কারণে দশমিক অংশ বাদ পড়ে যায়।

Calculation| Result
"5 / 2"| 2
"7 / 2"| 3
"9 / 4"| 2
"10 / 4"| 2

মনে রাখবে, Integer Division-এ দশমিক অংশ Round করা হয় না; Truncate করা হয় অর্থাৎ দশমিক অংশ বাদ দেওয়া হয়।

---

05. Type Casting

Integer Division-এর এই সমস্যার সমাধান করতে আমরা Type Casting ব্যবহার করতে পারি।

Type Casting হলো কোনো Value বা Expression-কে এক Data Type থেকে অন্য Data Type-এ রূপান্তর করা।

C-তে আমরা Casting-এর মাধ্যমে Integer-কে Float বা Double-এ রূপান্তর করতে পারি।

Syntax

(float) variable

এখানে "(float)" লিখে আমরা নির্দিষ্ট Value-কে Float Type-এ রূপান্তর করছি।

Example: Type Casting ব্যবহার করে Division

#include <stdio.h>

int main()
{
    int a = 5, b = 2;

    printf("%f", (float)a / b);

    return 0;
}

Output:

2.500000

কীভাবে কাজ করল?

- "a" এর Value হলো "5" এবং "b" এর Value হলো "2"।
- "(float)a" লিখে "a"-কে Float-এ Convert করা হয়েছে।
- এখন Division হচ্ছে "5.0 / 2"।
- যেহেতু একটি Operand Float, তাই Division-এর Result Decimal-এ পাওয়া যায়।

নির্দিষ্ট Decimal পর্যন্ত দেখানো

printf("%.2f", (float)a / b);

Output:

2.50

"%.2f" ব্যবহার করলে Decimal Point-এর পরে দুইটি Digit প্রদর্শিত হয়।

মনে রাখবে: Type Casting শুধু Output-এ Decimal দেখানোর জন্য নয়, বিভিন্ন Data Type-এর মধ্যে সঠিকভাবে Calculation করার জন্যও গুরুত্বপূর্ণ।

---

06. Unary Operators

Unary Operator হলো এমন Operator, যা একটি মাত্র Operand বা Variable-এর উপর কাজ করে।

C Programming-এ আমরা আজ Increment এবং Decrement Operator শিখেছি।

Increment Operator (++)

Increment Operator কোনো Variable-এর Value এক (1) বৃদ্ধি করে।

int a = 5;
a++;

এখন "a" এর Value হবে "6"।

নিচের দুইটি Statement একই কাজ করে:

a++;

a = a + 1;

Decrement Operator (--)

Decrement Operator কোনো Variable-এর Value এক (1) কমিয়ে দেয়।

int a = 5;
a--;

এখন "a" এর Value হবে "4"।

নিচের দুইটি Statement একই কাজ করে:

a--;

a = a - 1;

---

07. Post-Increment & Post-Decrement

Increment এবং Decrement Operator দুইভাবে ব্যবহার করা যায়:

- Pre-Increment / Pre-Decrement
- Post-Increment / Post-Decrement

Post-Increment (a++)

Post-Increment-এ প্রথমে Variable-এর বর্তমান Value Expression-এ ব্যবহার হয়, এরপর Value এক বৃদ্ধি পায়।

int a = 5;

printf("%d\n", a++);
printf("%d\n", a);

Output:

5
6

ব্যাখ্যা:

1. প্রথম "printf()"-এ "a" এর বর্তমান Value "5" Print হয়।
2. এরপর "a" এর Value এক বৃদ্ধি পেয়ে "6" হয়।
3. দ্বিতীয় "printf()"-এ "6" Print হয়।

Post-Decrement (a--)

Post-Decrement-এ প্রথমে বর্তমান Value Expression-এ ব্যবহার হয়, এরপর Value এক কমে যায়।

int a = 5;

printf("%d\n", a--);
printf("%d\n", a);

Output:

5
4

Pre-Increment (++a)

Pre-Increment-এ প্রথমে Variable-এর Value এক বৃদ্ধি হয়, তারপর Expression-এ সেই নতুন Value ব্যবহার হয়।

int a = 5;

printf("%d\n", ++a);
printf("%d\n", a);

Output:

6
6

Pre-Decrement (--a)

Pre-Decrement-এ প্রথমে Variable-এর Value এক কমে যায়, তারপর Expression-এ সেই নতুন Value ব্যবহার হয়।

int a = 5;

printf("%d\n", --a);
printf("%d\n", a);

Output:

4
4

চারটি Operator-এর পার্থক্য

Operator| কাজ
"a++"| আগে বর্তমান Value ব্যবহার, পরে 1 বৃদ্ধি
"++a"| আগে 1 বৃদ্ধি, পরে নতুন Value ব্যবহার
"a--"| আগে বর্তমান Value ব্যবহার, পরে 1 হ্রাস
"--a"| আগে 1 হ্রাস, পরে নতুন Value ব্যবহার

গুরুত্বপূর্ণ: শুধু আলাদা Statement হিসেবে "a++" এবং "++a" ব্যবহার করলে উভয়ই "a" এর Value এক বাড়ায়। পার্থক্য বোঝা যায় যখন একই Expression-এ Value ব্যবহার করা হয়।

---

08. Operator Precedence

একটি Expression-এর মধ্যে একাধিক Operator থাকলে কোন Operator আগে কাজ করবে, তা নির্ধারণ করে Operator Precedence।

আমরা সাধারণ Mathematics-এ যেমন BODMAS নিয়ম অনুসরণ করি, C Programming-এও Operator-এর নির্দিষ্ট Priority বা Precedence রয়েছে।

সাধারণ Precedence

Priority| Operator| কাজ
1| "()"| Parentheses / Bracket
2| "++", "--"| Increment / Decrement
3| "*", "/", "%"| Multiplication, Division, Modulus
4| "+", "-"| Addition, Subtraction

একই Priority-এর Operator সাধারণত Left থেকে Right-এ কাজ করে (এই Arithmetic Operator-গুলোর ক্ষেত্রে)।

Example 1

int result = 10 + 5 * 2;

Calculation:

প্রথমে Multiplication:

"5 * 2 = 10"

তারপর Addition:

"10 + 10 = 20"

Result:

20

Example 2: Parentheses ব্যবহার

int result = (10 + 5) * 2;

এখানে Parentheses-এর ভিতরের Calculation প্রথমে হবে।

"10 + 5 = 15"

তারপর:

"15 * 2 = 30"

Result:

30

Example 3

int result = 20 / 5 * 2;

"/" এবং "*" একই Precedence-এর Operator। তাই Left থেকে Right-এ হিসাব হবে।

ধাপ:

"20 / 5 = 4"

"4 * 2 = 8"

Result:

8

Example 4

int result = 20 - 5 + 2;

"-" এবং "+" একই Precedence-এর Operator। তাই Left থেকে Right-এ হিসাব হবে।

"20 - 5 = 15"

"15 + 2 = 17"

Result:

17

মনে রাখবে

একটি Expression-এর Calculation সহজে বোঝার জন্য প্রয়োজনে Parentheses "()" ব্যবহার করবে। এতে Code পরিষ্কার হয় এবং ভুল Calculation হওয়ার সম্ভাবনা কমে।

---

09. Complete Practical Example

নিচের প্রোগ্রামে আমরা একসাথে Multiple Variable Declaration, Multiple Input, Arithmetic Operator, Type Casting এবং Increment/Decrement ব্যবহার করেছি।

#include <stdio.h>

int main()
{
    int a, b;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    printf("Addition = %d\n", a + b);
    printf("Subtraction = %d\n", a - b);
    printf("Multiplication = %d\n", a * b);
    printf("Integer Division = %d\n", a / b);
    printf("Decimal Division = %.2f\n", (float)a / b);
    printf("Remainder = %d\n", a % b);

    a++;

    printf("After Increment = %d\n", a);

    b--;

    printf("After Decrement = %d\n", b);

    return 0;
}

Input:

10 3

Output:

Enter two numbers: 10 3
Addition = 13
Subtraction = 7
Multiplication = 30
Integer Division = 3
Decimal Division = 3.33
Remainder = 1
After Increment = 11
After Decrement = 2

---

10. Quick Revision

Topic| মনে রাখার বিষয়
Multiple Declaration| একই লাইনে একাধিক Variable Declare করা যায়
Multiple Initialization| একই লাইনে একাধিক Variable-এর Value দেওয়া যায়
Multiple Input| একটি "scanf()" দিয়ে একাধিক Input নেওয়া যায়
"+"| যোগ
"-"| বিয়োগ
"*"| গুণ
"/"| ভাগ
"%"| ভাগশেষ
Integer Division| দশমিক অংশ বাদ পড়ে
Type Casting| Data Type পরিবর্তন করা
"++"| Value এক বৃদ্ধি
"--"| Value এক হ্রাস
Pre-Increment| আগে বৃদ্ধি, পরে ব্যবহার
Post-Increment| আগে ব্যবহার, পরে বৃদ্ধি
Pre-Decrement| আগে হ্রাস, পরে ব্যবহার
Post-Decrement| আগে ব্যবহার, পরে হ্রাস
Precedence| কোন Operator আগে কাজ করবে তা নির্ধারণ করে
Parentheses| "()" এর ভিতরের Calculation আগে হয়

---

11. Practice Questions

Part A: Basic Practice

1. একই লাইনে তিনটি Integer Variable Declare করো।
2. একই লাইনে তিনটি Variable Initialize করো: "10", "20", "30"।
3. "scanf()" ব্যবহার করে একই লাইনে দুইটি Integer Input নাও।
4. দুইটি সংখ্যা Input নিয়ে Addition, Subtraction, Multiplication এবং Division বের করো।
5. দুইটি সংখ্যা Input নিয়ে তাদের ভাগশেষ বের করো।

Part B: Output Prediction

নিচের Code-এর Output কী হবে?

Question 1

int a = 5, b = 2;
printf("%d", a / b);

Question 2

int a = 5;
printf("%d\n", a++);
printf("%d", a);

Question 3

int a = 5;
printf("%d\n", ++a);
printf("%d", a);

Question 4

int result = 10 + 5 * 2;
printf("%d", result);

Question 5

int result = (10 + 5) * 2;
printf("%d", result);

Part C: Problem Solving

1. দুইটি সংখ্যা Input নিয়ে তাদের গড় (Average) বের করো। Decimal Result পাওয়ার জন্য Type Casting ব্যবহার করো।
2. একটি সংখ্যা Input নিয়ে তার Square এবং Cube বের করো।
3. একটি সংখ্যা Input নিয়ে সেটি Even নাকি Odd নির্ণয় করো। (Hint: Modulus Operator)
4. দুইটি সংখ্যা Input নিয়ে বড় সংখ্যাটি বের করার জন্য Arithmetic Calculation এবং Comparison সম্পর্কে চিন্তা করো। Comparison Operator আমরা পরবর্তী ক্লাসে শিখব।

---

Class 05 – Final Reminder

আজকের ক্লাসের মূল উদ্দেশ্য ছিল একাধিক Variable ও Input নিয়ে সহজে কাজ করা, Arithmetic Calculation বোঝা, Integer Division-এর সমস্যা সমাধান করা, Type Casting ব্যবহার করা, Increment/Decrement এবং Operator Precedence বুঝতে শেখা।

C Programming শেখার সবচেয়ে ভালো উপায় হলো প্রতিটি Example নিজে Code করে Run করা এবং Output আসার আগে নিজে অনুমান করা।

NUB COMPUTER CLUB
C Programming Foundation Course