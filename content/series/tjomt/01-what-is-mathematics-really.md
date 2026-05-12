+++
draft          = true
title          = "What Is Mathematics, Really?"
episode_number = 1
description    = "."
youtube_url    = ""
exercises      = []
resources      = []
tags = ["the-joy-of-mathematical-thinking"]
+++


## Episode Goal

Shatter the viewer's existing mental model of mathematics and replace it with something truer. By the end, the viewer should understand that mathematics is not about numbers, formulas, or getting the right answer — it is about *reasoning precisely about abstract structures*. They should feel invited, not intimidated.

## Math Problems

When we think of math, we often think of it as being something akin to computing and solving equations and functions involving numbers.

**Consider the following problems and try to solve them if you know how:**

1. Simplify the following equation: $3y \= \\frac{2x}{y-3}$  
2. Solve for when y \= 10: $2y \= 3x \+ 7$  
3. Find the derivative, if it exists, for the following function: $f(x) \= \\frac{1}{3x^2}+\\frac{x}{5}+10$

Such problems are common in lower levels of mathematics and thus, when we think of math, we often this this is what mathematicians do every day: finding and solving larger and more complex functions and then writing about them in some fancy paper. While this might seem true based on your high school education, I want you consider the following 3 problems:

**1\. Are there more fractions or whole number? How do you know?**

We know there is an infinite number of whole numbers going in both positive and negative infinity directions. We know this because we can think of a very big number and then add one on top of that. We can do this as many times as we want. But what about fractions?

We know there are fractions between whole numbers. For example 1/10, 2/100, 3/1000, 4/10000, and so on. But wait, we can keep adding a zero to the bottom number and keep getting a smaller and smaller fraction. In fact we could add an infinite number of zeros to the bottom number and get an infinitely small fraction, all before we have even reached the number 1\!

Because there are apparently an infinite number of fractions between 0 and 1, there must also be an infinite number of fractions between 1 and 2\! In fact, you can most definitely conclude that there are an uncountably infinite number of fractions, while there are just a countable number of infinite whole numbers.

**2\. In 1700's Russia, in the city of what we now call Kaliningrad, there were seven bridges configured in such a way that it caused the famed mathematician Euler to wonder if you could cross all of them once and only one while out on a walk.**

He concluded that you couldn't, by turning the bridges into nodes in a network and creating connections between them, he realized that you had to cross one twice, or add a new node into the network in order to solve it.

**3\. What is the optimized way to pack 10 smaller squares into a single larger square?**

It turns out, it's a bit [more unusual than you think](https://en.wikipedia.org/wiki/Square_packing), but these sorts of problems have actual use in our everyday lives.A program is built from exactly three elements: primitives, combination, and abstraction. C makes all three visible by exposing the machine underneath.

### Math is about Patterns and Structures

All 6 of these problems are actually math problems, but we don't look at the last 3 problems as young students and if we do, they arrive as games or logic puzzles, but not math problems. And yet, they are math problems\! They hold just as much weight and importance in the field of mathematics as the top 3 do. In fact, if you talk to a mathematician, you might find they don't really care about the first 3 problems anywhere near as much as the last 3\!

Something you are not taught as a student, or it is not drilled into you, is that math is less about getting the "right" answer on a numbers test and far more about something abstract: patterns and hidden structures that surround our everyday lives.

When we first learn math, we are asked “What is the correct answer?” Mathematicians and those in similar fields ask “What is the truth and how do I prove it?”

To understand this, let’s look at an example from geometry:

## Geometry and Visual Proof

Let’s get a sheet of paper and draw a rectangle. Unless you are using a perfectly aligned straightedge with perfect drawing skills, you will be imperfect in your drawing skills. That is okay. At each edge label the corners A, B, C, and D. We do this to help us give names to things for when we draw things imperfectly. Is it tedious? Yes, but in light of the fact that we will never be able to truly draw the perfect rectangle, we need to describe our rectangle with words.

We know that a rectangle has 4 line segments that join such that they form right angles. We also know that a right angle is 90 degrees.


![][image1]

If you were to take the line segment $\\overline{AC}$ it would split the rectangle down the middle. Likewise, it would form two triangles.


![][image2]

We also know that we can find the area of a rectangle by multiplying the length of the rectangle by the height:  
So, we just presented a lot of information that we know to be true:

1. *Given rectangle $R \= ABCD$ and triangles $T\_1 \= ACD$ and $T\_2=ACB$*
2. *Given the area of rectangle $ABCD$ is $A\_r=l\*h$ or in other words, $A\_r \= \\overline{DC}\*\\overline{AD}$*
3. *If line segment $\\overline{AC}$ bisects rectangle R, then it stands that triangles $T\_1$ and $T\_2$ are half the area of rectangle R.*
4. *Thus, we can reasonably conclude that the areas of both $T\_1$ and $T\_2$ are ½ the area of rectangle R.*
5. *Thus, we conclude that the area of a triangle is $A \= \\frac{b\*h}{2}$*

**But, can we prove this to be true for all triangles? Let’s assume that the formula is true for all cases.**

1. *Given a triangle $EFG$ that has no set form, we can draw a line from the top to the base line segment.*  
2. *Even though we cannot find the area of triangle $EFG$, we know that it must be $\\triangle{FGH}+\\triangle{EGH}$*  
3. *We can rewrite the formula as $A\_{EFG}=\\frac{y\*h+x\*h}{2}$*
4. *Simplifying the equation, we see that $A\_{EFG}=\\frac{h(y+x)}{2}$*
5. *Notice that $x+y$ is the same thing as the base of triangle $EFG$*
6. *So we can simplify the equation to $A\_t \= \\frac{b\*h}{2}$*

**Example — The sum of the first $n$ odd numbers:**

| $n$ | Odd numbers | Sum |
|-----|-------------|-----|
| 1 | 1 | 1 |
| 2 | 1 + 3 | 4 |
| 3 | 1 + 3 + 5 | 9 |
| 4 | 1 + 3 + 5 + 7 | 16 |
| 5 | 1 + 3 + 5 + 7 + 9 | 25 |

The pattern: the sum of the first $n$ odd numbers is $n^2$. Arithmetic tells you this is true for $n = 1, 2, 3, 4, 5$. Mathematics asks: *Is this always true? Can I be certain it works for $n = 1{,}000{,}000$?*

(Don't prove it yet — that's Episode 11, induction. Just plant the question.)

### Manim Animation Candidate: Odd Numbers as L-Shaped Gnomons

Animate a growing square grid. Each new "layer" of dots forms an L-shape (a gnomon) around the existing square. The first gnomon has 1 dot. The second has 3 dots. The third has 5 dots. Each gnomon is an odd number, and together they build a perfect square. This is a *visual proof* — the sum of the first $n$ odd numbers is $n^2$ because odd numbers are the shapes that grow squares.

### Segment 2: What Mathematicians Actually Do (5 minutes)

Mathematicians do four things:

1. **Define** — they create precise definitions for the objects they study.
2. **Conjecture** — they propose statements that might be true.
3. **Prove** — they construct airtight arguments that a statement *must* be true.
4. **Connect** — they find surprising links between seemingly unrelated ideas.

**Example of precision in definitions:**

Ask the viewer: "What is a circle?" Common answers: "A round shape," "Something with no corners," "A ring."

The mathematical definition: A circle is the set of all points in a plane that are equidistant from a given point. Every word is load-bearing: *set of all points* (not the interior — that's a disk), *in a plane* (not a sphere), *equidistant* (exactly one distance, not "roughly"), *from a given point* (the center, which is not itself on the circle).

This level of precision isn't pedantry — it's what makes mathematical reasoning possible. Imprecise definitions create ambiguity, and ambiguity makes proof impossible.

### Segment 3: Why This Matters for Computer Science (3 minutes)

Brief preview (not a full argument — that's Episode 35). The theory of computing is built on definitions and proofs:

- A *Turing machine* is defined with the same precision as a circle — every component specified exactly.
- The statement "the halting problem is undecidable" is not an opinion or an observation. It's a *theorem*, proved with a logical argument that has been unassailable for 90 years.
- When a computer scientist says "this problem is NP-complete," they mean something precise, provable, and consequential — not a vague claim about difficulty.

The viewer's goal in this series: learn the language and practice of precise reasoning so that when they encounter these ideas in the Theory of Computing, they can engage with them as participants, not spectators.

### Segment 4: The Emotional Landscape (3 minutes)

Address the viewer directly. Many adults carry math trauma — a teacher who said they weren't a "math person," a class where they fell behind and never caught up, a belief that mathematical ability is innate.

Counter this directly: mathematical reasoning is a *skill*, like writing or cooking. It can be learned by anyone willing to practice. It feels uncomfortable at first — the discomfort of thinking carefully about something that doesn't yield immediately is *the actual experience of doing mathematics*, not a sign of failure.

The series will move slowly and explain everything. The viewer's job is to *engage actively* — pause, think, try problems, and not just passively watch.

## Example Problems for On-Screen Demonstration

### Problem 1: The Locker Problem

There are 100 lockers in a row, all closed. Student 1 opens every locker. Student 2 toggles every 2nd locker. Student 3 toggles every 3rd locker. ... Student 100 toggles the 100th locker. Which lockers are open?

**Why this problem is good here:** It's accessible (no prerequisites), it resists brute force (you *could* track all 100 lockers, but that's miserable), and the answer is surprising: exactly the perfect squares ($1, 4, 9, 16, 25, \ldots, 100$). A locker ends up open if and only if it was toggled an odd number of times, and a number has an odd number of divisors if and only if it's a perfect square (because divisors pair up, except when $d = n/d$, i.e., $d^2 = n$). This is a *mathematical* insight, not a computational one.

### Problem 2: Handshake Lemma Preview

At a party, is it possible for every person to shake hands with exactly 3 other people if there are 7 people at the party?

**Why this problem is good here:** The answer is no — because the sum of all handshakes must be even (each handshake is counted twice), but $7 \times 3 = 21$ is odd. This is an easy-to-state problem whose solution requires *reasoning about structure*, not calculation. It also foreshadows graph theory (Episode 27–28 of this series).

## Closing (1–2 minutes)

Recap the three-level distinction: arithmetic (compute), pattern recognition (conjecture), proof (certainty). The series teaches the third level. Next episode: the raw material of mathematical reasoning — *statements*.

