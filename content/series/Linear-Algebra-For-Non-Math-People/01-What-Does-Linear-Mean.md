+++
draft = true
title = '01 What Does Linear Mean' 
series = ['Linear Algebra For NonMath People']
tags = ['linearalgebra']
[params]
math = true
+++


In the 1930's, two indepentent mathematicians, Leonid Kantorovich and Wassily Leontief were busy producing something that would be overlooked for decades: The true and practical application of linear equations in an increasingly modern, increasingly mechanical world. While their groundbreaking work was overlooked by peers like Alan Turing and John Von Neumann, both of whom would have profound impact on the world of mathematics and computer science, Kantorovich and Leontief's work would nontheless be just as important in our modern age as Turing's and von Neumann's.

By 1949, Wassily's work would finally pay off, with Dr. Leontief creating a program for the Mark II that would permanently change the way in which computers were used by economists, business professionals, and individuals who use applied mathematics. He wrote a program, mathematically rigorous but converted to the Instruction Set Language of the Mark II, that took a number of linear equations and solved the model in 52 hours. This was the first instance of a mechanical computer being able to solve such large models and while trivial for programmers today, it was a feat that would have quiet, but profound impacts on the world of economics.

Meanwhile, in the USSR, under the heel of the slowly dying Stalin and the powerstruggle that would ensue from this, Kantorovich's work would be left mostly obscure and underused. Regardless, both gentlement would share the 1973 Nobel Prize for Economics for their research into linear modeling of economics data.

## The Problem of Evil... Variables

Such problems have a number of variables. If you recall, a variable is any unknown and we usually represent them with numbers like $x$ and $y$. We can use these variables in functions like 

$$y=mx+b$$

Which is you recall is our simple formula for a linear equation, where $m$ is our *coeffecient* and $x$ is a variable. This is pretty simple and we can do all sorts of analysis on just this formula alone (which we would call pre-algebra and algebra 1). However, once we start to add in a bunch of variables, it gets pretty crazy:

$$2x + /frac{2/3}y+27z = 34$$

To help us just a tiny bit, bucause we could have more than 26 variables, let's rename $y$ and $z$ to $x_2$ and $x_3$ respectively.