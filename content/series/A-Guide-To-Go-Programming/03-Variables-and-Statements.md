+++
draft = false
title = '03 Variables and Statements'
series = ['A Guide To Go Programming']
tags = ['golang']
+++
## Introduction

I want you to imagine a person who has the ability to retain any and all information but cannot reason about it. They could say the words "blue", "The Thames", "Budapest" and know that those words existed. They could recall facts and figures but those facts, figures, and words would mean nothing. Without the ability to reason about things (which is what we call abstraction), we are useless. And as absurd to us this might feel to us thinking abstracting, reasoning, logic-ing humans, this is actually how a computer works. At their core, computers retain data in simple groups of 1s and 0s, called **bytes**, and these bytes something like this: `00101101`. That's it. That's a byte. It doesn't tell you what it is or why it even matters. It exists without any other context.

To be able to really use this data and classify it, in other words, in order to give computers the ability to reason with our data, we need to give it **types**. Think of types as a label, a way to let our computer know what it is working with and how it should be treated. By assigning types, we can achieve a level of **abstraction** that allows us to model data and real-world events in our computer.

Of course, the theory and concepts behind types can get pretty complex and mathematical rather quickly, so we'll just keep it high-level for now. But just know that types are very important part of how our programming langauages work.

### How Data is Classified, How Data is Stored

For us to be able to use data, we need to be able to give it a place to exist and we need to classify it. Now, if you've programmed in other languages, you might be thinking: "wait, python doesn't require me to use types, neither does javascript, so you must be wrong." The sneaky truth is, they do use types, they just assign them at runtime during evaluation, rather than evaluating them during the compilation process.

In Go, we have to assign our types to everything we want to keep around. The easiest way to do this is through variables

## Variables

When I was teaching, I liked to bring a box and then I would put things into the box, give the box a label, and boom, that was a variable. I still believe this is a pretty apt description for a variable: "A variable is a primative data structure that hold *something*" Is it specific? No, but you'll see what I mean over the next several videos. Let's start with the most basic variables:

### Basic Variables

```go
  var myNumber int = 42

  var name, phrase string

```
This can be seen as the "classic" way of creating (or **declaring**) variables. Variables are initialized with the keyword `var`, then they are given a name, then they are given a type. In one example, they are given a value immediately, and in another, that value will be given later. Regardless, they are declared before they are used.

There's another way to declare a variable and it looks like this: 

```
myNumber := 42

```

This is the same thing as above, but it shortens down the declaration and assignment into one concince `:=` operator. You'll see these all the time in Go, so get used to them.

### Variable Types

#### Basic Types

```
bool

string

int  int8  int16  int32  int64
uint uint8 uint16 uint32 uint64 uintptr

byte // alias for uint8

rune // alias for int32
     // represents a Unicode code point

float32 float64

complex64 complex128

```

### Picking Types

When picking a type for a variable, we need to think about what it is we are wanting to do? Do we want to store a list of characters (also known as a string?) Do we want a single character (known in go as a rune), or do we need a number? While Go's type system is limited, other languages like rust or ABAP will have a large and robust type system, which fits the needs and design of Rust and ABAP.

### Constants and Reassigning Values

When we use a variable like so:

```
example := 32

example = 42
```

We are doing something like reassigning values to variables. Again, thing of it like a box. If you have a box that's meant to hold CDs, then you can add or remove CDs, so long as they aren't DVDs or records.

However, there's a specific kind of variable that never changes: constants. Constants don't vary in size, they stay the same permanently and can never be changed during runtime or compliation of the program. 

PUT EXAMPLE HERE


### Formatting Output

## Logic: Making Variables Do Stuff

If you've ever had the pleasure of driving in the Dallas-Forth Worth Metroplex, then you might have encountered the "special" highway interchange system where the roads to Houston, Austin, Amarillo, Oklahoma City, Shreveport, Dallas, Fort Worth, Little Rock, Abeline, and others converge. In short, it is a hot mess of spaghetti roads, crossovers, traffic, and signage.

Our computers are more often than not similar to this. Think of data flowing on a pathway, a stream of 1s and 0s. How it does that is determined by control flow and logic. We programmers have the ability to determine and create this control flow in our code through several means:

Booleans

AND, NOT and OR

If, Else, Switch and Case

and Loops

### Breakin 2: Electric "Bool"galoo

### AND, NOT, and OR Can Get You Pretty Far


### Me >= You

### If and Else

### Switch and Case

### Looping Again and Again and Again and Again

#### Continue and Break
