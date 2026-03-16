+++
draft          = true
title          = "Functions"
episode_number = 5
description    = "Defining, calling, and reasoning about functions in C."
youtube_url    = ""
exercises      = []
resources      = []
tags           = ["tadocp"]
+++

## Video Link

---

# Exercises

Functions are the fundamental unit of organization in C. They let you name a piece of logic, reuse it, and think about your program in manageable chunks. Getting comfortable with how functions work, how they receive data, what they can see, and how they can call themselves is one of the most important steps in learning to write real programs.

---

## Section 1: Defining and Calling Functions

---

### Exercise 1.1 Your First Function 

Move logic out of `main()` and into a dedicated function.

1. Write a function called `greet` that takes no parameters and returns nothing (`void`). It should print `Hello from a function!`
2. Call it from `main()`.
3. Now modify `greet` to accept a `char` parameter called `initial`, and print `Hello, C!` using that initial.
4. Call the new version from `main()` passing your own initial.

---

### Exercise 1.2 Functions That Return Values 

A function that computes something and hands the result back.

1. Write a function `square` that takes one `int` parameter and returns its square as an `int`.
2. Write a function `cube` that takes one `int` parameter and returns its cube as an `int`.
3. In `main()`, ask the user to enter a number. Print its square and cube using your two functions.
4. Now write a third function `power` that takes two `int` parameters a base and an exponent and returns the result of raising base to that exponent using a loop. (Do not use `pow()` from `math.h`.)

>  **Hint:** `power(2, 8)` should return 256. Think through the loop: start at 1 and multiply by base, exponent times.

---

### Exercise 1.3 Functions With Multiple Parameters 

Practice writing functions that take several inputs and produce a single result.

1. Write a function `add` that takes two `int` parameters and returns their sum.
2. Write a function `max_of_two` that takes two `int` parameters and returns whichever is larger.
3. Write a function `clamp` that takes three parameters `value`, `min_val`, `max_val` and returns `value` if it's within the range, `min_val` if it's below, or `max_val` if it's above.
4. In `main()`, test `clamp` with: `clamp(5, 1, 10)`, `clamp(-3, 1, 10)`, and `clamp(15, 1, 10)`. Print all three results.

---

## Section 2: Passing by Value

---

### Exercise 2.1 Observing Pass by Value 

C passes arguments *by value* functions receive a copy, not the original. See this for yourself.

1. Write a function `double_it` that takes an `int` parameter `n`, multiplies it by 2, and prints the result inside the function.
2. In `main()`, declare `int x = 7`. Print `x` before calling `double_it(x)`, then print `x` again after.
3. Did `x` change? Write a comment explaining what you observe and why.
4. Now modify `double_it` to *return* the doubled value instead of printing it. In `main()`, write `x = double_it(x)` and print `x` again. What's different this time?

>  **Key idea:** When you call `double_it(x)`, C copies the value of `x` into the parameter `n`. The function works on that copy. The original `x` in `main()` is untouched unless you explicitly assign the return value.

---

### Exercise 2.2 The Broken Swap 

This exercise demonstrates a very common beginner mistake and why it happens.

1. Write a function `swap` that takes two `int` parameters `a` and `b`, and swaps their values inside the function. Print `a` and `b` at the end of the function to confirm the swap worked.
2. In `main()`, declare `int x = 10, y = 99`. Print them before calling `swap(x, y)`, then print them again after.
3. Did `x` and `y` swap? Write a comment explaining the result.
4. This is a deliberate demonstration of a limitation. Write a comment describing what you would need to learn (look ahead: *pointers*) to make a swap function that actually modifies the caller's variables.

---

### Exercise 2.3 Tracing Function Calls 

Read this code carefully and trace its execution *before* running it.

```c
#include <stdio.h>

int mystery(int a, int b) {
    a = a + b;
    b = a - b;
    a = a - b;
    return a;
}

int main(void) {
    int x = 4;
    int y = 9;
    int result = mystery(x, y);
    printf("x=%d y=%d result=%d\n", x, y, result);
    return 0;
}
```

1. On paper, trace the execution line by line. What does `mystery` return? What are the final values of `x` and `y`?
2. Run the program and check your answer.
3. What does `mystery` actually do? Give it a more descriptive name and write a comment explaining it.
4. Notice that `x` and `y` in `main()` were not affected by the operations inside `mystery`. Write a comment confirming this and explaining why.

---

## Section 3: Function Prototypes

---

### Exercise 3.1 The Order Problem 

Without prototypes, the order you define functions in your file matters until it doesn't.

1. Write a program *without* prototypes where `main()` appears at the *bottom* of the file, after `square` and `greet`. Verify it compiles and runs correctly.
2. Now move `main()` to the *top* of the file, above `square` and `greet`. Try to compile. What error do you get? Write it down.
3. Fix it by adding prototypes for `square` and `greet` at the top of the file (before `main()`).
4. Write a comment explaining what a prototype tells the compiler.

>  **Hint:** A prototype is just the function's signature followed by a semicolon: `int square(int n);`

---

### Exercise 3.2 Writing a Prototype-First Program 

Professional C code is often written prototype-first. Practice this style.

1. At the top of your file (after `#include` statements), write prototypes for *all* functions before writing any of their definitions.
2. Implement these three functions in any order you like:
   - `int celsius_to_fahrenheit(int c)` converts Celsius to Fahrenheit
   - `int fahrenheit_to_celsius(int f)` converts Fahrenheit to Celsius
   - `void print_conversion_table(void)` prints a table of Celsius values from 0 to 100 in steps of 10, with their Fahrenheit equivalents
3. Call all three from `main()`. The table function should call `celsius_to_fahrenheit` internally.
4. Notice that with prototypes, the order of function *definitions* in the file doesn't matter at all.

---

### Exercise 3.3 Prototype Parameter Names 

Parameter names in prototypes are optional. Explore this.

1. Write a prototype for a function `rectangle_area` that takes two `int` parameters. Write it *with* parameter names: `int rectangle_area(int width, int height);`
2. Write the same prototype *without* parameter names: `int rectangle_area(int, int);`
3. Both are valid C. Implement the function and verify both prototype styles work.
4. Write a comment: which style is more readable, and when might you prefer each?

---

## Section 4: Empty Parameter Lists

---

### Exercise 4.1 void vs. Empty 

In C, there's a meaningful difference between `f(void)` and `f()`. This exercise makes it concrete.

1. Write a function declared as `void say_hello()` (empty parameter list). Call it from `main()` with no arguments it works fine.
2. Now try calling it with an argument: `say_hello(42)`. What happens? Does it compile?
3. Rewrite the declaration as `void say_hello(void)`. Try calling it with `say_hello(42)` again. What happens now?
4. Write a comment explaining the difference: in older C, `f()` means "I'm not telling you what parameters this takes." `f(void)` means "this function takes *no* parameters."

>  **Key point:** Always use `void` in the parameter list for functions that take no arguments. It's explicit and prevents accidental misuse.

---

### Exercise 4.2 Applying the Convention 

Audit your earlier code from this exercise set.

1. Look back at every function you've written so far that takes no parameters. Check: did you write `f()` or `f(void)`?
2. Update any that use `()` to use `(void)` instead.
3. Recompile everything and confirm nothing broke.
4. Write a comment that you'll carry forward: *all no-parameter functions in C should be declared with `(void)`.*

---

## Section 5: Block Scope

Understanding scope where a variable is visible and how long it lives is essential to avoiding confusing bugs.

---

### Exercise 5.1 Where to Define Variables 

Variables should be declared close to where they're first used, not all at the top of a function.

1. Write a function that asks the user for two numbers and prints their sum, difference, and product.
2. First version: declare *all* variables at the top of the function (old-school C style).
3. Second version: declare each variable just before you first need it.
4. Which version is easier to read? Write a comment with your reasoning.

>  **Note:** Declaring variables at the top was *required* in older C standards (C89). Modern C (C99 and later) allows declarations anywhere in a block and most style guides prefer them close to first use.

---

### Exercise 5.2 Variables Don't Escape Their Block 

A variable declared inside a block `{}` only exists inside that block.

1. Write this code and try to compile it:

```c
#include <stdio.h>

int main(void) {
    int x = 10;

    {
        int y = 20;
        printf("Inside block: x=%d, y=%d\n", x, y);
    }

    printf("Outside block: x=%d\n", x);
    printf("Outside block: y=%d\n", y); /* Does this work? */
    return 0;
}
```

2. What error do you get on the last `printf`? Write it down.
3. Remove the offending line, recompile, and confirm it runs.
4. Write a comment explaining: what is a "block" in C, and what does it mean for a variable to be "in scope"?

---

### Exercise 5.3 Variable Hiding 

An inner block can declare a variable with the same name as one in an outer block. The inner one "hides" the outer one.

1. Write and run this program:

```c
#include <stdio.h>

int main(void) {
    int x = 1;
    printf("Outer x: %d\n", x);

    {
        int x = 2;
        printf("Inner x: %d\n", x);

        {
            int x = 3;
            printf("Innermost x: %d\n", x);
        }

        printf("Inner x again: %d\n", x);
    }

    printf("Outer x again: %d\n", x);
    return 0;
}
```

2. Before running: predict every line of output.
3. Run it and check your predictions.
4. Write a comment: is variable hiding good or bad practice? When might it cause bugs?

>  **Key point:** Each `int x` is a completely separate variable. The inner one doesn't modify the outer one it simply makes it temporarily invisible. Many style guides recommend *against* variable hiding precisely because it's confusing.

---

### Exercise 5.4 File Scope 

A variable declared outside of any function has *file scope* every function in the file can see it.

1. Declare a global `int call_count = 0;` at the top of your file, outside any function.
2. Write a function `tracked_add(int a, int b)` that increments `call_count` each time it's called, then returns `a + b`.
3. In `main()`, call `tracked_add` five times with different inputs. After all calls, print: `tracked_add was called 5 times.`
4. Now write a second function `reset_count(void)` that sets `call_count` back to 0. Call it and verify the counter resets.
5. Write a comment: what's the risk of using global variables? Why do most experienced programmers minimize their use?

>  **Key point:** Global variables are visible and *modifiable* by any function. This makes them convenient but dangerous any function can change them, often in ways that are hard to trace.

---

### Exercise 5.5 for-loop Scope 

In C99 and later, a variable declared in a `for` loop header only exists for the duration of that loop.

1. Write a `for` loop that declares `int i` in its header: `for (int i = 0; i < 5; i++)`.
2. After the loop, try to print `i`. What error do you get?
3. Compare with declaring `int i` *before* the loop. Now can you print `i` after the loop? What value does it have?
4. Write two versions of a program that sums the numbers 1 to 10 one where `i` is declared in the loop header, and one where it's declared before. Write a comment: which approach is preferable, and why?

>  **Hint:** Declaring `i` in the loop header is almost always better it makes clear that `i` only matters inside the loop and prevents accidentally reusing a stale loop variable.

---

### Exercise 5.6 Scope Bug Hunt 

Find and fix all the scope-related bugs in this program. There are four.

```c
#include <stdio.h>

int total;

void add_to_total(int amount) {
    int total = total + amount;
    printf("Added %d, total is now %d\n", amount, total);
}

int compute(int x) {
    if (x > 10) {
        int result = x * 2;
    }
    return result;
}

int main(void) {
    total = 0;
    add_to_total(5);
    add_to_total(3);

    for (int i = 0; i < 3; i++) {
        int running = 0;
        running += i;
    }
    printf("Running total: %d\n", running);

    printf("Compute(15): %d\n", compute(15));
    printf("Compute(5): %d\n", compute(5));

    return 0;
}
```

1. Identify each bug. For each one, write: what the bug is, why it's a bug, and how to fix it.
2. Fix all four and confirm the program compiles and behaves correctly.
3. **Bonus:** The `compute` function has an additional logic problem beyond the scope bug what should it return when `x <= 10`? Make a decision and handle that case.

---

## Section 6: Recursion Basics

A recursive function calls itself. Every recursive function needs two things: a **base case** (when to stop) and a **recursive case** (how to reduce the problem toward the base case). Without a base case, recursion never stops.

---

### Exercise 6.1 Countdown 

The simplest possible recursive function.

1. Write a recursive function `countdown(int n)` that prints the numbers from `n` down to 0, one per line, then prints `Liftoff!`
2. The base case: if `n < 0`, return immediately.
3. The recursive case: print `n`, then call `countdown(n - 1)`.
4. Call it from `main()` with `countdown(5)`.
5. On paper, draw the chain of calls that results from `countdown(3)`. Show which call prints which number.

---

### Exercise 6.2 Factorial 

The classic recursive example.

1. Write a recursive function `int factorial(int n)` that returns n! (n factorial).
2. Base case: `factorial(0)` is 1.
3. Recursive case: `factorial(n)` is `n * factorial(n - 1)`.
4. In `main()`, print the factorial of 0 through 10.
5. What happens if you call `factorial(-1)`? Try it. Then add a guard: if `n < 0`, print an error and return -1.

>  **Hint:** 5! = 5 × 4 × 3 × 2 × 1 = 120. Make sure your base case returns 1, not 0 multiplying by 0 would wipe out the whole result.

---

### Exercise 6.3 Sum of Digits 

A less obvious recursive structure.

1. Write a recursive function `int sum_of_digits(int n)` that returns the sum of all digits in a positive integer. For example, `sum_of_digits(1234)` returns `1 + 2 + 3 + 4 = 10`.
2. Identify the base case: what's the simplest version of this problem?
3. Identify the recursive case: how do you peel off one digit and recurse on the rest?
4. Test with: `sum_of_digits(0)`, `sum_of_digits(7)`, `sum_of_digits(123)`, `sum_of_digits(9999)`.

>  **Hint:** The last digit of any number is `n % 10`. The number with its last digit removed is `n / 10`. When is the problem fully solved?

---

### Exercise 6.4 Fibonacci 

Fibonacci numbers are famous in both math and computer science.

1. Write a recursive function `int fibonacci(int n)` that returns the nth Fibonacci number. The sequence starts: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, ...
2. Base cases: `fibonacci(0) = 0`, `fibonacci(1) = 1`.
3. Recursive case: `fibonacci(n) = fibonacci(n-1) + fibonacci(n-2)`.
4. Print `fibonacci(0)` through `fibonacci(10)`.
5. Try `fibonacci(40)` or `fibonacci(45)`. Notice anything? How long does it take? Write a comment about why this version of Fibonacci gets slow for large inputs.

>  **Key insight:** `fibonacci(5)` calls `fibonacci(4)` and `fibonacci(3)`. But `fibonacci(4)` *also* calls `fibonacci(3)`. The same values get recomputed over and over. This is why naive recursive Fibonacci is slow but it's also what makes it a perfect introduction to a more advanced technique called *memoization*.

---

### Exercise 6.5 Power Function, Recursively 

You wrote `power` iteratively in Section 1. Now write it recursively.

1. Write a recursive function `int power(int base, int exponent)` that computes base^exponent.
2. Base case: any number to the power of 0 is 1.
3. Recursive case: `base^exponent = base * base^(exponent-1)`.
4. Compare your result against the iterative version from Exercise 1.2 with several test inputs.
5. Trace on paper: what chain of calls does `power(3, 4)` produce? How many multiplications happen?

---

### Exercise 6.6 Recursive Digit Reversal 

Combine recursion with the digit manipulation skills from Exercise 6.3.

1. Write a recursive function that *prints* the digits of an integer in reverse order. For example, given `1234`, it should print `4 3 2 1`.
2. Think carefully about the base case and what "reverse" means recursively: to reverse `1234`, you print `4`, then reverse `123`.
3. Write a separate version that *returns* the reversed number as an integer (so `reverse(1234)` returns `4321`). This one is harder think about how to weight each digit as you unwind the recursion.
4. Test both versions with: `1234`, `1000`, `9`, and `120`.

>  **Hint for the returning version:** You'll need to know the number of digits to correctly position each one. Consider writing a helper function `int count_digits(int n)` first.

---

### Exercise 6.7 Spot the Missing Base Case 

Recursive bugs are particularly nasty because they don't just produce wrong answers they crash your program.

Analyze each of the following functions. For each one: identify whether it has a valid base case, predict what will happen when called, and write a corrected version.

**Function A:**
```c
int countdown(int n) {
    printf("%d\n", n);
    return countdown(n - 1);
}
```

**Function B:**
```c
int factorial(int n) {
    return n * factorial(n - 1);
}
```

**Function C:**
```c
int sum_to(int n) {
    if (n == 0) return 0;
    return n + sum_to(n + 1);
}
```

**Function D:**
```c
int power(int base, int exp) {
    if (exp == 0) return 1;
    if (exp < 0) return 0;
    return base * power(base, exp - 1);
}
```

1. For each function: does it have a base case? Will it terminate for typical inputs?
2. Function D is different from the others is it correct? Is it a good way to handle negative exponents?
3. Fix Functions A, B, and C. For Function D, write a comment on whether its handling of negative exponents is mathematically reasonable.

---