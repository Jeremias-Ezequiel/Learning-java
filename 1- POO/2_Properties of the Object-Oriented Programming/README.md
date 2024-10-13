## The propierties of Object-Oriented Programming (OOP) 

In Java, object-oriented programming is based on four fundamental concepts: 
    - Abstraction 
    - Inheritance 
    - Polymorphism
    - Encapsulation

# Abstraction 

Abstraction in OOP is the process of identifying and dividing the essential characteristics of a real-life object to represent them in an abstract or logical form within a program. In Java, this it archieved by creating classes and defining their atributes and methods. 

# Inheritance 

In OOP, inheritance is a key conecept that allows a class to inherit attributes and methods from another class. 

Inheritance allows us to reuse classes. Generally, when using inheritance, a new class is created that inherits or extends the methods and attributed of another class. This class if generally referred to as a *subclass* or child class and can have attributes or methods that do not exist in the original class. On the other land, the original class is called the *superclass*, or sometimes the parent class.

Just like genetic inheritance in real life, where children inherit characteristics and behavios from their parents, programming inheritance follows the same concept. 

# Poymorphism

Polymorphism in Java refers to the ability of an object to take many forms. In simple terms, it means that an object can be treated as if it were of several types. 

In Java, this is possible through inheritance and method overriding. Let's suppose we have a class called Animal and chil classes called Dog and Cat. Since both are Animal, they can inherit from the Animal class. 

Polymorphism allows seeing a dog or a cat as a generic animal. For example, if you have a method that takes a parameter of type Animal, you can send an object of type Dog or Cat. This is possible because they are subtypes of Animal.

# Encapsulation

Encapsulation in Java is a feature that allows us to hide the internal details of a class and provides controlled access to its attributes and methods using reserverd words called 'access modifiers'. 

# Access Modifiers in Java

In Java, there are four access modifiers that control the visibility and accessibility of classes, attributes, methods and constructors
    
    1. Public: is the most open and commonly used access modifier. Members (attributes, methods, constructors) declared as public are accessible from other classes and packages. They can be used by anu object that has access to the class. 
    
    2. Protected: Members declared as protected are accessible only within the same class, in subclasses (child classes), and within the same package.

    3. Private: It is the most resctrictive access modifier. Members declared as private are accessible only within the same class. They cannot be accessed from other class. 

    4. Default: If no access modifiers is specified, it is considered the default access. Member with default classes are accesible only within the same package. They cannot be accessed from classes in different packages.
    
## Abstract Classes 

An abstract class in Java is a class that cannot be instantiated directly; object cannot be created from this class. It is used as a base class or templates for other related classes.

The main feature of an abstract class is that is can have abstract methods. An abstract method is considered abstract when it is declared but does not have an implementation; it does not contain any code between its braces. In an asbtract method, only the function name and the parameters it accepts are declared, finishing the line with a ';'.

When a class declares only abstract methods, we must mark it as abstract using the keyword 'abstract'. An abstract class can have abstract methods or concrete methods, but it is obligatory to use at least one abstract method.

Classes that inherit from an asbtract class, called subclasses or child classes, must provide an implementation for all inherited abstract methods. This means thath they must implement the abstract methods defined in the abstract class. 

An abstract class is used as a general abstraction from which more specified classes are derived. It provides a common structure and defines abstract methods thaht must be implement in subclasses. This promotes code reuse and the creation of a hierachy of classes. 

## Interface 


Interfaces in Java are a collection of abstract methods and attributes that can be unique constants. Esseantially, we can think of an interface as a cgroup of behaviors and methods that a class can implement.

An interface only declares the function names and parameters that it accepts. Classes that implement an interface are responsible for providing the implementation of all methods declared in it.

In summary, we can say that an interface: 
    - Is a collection of abstract methods with constants properties (attributes) 
    - Only allows the extraction or implementation of other interfaces
    - Specifies what should be done (methods) bue does not show the implementation (can only have abstratac methods)
    - Can only have methods with public access(they cannot be protected or private) 
    - Can only contain 'variables' that are public, static and final
    - The word 'abstract' in the method definition is not obligatory. 
    - Generally, interfaces indice what an object can be.

