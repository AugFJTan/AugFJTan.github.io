---
layout: post
title:  "Syntax, Semantics and Pragmatics"
description: "An article about the linguistics of programming languages."
date:   2017-08-21 09:42:00 +0800
categories: programming
---

Most mainstream programming languages centre around the English language. Even so, the fact that the code of any given programming language is so detached from even a basic, grammatically correct sentence, you might as well be learning another language altogether. An [article](https://temochka.com/blog/posts/2017/06/28/the-language-of-programming.html) by Artem Chistyakov, a Russian developer, brought to my attention the inherent difficulty of programming in these English-centric languages for non-English speakers. I was rather impressed that he and his peers managed to learn the C language... through a Russian-medium university course. As much as it was absurd to me, it was practical decision. Russia's education is taught exclusively in Russian, and its students would be more comfortable learning about programming in their mother tongue. That being said, perhaps most English-speaking programmers take for granted the fact that they can easily refer to documentation online and get what they want while their non-English speaking peers struggle to understand colloquial and technical terms that litter the vocabulary of most programmers, most notably words and phrases such as `spaghetti code`, `polymorphism`, `preprocessor directives` and so on.

Anyway, on to the topic of today's article. Much like linguistics of natural languages, programming languages (save some esoteric ones) follow a set of rules as defined by their **syntax**, **semantics** and **pragmatics**. Firstly, **syntax** is the grammar of the programming language, the way certain symbols such as `!`, `[` and `%` as well as reserved words such as `for`, `while` and `int` interact with variables and data structures. If you fail to follow the syntax (or, more often than not, miss a semicolon), the compiler will display error messages. Secondly, **semantics** is the intended meaning of the program as expressed by the code. If the the program does what the programmer wanted it to do, it is semantically correct. Many inexperienced programmers mistake semantics with syntax, thinking that just because their code managed to compile, therefore there are no problems with the executable program. (*Aside:* Wait until they learn how stupid a compiler is.) Last but not least, **pragmatics** is the practical use of syntax and semantics to express code in an understandable way. Good code is its own documentation. Pragmatic code takes that a step further by making it more elegant with lesser iterations and conditional statements, simplifying but not obfuscating the original code. Let's talk about each of these aspects in detail.

### Syntax

I am often surprised at how syntactically different each programming language is. Many languages share similar syntax (the grandfather of many modern languages is C, after all), but each has its own way of expressing fundamental programming concepts. One major influence on syntax is the paradigm (or sometimes paradigms!) the programming language utilizes. A programming paradigm is basically the approach taken (by the programmer or the language) to solve a given problem. Some examples of programming paradigms are imperative, procedural, object-oriented and functional. Understanding and applying each paradigm is challenging enough, so it would be more practical for the programmer to understand syntax first. Once he is used to the syntax, he can approach the problem using an appropriate paradigm. 

Another influence on syntax is the expressiveness of a language. C++, for example, heavily uses namespaces (particularly, the `std` namespace, unless you decide to use a `using namespace` statement). A simple `Hello World!` print statement is expressed as

```cpp
std::cout << "Hello World!" << std::endl;
```

The same statement in Java, which heavily uses classes, is expressed as

```java
System.out.println("Hello, World!");
```

Again, but in C, which is a mixture of imperative and functional, the statement is expressed as

```c
printf("Hello World!\n");
```

Then there's Python, a **very** high-level language, which is expressed as

```python
# Python 2 and below
print "Hello World!"

# Python 3
print("Hello World!")
```

Correct syntax ensures that the compiler (in the case of C and C++) or interpreter (in the case of Java and Python) "understands" the variables, functions, classes, etc. as expressed by the programmer, and handles the code accordingly. To avoid confusion, the syntax in a programming language has to be consistent throughout so that programmers can effectively write and debug their code.

### Semantics

With syntax out of the way, semantics come next. There is often a joke in the online coding community that if customers like a certain bug in the program because it does something useful, it is considered a feature! (Think of the long-time piston displacement bug in the videogame *Minecraft* that Mojang eventually managed to fix!) Bugs are unintentional product of code that is expanded upon over time. Enterprise-level programs sometimes exibit buggy behaviour not because they weren't rigorously tested, but because the bug was probably overlooked. Proper semantics ensure that the expression of the code is consistent with the intention of its executable program.

As an example, consider the following statements in C:

```c
x = y++; /* Acceptable */

++x = y++; /* Wait, what? */

array[++x] = x++; /* Oh, I give up! */
```

Just so you know, the second statement with `x++` on the left side of the `=` operator will compile, but most likely result in undefined behaviour. In short, correct semantics ensures that the meaning of the code is reflected in the program, which functions as expected.

### Pragmatics

Pragmatics is perhaps a difficult and elusive aspect of programming languages. Looking for good code examples is hard, writing good code is harder. Oftentimes, pragmatic code follows conventions such as:

- Giving meaningful names to variables
- Using clear and concise statements
- Using proper indentation

Pragmatic code is admired by other programmers for its elegance and practicality. Pragmatics varies from language to language, but ultimately its goal is to produce structured, readable and intuitive code. This can only be attained through dedication and practice.

### Conclusions

Learning about programming is one thing, learning about the theory and practical considerations behind programming is another. Programming in general has not fully matured as a process, as opposed to more established processes such as writing (literature), painting (art) and woodwork (carpentry). By discussing the syntax, semantics and pragmatics of programming languages, it is hoped that programmers may have a better dialogue on these "meta" aspects and suggest better practices that will increase the overall productivity and maintainability of future software.