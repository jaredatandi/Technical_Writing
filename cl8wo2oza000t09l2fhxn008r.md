## How to write a programming language interpreter

## Introduction
A programming language interpreter is a program that reads and executes code written in a particular programming language. The interpreter translates the code into instructions that can be understood by the computer's processor. Interpreters are usually written in a lower-level language than the source code they interpret, and they can be either compiled or interpreted themselves.

C is a versatile and powerful programming language that is widely used for developing interpreters. In this article, we will discuss how to write an interpreter with the C language in mind.

## Types of interpreters

There are two main types of interpreters: bytecode interpreters and source code interpreters. Bytecode interpreters execute programs that have been compiled into a bytecode format, which is a platform-independent machine code. Source code interpreters, on the other hand, execute programs directly from source code.

Compilers can also be used to translate source code into machine code, but they generally produce more efficient code than interpreters. This is because compilers translate the entire program into machine code all at once, before it is executed, while interpreters translate the program one line at a time as it is executed.

In this article, we will be focusing on creating a source code interpreter rather than bytecode interpreters. I may consider writing a different article for bytecode interpreters in the future.

## Lexical analysis or scanning

The first step to writing a source code interpreter is lexical analysis or scanning. This process converts the input code into a stream of tokens. Tokens are the basic units of the code. For example, a token can be a keyword, an identifier, a literal, or an operator.

A lexer often exists as a single function that is called by a parser or another lexer. Lexical analysis is the first stage of a two-stage process: first, the scanner breaks an input stream into tokens; then the parser builds up structures from those tokens. Parsing is sometimes used as a general term that covers both lexical analysis and syntax analysis.

Okay, forget the gibberish terms. In terms of C language, think of lexical analysis and scanning as the work performed by the std function `strtok`. It basically, takes an input as a "sentence" and returns an array containing the constituted words of the sentence but after removing the unwanted tokens (as seen in the next step) such as tabs, space, etc.

In this step, write a function to take inputs from the user or a file. You can also go overboard and ensure that the files are in the format that the interpreter should specify by using the ELF function. To do this, you will have to decide the entry point for all your files.

## Parsing

The second step is parsing. This process builds a data structure(usually an array), called a parse tree, from the stream of tokens. The parse tree represents the structure of the code.

When an interpreter encounters a line of code, it will parse it to determine what it needs to do. This process involves breaking the line down into smaller pieces and understanding the meaning of each piece.

For example, consider the following line of a C code:

```
printf("Hello, world!");
```
The interpreter will first identify the `printf` keyword and know that this is a keyword that is used to print to the screen. It will then identify the string `"Hello, world!"` and know that this is the message to print to the screen. All this is only possible if the data is correctly parsed to tokens.

Another example would be a language used in data structure that has instructions such as
```
push 1
```
The interpreter should understand that push means adding to the queue or stack from a direction specified earlier and whatever needs to be added is 1. It does so by parsing the line `push 1` into two tokens `push` and `1`.

In this part, write a function to chop up the inputs to individual words(tokens).

## Code generation

The third step is code generation. This process converts the parse tree into executable code. The code can be in the form of machine code or bytecode.

Code generation involves calling the necessary function to perform the actions specified from the parsed data. From our example of

```
printf("Hello, world!");
```
The interpreter will correctly call the function that is involved in printing to the screen and pass to it the argument `Hello, world!`. 

In the second example, the interpreter will call the function involved with "pushing" to the stack or queue and pass the argument `1` to it.

For this step, write a function that will be calling the right function associated with the keywords in the tokens.

## Code execution
The fourth and final step is execution. This process runs the code and produces the desired output. In this stage, the called function from code generation will do its job and the interpreter will return to the caller.
For instance, the `push` will actually push to the stack the number 1.

This is the part where you are supposed to write the functions to handle all the instructions that you expect in your language.

## Conclusion

A language interpreter is a computer program that is able to read and execute code written in a certain programming language. Interpreters are useful for running code without having to compile it first, and can also be used to debug code.

Writing a language interpreter is a complex task, but it can be rewarding. By creating an interpreter, you can not only run code written in your language but also help others to use it and consequently deeply understand the language itself.
