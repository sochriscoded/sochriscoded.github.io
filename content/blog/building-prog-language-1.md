+++
date = '2026-04-16T15:14:13-06:00'
draft = true
title = 'Building Prog Language 1'
+++

> "Any sufficiently advanced technology is indistigushable from magic." - Arthur C. Clarke.

Growing up I was enamored with the idea of language. The fact that people can use sounds differently from me and produce, in effect, the exact same thoughts and ideas that I can, all without my needing to understand it was both fascinating and alluring. I eventually picked up a second language in Spanish, but not before getting suckered into the world of conlanging.

Conlanging is the art of developing your own language for your own purposes. There is a whole community of language geeks and wanna-be tolkiens seeking to produce their own esperanto, their own elvish, their own world. I was at one point one such person. While my notes and work are gone, my love for language is not, it has, however evolved.

Take a moment and consider Javascript and C#. Two very different languages, each using two very different sets of paradigms to do different things. And yet, theoretically, both can be used to compute any idea. You can rewrite doom with either language. In fact, as long as your programming language is **turing complete** then you can theoretically doing anything with your language that can logically be computed.

But take a second and consider HOW such a language comes to be. What is the theory and meaning behind those languages? What makes them tick, what is the pros and cons that come from various paradigms used by programming languages? Can I make my own? Is it really that hard?


Answer: Yes.


## Building a Programming Language from Scratch


So, of course, the language bug got me again and I really want to build my own programming language. I also know that building programming languages are difficult, complex tasks, so I've broken down into general steps that will be more digestable for me to talk about and do:

### The roadmap:

#### Stage 1: Design, Philosophy, and Scope Development

Overall, this will be the longest and most detailed part of the whole project. Everything from the type system to the Language Specification Document will be produced in this stage. Overall, this stage has 8 steps:

##### Language Philosophy & Core Principles

Overall, this is the most important step. If I haven't planned out my philosophy and the why behind the what, then it really doesn't matter what I am doing. What I will get back is a bunch of garbage. No *good* language was built on a whim.

2. Type System Design

Once I have determined what my philosophy will be, I can start on the most mathematically difficult part: designing the type system. I will be doing this in a latex document using type theory/system F to coordinate and ensure my system is reasonabily sound (this has never stopped a programming language developer before!) but since I'm a goofy mathhead, I like writing latex papers and there's a rush in building out mathematically rigerous type systems, even if the end result is a bunch of incomprehensible heiroglyphs only legible to the clinically insane.

3. Syntax Design

The fun part! This is where I will be determining the look and feel of the language. I will use Bakus-Naur Form for this specification, so it too will be in a latex document (more math!) but I will have examples mockups to demonstrate how it will look and feel.

4. Module & Package System

A core feature of any modern language is a module or package system, so I will have to plan that out before I actually start work, let I wind up with something C-like that doesn't fit the modern standard (it is okay though, C is still the GOAT.)

5. Concurrency & I/O Model

Same as above. Welcome to the future kid, everything is threaded in the future!

6. Standard Library Scope

Yeah, you need one.

7. Tooling & Developer Experience Plan

I hate my developers so I will make them use an SAP GUI-like experience! I kid, I will have to plan and build an LSP for good development. Maybe a REPL. Who knows.

8. Language Specification Document

And the final part of this stage is making sure the actual nerds have a reference document to look at