# FileIO & Exceptions

## Reading and Writing Files in python

One of the most common tasks that you can do with Python is reading and writing files. Whether it’s writing to a simple text file, reading a complicated server log, or even analyzing raw byte data, all of these situations require reading or writing a file.

### What Is a File?

At its core, a file is a contiguous set of bytes used to store data. This data is organized in a specific format and can be anything as simple as a text file or as complicated as a program executable. In the end, these byte files are then translated into binary 1 and 0 for easier processing by the computer.

Files on most modern file systems are composed of three main parts:

* Header: metadata about the contents of the file (file name, size, type, and so on)
* Data: contents of the file as written by the creator or editor
* End of file (EOF): special character that indicates the end of the file

![file](https://files.realpython.com/media/FileFormat.02335d06829d.png)

### File Paths

When you access a file on an operating system, a file path is required. The file path is a string that represents the location of a file. It’s broken up into three major parts:

1. Folder Path: the file folder location on the file system where subsequent folders are separated by a forward slash / (Unix) or backslash \ (Windows)
2. File Name: the actual name of the file
3. Extension: the end of the file path pre-pended with a period (.) used to indicate the file type

### Line Endings

One problem often encountered when working with file data is the representation of a new line or line ending. The line ending has its roots from back in the Morse Code era, when a specific pro-sign was used to communicate the end of a transmission or the end of a line.

Later, this was standardized for teleprinters by both the International Organization for Standardization (ISO) and the American Standards Association (ASA). ASA standard states that line endings should use the sequence of the Carriage Return (CR or \r) and the Line Feed (LF or \n) characters (CR+LF or \r\n). The ISO standard however allowed for either the CR+LF characters or just the LF character.

## Opening and Closing a File in Python

When you want to work with a file, the first thing to do is to open it. This is done by invoking the open() built-in function. open() has a single required argument that is the path to the file. open() has a single return, the file object:

    file = open('dog_breeds.txt')

When you’re manipulating a file, there are two ways that you can use to ensure that a file is closed properly, even when encountering an error. The first way to close a file is to use the try-finally block:

    reader = open('dog_breeds.txt')

    try:

     # Further file processing goes here

    finally:

      reader.close()

### Text File Types

A text file is the most common file that you’ll encounter. Here are some examples of how these files are opened:

    open('abc.txt')

    open('abc.txt', 'r')

    open('abc.txt', 'w')

![openFile](https://cdn.guru99.com/images/Pythonnew/Python17.5.jpg)

## Python Exceptions: An Introduction

A Python program terminates as soon as it encounters an error. In Python, an error can be a syntax error or an exception. In this article, you will see what an exception is and how it differs from a syntax error. After that, you will learn about raising exceptions and making assertions. Then, you’ll finish with a demonstration of the try and except block.
An introduction to exceptions in Python.

### Exceptions versus Syntax Errors

Syntax errors occur when the parser detects an incorrect statement. Observe the following example:

    >>> print( 0 / 0 ))
    File "<stdin>", line 1
        print( 0 / 0 ))
                    ^
    SyntaxError: invalid syntax

The arrow indicates where the parser ran into the syntax error. In this example, there was one bracket too many. Remove it and run your code again:

    >>> print( 0 / 0)
    Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
    ZeroDivisionError: integer division or modulo by zero

### Raising an Exception

We can use raise to throw an exception if a condition occurs. The statement can be complemented with a custom exception.

![raise](https://files.realpython.com/media/raise.3931e8819e08.png)

### The AssertionError Exception

Instead of waiting for a program to crash midway, you can also start by making an assertion in Python. We assert that a certain condition is met. If this condition turns out to be True, then that is excellent! The program can continue. If the condition turns out to be False, you can have the program throw an AssertionError exception.

![assert](https://files.realpython.com/media/assert.f6d344f0c0b4.png)

### The try and except Block: Handling Exceptions

The try and except block in Python is used to catch and handle exceptions. Python executes code following the try statement as a “normal” part of the program. The code that follows the except statement is the program’s response to any exceptions in the preceding try clause.
Diagram showing try and except statements

![try](https://files.realpython.com/media/try_except.c94eabed2c59.png)

### The else Clause

In Python, using the else statement, you can instruct a program to execute a certain block of code only in the absence of exceptions.

![else](https://files.realpython.com/media/try_except_else.703aaeeb63d3.png)

### Cleaning Up After Using finally

Imagine that you always had to implement some sort of action to clean up after executing your code. Python enables you to do so using the finally clause.

![finally](https://files.realpython.com/media/try_except_else_finally.a7fac6c36c55.png)