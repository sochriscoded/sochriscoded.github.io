+++
draft = false
title = '02 Matricies in Linear Systems' 
series = ['Linear Algebra For NonMath People']
tags = ['Linear Algebra']
[params]
math = true
+++

## Matrices Makes Things Simpler!

Let's look at a new linear system: 

$$\begin{cases}-\frac{1}{2}x + 3y + \frac{1}{8}z = \frac{17}{2} \\ 5x + 12y - 8z = 14 \\ x + 2z = 10 \end{cases}$$

While this is pretty trival and graphing it is no issue now thanks to 3d calculators, its difficult to envision a 4th or 5th dimension in which to find the point. From about here, we need to start to look at our linear equations strictly as that. But having all of these extra letters and operators tend to get in the way of our math, as what we are really doing our math on isn't our unknown variables, rather we are doing the math on the *coefficients* next to the variables.

Thus, its a lot easier to reduce down our system into a **matrix**: 

$$ \begin{bmatrix} -\frac{1}{2} & 3 & \frac{1}{8} &\bigm| & \frac{17}{2} \\ 5 & 12 & - 8 &\bigm| & 14 \\ 1 & 0 & 2 &\bigm| & 10 \end{bmatrix}$$

We have the coefficients from the left hand of our equation on the left side of the line, and the coefficients of right hand on the right side. This form is called an **augmented matrix**, but the standard form for a matrix is only including the left hand side. 

$$ \begin{bmatrix} -\frac{1}{2} & 3 & \frac{1}{8} \\ 5 & 12 & - 8 \\ 1 & 0 & 2 \end{bmatrix}$$

Notice we also include a $y$ coefficient as 0, to denote that there is no y variable in the 3rd equation. This will be helpful later on in this series as we look at patterns that arise from doing what we are doing now.

Moving forward, we can start to solve our matrix:

1. We can multiply our first row by a **scalar** or a whole number. Why does this work? *Because we can always undo it to return to our original row values and thus our original equation*. Without getting too complex, we can prove this is true by trying it with each number in the first row:

$$-1/2 * 8 = -4 \\ -4/8 = -1/2$$

Let's try it with 3:

$$ 3 * 8 = 24$$ $$ 24/8 = 3$$

And 1/8

$$ \frac{1}{8} * 8 = 1$$ $$ 1/8 = 1/8$$

The one thing you **Can Not** forget is to make sure to also do it to the entire equation: 

$$ \frac{17}{2}8 = 68$$ $$ \frac{68}{8} = \frac{17}{2}$$

While this isn't a "proof" per se in the rigorous mathematics sense, it is enough to hopefully demonstrate that this rule is true, *so long as you apply it to the whole equation and/or the whole row*.

Our matrix now looks like this:

$$ \begin{bmatrix} -4 & 24 & 1 &\bigm| & 68 \\ 5 & 12 & - 8 &\bigm| & 14 \\ 1 & 0 & 2 &\bigm| & 10 \end{bmatrix}$$

Next, we should want to isolate our x variable. Remember: 1 in a matrix means you have a variable by itself (for example: $ [1] = 1x = x$). We can move the order of our rows around and it will change nothing about the system at all: 

$$ R_1 \longleftrightarrow R_3$$

$$ \begin{bmatrix} 1 & 0 & 2 &\bigm| & 10 \\ 5 & 12 & - 8 &\bigm| & 14 \\  -4 & 24 & 1 &\bigm| & 68 \end{bmatrix}$$

That $ R_1 \longleftrightarrow R_3$ Is just a shorthand way of saying what operations we are doing. $R_1$ tells us the row we are working with, in this case the first row, the $\longleftrightarrow$ tells us that we are moving a row around (or **interchanging** a row), and $R_3$ tells us we are moving our current row 1 to row 3 and vice versa.

For the previous operation (8 times Row 1) the operation shorthand would be $8*R_1$ and taken together, the current row operations would be: 

$$ 8 * R_1 \\ R_1 \longleftrightarrow R_3 $$

With our new rows, we now need to get rid of x in the other 2 rows. We do this through **Row Replacement**.

Row replacement seems tricky, but it isn't. it is multiplying a row by a constant we'll call $k$ and adding it to another row. The row operation short hand looks like this:

$$ R_i \rightarrow R_i + kR_j $$

Let's try this on the second row ($R_2$) and then show why this works without destroying the equations in our matrix:

We want to get rid of 5, so we need to multiply row 1 by -5:

$$ kR_1 = [-5, -10 | - 50]$$ 

Then add (or subtract in this case) our modified first row to our second row:

$$ R_2 - kR_1 = [0, 12, -18 | -36]$$

and voila! We have the matrix:

$$\begin{bmatrix} 1 & 0 & 2 &\bigm| & 10 \\ 0 & 12 & - 18 &\bigm| & -36 \\  -4 & 24 & 1 &\bigm| & 68 \end{bmatrix}$$

**But again, why does this work?**

This works because we are **preserving our solution set**. Go back to the 2-equation system we worked on. Using the answers we came to, we can create any equation we want that satisfies the solution. *If the solution remains the same, then we can use it in our system.* Second, *any manipulation done on the entire row (not just part of it), preseves our solution set.* And finally, *because of this, we can undo our work and arrive at the original equation.*

To keep it simple: 

- Row replacement is like elimination. You use one equation to simplify another, but you’re not changing what solutions exist.

- Row scaling is like writing the same equation louder or softer.

- Row interchange is just reordering.

Back to our problem, we now need to do the same thing to row 3:

$$ R_3 \rightarrow R_3 +4R_1$$
$$ R_3 + 4([1, 0, 2 | 10])$$
$$ R_3 + [4,0,8,|40]$$
$$ [-4, 24, 1 | 68] + [4,0,8|40]$$
$$ R_3 \rightarrow [0,24,8|108]$$

And we now have the following matrix:

$$\begin{bmatrix} 1 & 0 & 2 &\bigm| & 10 \\ 0 & 12 & - 18 &\bigm| & -36 \\  0 & 24 & 8 &\bigm| & 108 \end{bmatrix}$$

Using the same process, we can find $y$ and $z$ in the same manner:

$$R_2 \rightarrow \frac{1}{12}R_2$$
$$\begin{bmatrix} 1 & 0 & 2 &\bigm| & 10 \\ 0 & 1 & - \frac{3}{2} &\bigm| & -3 \\  0 & 24 & 8 &\bigm| & 108 \end{bmatrix}$$
$$ R_3 \rightarrow R_3 -24R_2$$
$$\begin{bmatrix} 1 & 0 & 2 &\bigm| & 10 \\ 0 & 1 & - \frac{3}{2} &\bigm| & -3 \\  0 & 0 & 45 &\bigm| & 180 \end{bmatrix}$$
$$R_3 \rightarrow \frac{1}{44}R_3$$
$$\begin{bmatrix} 1 & 0 & 2 &\bigm| & 10 \\ 0 & 1 & - \frac{3}{2} &\bigm| & -3 \\  0 & 0 & 1 &\bigm| & 4 \end{bmatrix}$$
$$R_2 \rightarrow R_2 + \frac{3R_3}{2}$$
$$\begin{bmatrix} 1 & 0 & 2 &\bigm| & 10 \\ 0 & 1 & 0 &\bigm| & 3 \\  0 & 0 & 1 &\bigm| & 4 \end{bmatrix}$$
$$R_1 \rightarrow R_1 - 2R_3$$
$$\begin{bmatrix} 1 & 0 & 0 &\bigm| & 2 \\ 0 & 1 & 0 &\bigm| & 3 \\  0 & 0 & 1 &\bigm| & 4 \end{bmatrix}$$

Thus: 
$$ x = 2, y = 3, z = 4$$

While I'm hoping I didn't need to do the arithmatic out for you, I did include each of the row transformation steps to demonstrate how you could transform each row to find the answer. In fact, we can actually plug in our x, y and z into our system to demonstrate that the rules work:

$$\begin{cases}-\frac{1}{2}x + 3y + \frac{1}{8}z = \frac{17}{2} \\ 5x + 12y - 8z = 14 \\ x + 2z = 10 \end{cases}$$
$$\begin{cases}-\frac{1}{2}(2) + 3(3) + \frac{1}{8}(4) = \frac{17}{2} \\ 5(2) + 12(3) - 8(4) = 14 \\ (2) + 2(4) = 10 \end{cases}$$
$$\begin{cases}-1 + 9 + \frac{1}{2} = \frac{17}{2} \\ 10 + 36 - 32 = 14 \\ 2 + 8 = 10 \end{cases}$$
$$\begin{cases} \frac{17}{2} = \frac{17}{2} \\ 14 = 14 \\ 10 = 10 \end{cases}$$

With all of these new ideas being thrown around like matrix, scalars, row reduction, we should take a step back in the next lesson and see what is going on visually through something we call **vector space**.


