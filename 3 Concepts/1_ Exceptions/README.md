# Exceptions in Java

In Java, an exception is an unusual event or condition that occurs during the executions of a program and disrupts the normal flow of execution. Exceptions are used to handle and signal errors and exceptional situtations. 

Many things can cause exceptions, including: 
    - Hardware errors 
    - Impossible mathematical operations (dividing by zero) 
    - Program errors (array overflow error) 
    - Opening a non-existent file 
    - Among others..

# Types of Exceptions 
There are two distinct types: 
    - Built-in Java exceptions 
    - Custom exceptions 

# Buil-in Java Exceptions 
Among Java's built-in exceptions, we have the following: 

![Exceptions in Java](/Images/Exceptions/Exceptions.png)

Each can be used in different situations, for example, *FileNotFoundException* when a file is not found, or *ArrayIndexOutOfBoundsException* when trying to access a positions outside of an array. 

# Custom Exceptions 
To create custom exceptions, the following blocks must be considered: 
    - *try*: Bloc where the exception may occur
    - *catch*: Like the 'else' of the try (it executes when an exceptions is thrown in the try block) 
    - *finally*: Block of code that always executes (refardless of whether there were errors or not)
    - *throw*: Used to throw any exception
    - *throws*: Declared which exceptions a method may throw

