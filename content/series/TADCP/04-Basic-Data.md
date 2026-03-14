+++
draft = true
title = '03 Variables, Operators, and Control Flow' 
series = ['The Art and Design of Computer Programs']
tags = ['tadcp']
+++

## Video Link

---

# Exercises



## Section 1: Variables — Boxes That Hold Data

Variables are named containers for data. Every variable in C has a name, a type, and a value. These exercises will help you get comfortable declaring, initializing, and using variables.

---

### Exercise 1.1 — Declaring and Initializing

Write a program that stores and prints information about yourself.

1. Declare an `int` variable called `age` and set it to your age.
2. Declare a `float` variable called `height_cm` and set it to your height in centimeters.
3. Declare a `char` variable called `initial` and set it to the first letter of your name.
4. Print all three values using `printf`. Your output should look like:
   ```
   Age: 25  Height: 175.50 cm  Initial: C
   ```

>  **Hint:** Each `printf` call needs a matching format specifier: `%d` for int, `%f` for float, `%c` for char.

---

### Exercise 1.2 — Variable Naming Rules

Identify which of the following variable names are valid in C. For each invalid name, explain why and write a corrected version.

1. Evaluate each name: `first name`, `2ndValue`, `_counter`, `my-variable`, `totalCost`, `float`, `MAX_SIZE`, `x`
2. For each invalid name: write what rule it breaks and suggest a valid alternative.
3. **Bonus:** Which of the valid names follow good naming conventions, and which are technically valid but poor style?

>  **Hint:** C variable names must start with a letter or underscore, contain only letters/digits/underscores, and cannot be reserved keywords.

---

### Exercise 1.3 — Swap Two Variables

Without looking up how to do it, figure out how to swap the values of two variables.

1. Declare two `int` variables: `a = 10` and `b = 25`.
2. Print their values: `Before swap: a = 10, b = 25`.
3. Swap the values so that `a` contains 25 and `b` contains 10. You will need a third variable.
4. Print again: `After swap: a = 25, b = 10`.
5. Why can't you just write `a = b; b = a;` without a third variable? Write a comment in your code explaining this.

>  **Hint:** Think about what happens step-by-step when you write `a = b`. What happens to the original value of `a`?

---

### Exercise 1.4 — The Constant Variable

Explore the difference between a variable and a constant.

1. Declare `int pi_approx = 3` and `float pi_precise = 3.14159f`.
2. Now declare a constant: `const float PI = 3.14159f;`
3. Try to change `PI` after declaring it (e.g. `PI = 4.0f;`). What error does the compiler give you? Write it down.
4. Calculate the circumference of a circle with radius 7.5 using `circumference = 2 * PI * radius`. Print the result.
5. Why is using a named constant better than writing `3.14159` directly in your formula? Write a comment explaining.

---

### Exercise 1.5 — Memory Size Exploration

C variables take up physical space in memory. Investigate how much.

1. Use the `sizeof()` operator to print the size (in bytes) of each type: `char`, `int`, `float`, `double`, `long`, `long long`.
2. Format your output as a table:
   ```
   Type: int    Size: 4 bytes
   ```
3. Calculate: if you have an array of 1,000 `double`s, how many bytes of memory would it use? Print this.
4. **Research question** (write your answer as a comment): why might `sizeof(int)` differ between a 32-bit and 64-bit system?

>  **Hint:** `sizeof()` can be used like a function: `sizeof(int)` or `sizeof(myVariable)`. Use `%zu` as the format specifier for its return type.

---

## Section 2: Input & Output — Talking to Users

`printf()` sends data to the screen. `scanf()` reads data from the keyboard. Together they let your program have a conversation. These exercises build comfort with both — and with the quirks that catch beginners off guard.

---

### Exercise 2.1 — Formatted Output

`printf()` is more powerful than it looks. Explore its formatting options.

1. Print an integer right-aligned in a field 10 characters wide: use `%10d` with value `42`.
2. Print a float with exactly 2 decimal places: use `%.2f` with value `3.14159`.
3. Print a string left-aligned in a field 15 characters wide: use `%-15s`.
4. Combine them: print a "receipt" with item name, quantity, and price. Each column should be aligned.

>  **Hint:** Format specifiers can include width and precision: `%8.2f` means "width 8, 2 decimal places."

---

### Exercise 2.2 — Basic User Input

Build a program that asks the user for their initials and age, then greets them.

1. Prompt `Enter your first initial:` and read a single `char` using `scanf("%c", &initial);`
2. Prompt `Enter your age:` and read an `int`.
3. Print a greeting: `Hello, C! You are 25 years old.` (replacing `C` and `25` with the user's input)
4. Run your program and test it. What happens if someone enters letters when you ask for age?

>  **Hint:** Always put `&` before the variable name in `scanf()` — except for strings/char arrays.
> *NOTE: We will talk about scanf much later, we should avoid it for the most part in production code*

---

### Exercise 2.3 — Simple Calculator

Build an interactive two-number calculator.

1. Ask the user to enter two floating-point numbers.
2. Print the result of addition, subtraction, multiplication, and division — all four.
3. Format each result to 2 decimal places.
4. Handle the case where the user enters 0 for the second number: before dividing, check if it's zero and print `Error: division by zero` instead of crashing.
5. Sample output:
   ```
   10.00 + 3.00 = 13.00
   10.00 - 3.00 = 7.00
   10.00 * 3.00 = 30.00
   10.00 / 3.00 = 3.33
   ```

---

---

### Exercise 2.4 — Receipt Printer

Build a formatted store receipt that looks professional.

1. Ask the user to enter 3 items. For each: read a product name (single word), quantity (`int`), and price per unit (`float`).
2. Calculate the subtotal for each item (quantity × price).
3. Print a formatted receipt with columns: `Item`, `Qty`, `Unit Price`, `Subtotal` — all aligned.
4. Print a line of dashes as a separator, then the total at the bottom.
5. **Bonus:** Add an 8.5% tax calculation and print `Tax` and `Grand Total` lines.

>  **Hint:** Use `%-20s` for left-aligned strings, `%5d` for right-aligned integers, and `%8.2f` for currency amounts.

---

## Section 3: Operators — Math and Logic

C's operators let you compute, compare, and combine. The key insight: `=` means "assign", not "equals". `==` means "is equal to". This trips up almost every beginner. These exercises will make the distinction second nature.

---

### Exercise 3.1 — Arithmetic Operators

Practice all five arithmetic operators, including the one beginners forget about: `%`

1. Given `int a = 17` and `int b = 5`, calculate and print: `a+b`, `a-b`, `a*b`, `a/b`, and `a%b`.
2. Before running: predict each result on paper. Then check — were you surprised by any?
3. Now try with `float a = 17.0f` and `float b = 5.0f`. How does `a/b` change?
4. **Practical use:** Write code that determines whether a given number is even or odd using the `%` operator.

>  **Hint:** Integer division truncates: `17/5` is `3` in C, not `3.4`. The remainder `17%5` gives you what's left over: `2`.

---

### Exercise 3.2 — Comparison and Logical Operators

Comparison operators return `1` (true) or `0` (false) in C. Explore this.

1. Declare `int x = 10` and `int y = 20`. Print the result of: `x == y`, `x != y`, `x < y`, `x > y`, `x <= 10`, `y >= 20`.
2. Now test logical operators. Print the result of: `(x < y) && (x > 5)`, `(x > y) || (x == 10)`, `!(x == y)`.
3. Predict each result before running. Write your predictions as comments.
4. **Tricky question:** What does `printf("%d", x = 5);` print, and why is this different from `x == 5`? Write your answer as a comment.

---

### Exercise 3.3 — Compound Assignment Operators

Rewrite operations using shorthand compound assignment operators.

1. Start with `int score = 100`. Using only compound assignment operators (`+=`, `-=`, `*=`, `/=`, `%=`), produce the sequence: `100, 115, 110, 220, 55, 5`. Print the value after each operation.
2. Write the same sequence without compound operators (using full expressions like `score = score + 15`). Verify you get the same results.
3. Which version is easier to read? Write a comment with your opinion.
4. **Bonus:** What do the increment (`++`) and decrement (`--`) operators do? Test `i++` vs `++i` and explain any difference.

>  **Hint:** `i++` (post-increment) returns the value first, then increments. `++i` (pre-increment) increments first, then returns the value.

---

### Exercise 3.4 — Operator Precedence

Just like in math, C evaluates operators in a specific order. Get it wrong and you'll get the wrong answer silently.

1. Without running the code, evaluate each expression for `a=6`, `b=4`, `c=2`:
   - `2 + 3 * 4`
   - `a + b * c`
   - `a * b + c * a`
   - `a / b + c`
   - `a % b * c`
2. Now run the code and check your answers. Write corrections as comments for any you got wrong.
3. Add parentheses to the third expression so that the addition happens before the multiplication. What's the new result?
4. **Takeaway:** When in doubt, use parentheses. Write a comment explaining why explicit parentheses are good practice.

---

### Exercise 3.5 — Building an Expression Evaluator

Use your knowledge of all operators to solve a real problem.

A movie theater charges $12.50 per adult ticket and $8.00 per child ticket. There's a 10% group discount if the total number of tickets is 10 or more.

1. Ask the user how many adult tickets and child tickets they want.
2. Calculate: subtotal, whether discount applies (use a comparison: `totalTickets >= 10`), discount amount (if applicable), and final total.
3. Print a detailed breakdown. Format all money values to 2 decimal places.
4. Test your program with:
   - 3 adults + 2 children (no discount)
   - 8 adults + 4 children (discount applies)

---

## Section 4: Control Flow & Loops

Control flow is how programs make decisions and repeat actions. Without it, programs can only do one thing, in one order, every time. With it, programs can respond to input, repeat work, and solve complex problems.

---

### Exercise 4.1 — If/Else Chains

Write a grade classifier program.

1. Ask the user to enter a numeric score (0–100).
2. Using `if`/`else if`/`else`, print the letter grade: A (90–100), B (80–89), C (70–79), D (60–69), F (below 60).
3. Also print a message: `Passing!` or `Needs improvement.` depending on whether the grade is D or above.
4. Add input validation: if the score is below 0 or above 100, print `Invalid score` and skip the grade calculation.

---

### Exercise 4.2 — Switch Statements

Build a text-based day-of-week program using `switch`.

1. Ask the user to enter a number 1–7 (1 = Monday, 7 = Sunday).
2. Use a `switch` statement to print the day name.
3. Also print whether it's a weekday or weekend.
4. Use the `default` case to handle invalid input.
5. **Bonus:** Rewrite the same logic using `if`/`else`. Which feels more readable for this particular problem?

>  **Hint:** Group cases together for weekday/weekend: `case 1: case 2: ... case 5:` (all fall through to the same code).

---

### Exercise 4.3 — While Loop — Input Validation

Use a `while` loop to keep asking until the user enters valid input.

1. Ask the user to enter a number between 1 and 10.
2. If they enter something outside that range, print `Invalid. Try again.` and ask again.
3. Keep looping until they enter a valid number.
4. Once valid input is received, print `You entered: X` and exit.
5. Test your program by deliberately entering bad values first. Does it behave correctly?

>  **Hint:** The loop condition should check whether the input is *invalid*. The loop body should re-prompt and re-read.

---

### Exercise 4.4 — For Loops — Patterns and Sequences

For loops are perfect when you know exactly how many times to repeat.

1. Print the first 10 perfect squares (1, 4, 9, 16 ... 100). One per line, formatted as: `1^2 = 1`
2. Print a multiplication table for a number the user enters (show 1× through 10×).
3. FizzBuzz: print numbers 1 to 50. For multiples of 3 print `Fizz`, for multiples of 5 print `Buzz`, for multiples of both print `FizzBuzz`, otherwise print the number.
4. **Bonus:** Using a nested for loop, print a right triangle of asterisks 5 rows tall.

---

### Exercise 4.5 — Number Guessing Game

Combine everything: variables, input, comparison, and loops.

1. Set a secret number: `int secret = 42;`
2. Use a `while` loop to keep asking the user to guess.
3. After each guess, print `Too high!`, `Too low!`, or `Correct!` as appropriate.
4. Count the number of guesses and print it when they succeed: `You got it in 5 guesses!`
5. Add a maximum of 10 guesses — if they use all 10 without guessing correctly, reveal the answer.
6. **Bonus:** Use `rand()` and `srand(time(NULL))` to generate a random secret number between 1 and 100 each run.

---

### Exercise 4.6 — Collatz Conjecture

One of math's most famous unsolved problems — and a perfect loop exercise.

1. Ask the user to enter any positive integer.
2. Apply the Collatz rule: if the number is even, divide by 2. If odd, multiply by 3 and add 1.
3. Keep applying the rule and printing each value until you reach 1.
4. Count the number of steps taken.
5. Print: `Starting from X, it took N steps to reach 1.`
6. Test with: 6 (should take 8 steps), 27 (takes 111 steps!), and any large number of your choice.

>  **Note:** The Collatz conjecture says this always reaches 1, but mathematicians have never proven it for all numbers. Your code will empirically verify it for small inputs.

---

## Section 5: Types & Type Conversion — When Types Meet

C is a typed language — every value has a type, and mixing types has consequences. Sometimes C converts silently (implicit conversion). Sometimes you convert deliberately (explicit casting). Getting this wrong produces bugs that are notoriously hard to find.

---

### Exercise 5.1 — Integer Division Surprise

Integer division is one of the most common sources of bugs for C beginners.

1. Predict, then print: `7/2`, `7/2.0`, `7.0/2`, `7.0/2.0`. Are all four results different?
2. Calculate the average of three test scores: `int s1=85, s2=92, s3=78`. Store in a `float avg`.
3. First try: `float avg = (s1 + s2 + s3) / 3;` — print the result. Is it correct?
4. Fix it by casting: `float avg = (float)(s1 + s2 + s3) / 3;` — print again. What changed?
5. Write a comment explaining why the first version produced the wrong answer.

>  **Hint:** When C divides two ints, it throws away the decimal part before storing the result — even if you're storing into a float.

---

### Exercise 5.2 — Implicit Type Conversion Chain

When different types meet in an expression, C promotes to the "wider" type. Trace what happens.

1. For each expression, predict the type and value of the result, then verify with `printf`:
   - `5 + 2.0`
   - `'A' + 1`
   - `(int)3.9`
   - `(float)5 / 2`
   - `(int)(7.9 + 0.5)`
2. Expression `'A' + 1` may surprise you. In C, `'A'` is stored as the integer 65 (its ASCII value). What does `'A' + 1` equal?
3. Expression `(int)(7.9 + 0.5)` is a classic rounding trick. What does it do and why?

>  **Hint:** C's type promotion rules: `char` → `int` → `long` → `float` → `double`. The "wider" type wins.

---

### Exercise 5.3 — Type Casting in Practice

Explicit casting: you tell C what type conversion you want.

1. Write a program that converts a temperature from Celsius to Fahrenheit: `F = (9/5) * C + 32`.
2. First write it with all integer math. Test with C = 100. What do you get? (It will be wrong.)
3. Fix it: cast appropriately so the arithmetic works correctly. 100°C should give 212.0°F.
4. Also implement Fahrenheit to Celsius: `C = (F - 32) * 5 / 9`.
5. Ask the user to enter a temperature and direction of conversion, then print the result to 1 decimal place.

---

### Exercise 5.4 — Integer Overflow

What happens when a number gets too big for its type? Something surprising.

1. Declare `int max = 2147483647` (the maximum value for a 32-bit int on most systems). Print `max`. Then print `max + 1`. What do you see? Write down the result and explain it.
2. Now try: `unsigned int umax = 4294967295;` Print `umax`, then `umax + 1`.
3. Declare `char c = 127` (max for signed char). Print `c`, then `c+1`.
4. Write a comment explaining the concept of overflow and why it's dangerous in real programs.
5. **Research question:** What famous software bug was caused by integer overflow?

>  **Hint:** Numbers wrap around when they exceed their type's maximum — like an odometer clicking from 99999 to 00000.

---

### Exercise 5.5 — 0.1 + 0.2 ≠ 0.3

One of programming's most famous surprises: floating point numbers are not exact.

1. Print the result of `0.1 + 0.2`. Use `%.20f` to see 20 decimal places. Is it exactly `0.3`?
2. Now write:
   ```c
   if (0.1 + 0.2 == 0.3) {
       printf("Equal");
   } else {
       printf("Not equal");
   }
   ```
   What prints?
3. Fix it: instead of checking exact equality, check if the difference is smaller than a small epsilon:
   ```c
   fabs(result - 0.3) < 0.0001
   ```
   (You'll need `#include <math.h>`)
4. Write a comment explaining why floats can't represent `0.1` exactly (think binary fractions — just like `1/3` has no exact decimal representation).

>  **Note:** This is not a bug in your code or in C. It's a fundamental property of how floating point numbers are stored in binary.

---

### Exercise 5.6 — The Type Detective

Analyze and fix a buggy program. Each bug involves a type error.

1. **Bug 1:** `int total = 0; total = total + 3.7 + 2.1; printf("%d", total);` — why does this print an unexpected value, and what's the correct approach?
2. **Bug 2:** `char grade = 'A'; printf("%d", grade);` — this actually compiles fine, but what does it print and why?
3. **Bug 3:** `int x = 1000000; int y = 1000000; printf("%d", x * y);` — what happens and why?
4. **Bug 4:** `float price = 19.99f; int cents = price * 100;` — is `cents` exactly `1999`? Check and explain.
5. For each bug: write the corrected version and a comment explaining the fix.