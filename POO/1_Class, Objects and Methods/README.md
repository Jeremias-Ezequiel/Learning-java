## What are classes? How to create one?

The classes are templates that allow us to create objects. It is one of the main ways to abstract real-life objects to use them in the logical world in the Java applications that we develop.

For example: If we had the class called *Car*, it would contain the main parts or elements that a car has in order to build it or represent it at a logical level.

All classes have the following characteristics or particularities: 

    - They represent real world entities. 
    - They have attributes and methods. 
    - To use them, we must create instances or objects. 

# Attributes of a class

Attributes are characteristics that a class possesses. They are varibles contained and established by objects and normally have an associated data type. 

# Tips to keep in mind about classes 

The following conventions are interntionally accepter standarts: 
    
    - All classes should begin with a capital letter in each of their words.
    - All attributes should start with a lowercase letter,and if they have more than one word they must start with an uppercase letter. There sould be no spaces between words. 

## What are methods? How to create one? 

Operations or methods are actions contained in a class and help define the behavior of the class, saying what actions it can do. 

Within a system, methods are usually represented as infinitive verbs and may optionally have input values (Parameters) and output values (Return).

There are methods that can be *procedures* (they do not return a value) or Functions (they return a value of a specific data type).

# Input values or Parameters

Parameters are values that can be sent to a method. Methods take parameters as input values and can be perform necessary actions based on them. 

All parameters should have a associety data type (they can also be empty or optional).

# Output values or Returns

The output of a method is a special value that it return after performing a series of actions or proccesses. Input values are data, and outputa values are generally considered information. 

All input values should have an associated data type. In methos, it is possible to return a single output value, and this actions is performed using the reserverd word *return*. 

## Constructor methods and Objects

In Java, objects are instances of classes, and they are created using a method called a *constructor*. An object in programming is generally a logical representation of a real-life entity. It has a state and also has behavior. 

A constructor is a special method that is called automatically when an object of a class is created. 

Constructors are used to initialize the attributes of an object when it is created. Each class can have one or more constructors, and each constructor has the same name as the class.

## Getters and Setters 

In Java, getters and setters are methods used to access and modify values in the attributes in a controlled and safe way. 

In simple terms, getters and setters allow the attributes of a class to remain private, preventing direct access from outside the class. 

