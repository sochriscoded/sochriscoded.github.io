+++
draft = false
title = '02 Hello World'
series = ['A Guide To Go Programming']
tags = ['golang']
+++

When Go was initially designed, it was built with the intent of being a "Modern C" or a reimagining of what C would be like, had it been invented in the Year of our Lord Alan Turing, 2015.

Go is a compiled, strongly typed, multi-paradigmed, garbage-collected language that focuses on simplicity and speed rather than a vast type system, or single-paradigm behavior.

It has recieved critical acclaim as well as criticism from throughout the community but its nature has lent itself well to becoming a solid choice for backend, service-centered architecture, while remaining fast and memory-safe.

Often, if you are forever online, you might know of the debate that rages between Rust users, Go users, Haskell users, and Ocaml users, however I find these debates rather cumbersome and pointless. I live by the idea that most programming languages are good and serve their purpose well, even ABAP, which I work with professionally [see this Y Combinator forum post from 2020 to get a sense for how SAP Engineers feel about it](https://news.ycombinator.com/item?id=22247205).

With this being said, you can expect to breeze through the syntax of Go fairly quickly, but find, that like C, the complexity rests under the hood and in your own knowledge. With that out of the way, let's dive into our first Go program!

## Hello Go

Let's look at that classic first example: Hello, World!

```go
package main

include "fmt"

func main(){
  
  fmt.Println("Hello, World!")
}
```

to compile and run, save this file as `hello.go` and open the terminal. `cd` to the director/folder where your `hello.go` is located and run the following command:

```bash
go run hello.go
```

The terminal should display `Hello, World!`

the `go` command is an important part of the go programming language that we call the **go toolchain**. We can compile with `go build` and run without compiling with `go run`.

## Breaking down the code

We start with line 1: `package main`. This tells the compiler that we are putting our code into a bundle of other code files we call the `main` package. the Go compiler looks for a main package and a main method, where it will start from.

There is some pre-written, pre-packaged code that comes with the Go language, and these codes are bundled into packaged. To use them we use the `include` keyword.

next is a special **function** we call `main`. A function is a block of code that takes in some input, and can spit out an output. We'll talk more about them later but for now, just know that it exists.

On the next line, we have `fmt.Println("Hello, World!")`. `fmt` is our package of code that we are using and we are using a specific function from this code called `Println()` which takes some input (in our case `"Hello, World!"`) and turns it into some output onto the console screen.

And that's it, that is your first Go program! In the next post, we'll talk more about functions and some other things called variables and conditional logic.
