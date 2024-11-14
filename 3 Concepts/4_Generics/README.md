# Generics in Java

Generics in Java are a feature that allows defining classes, interfaces, and methods with parameterized data types. This means that you can write more flexible and reusable code while maintaining type saferty a compile-time. 

Generics were introduced in Java with version 5.0, and their main purpose is to provice a way to handle data of different types without losing type safety or data integrity.

# Basic Syntax

The syntax of generics is base on the use of <T>, where *T* is a type parameter representing a generic data type that can be replaced with any specific type. 

Let's create a *Box* class where we want to store content regardless of its data type: 

```JAVA
    public class Box<T>{
        private T content; 

        public void put(T content){
            this.content = content; 
        }

        public void take(){
            return content; 
        }
    }
```

Then, from the *Main*, let's use this class with differente types of content: 

```JAVA
    Box boxOfString = new Box<>(); 
    boxOfString.put("Hello"); 
    String content = boxOfString.take(); 

    Box boxOfInteger = new Box<>(); 
    boxOfInteger.put(123); 
    Integer number = boxOfInteger.take(); 
```