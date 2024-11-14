# What are Collections? 

Collections are structures similar to arrays, but with the main feature that they are dynamic(their size and capacity can vary over time). In Java, collections are used through the 'collection' interface, which allows the use of a series of common methods such as: add, delete, get size of the collection, etc.

![Main types Of Collections](/Images/Collections/Main%20types%20of%20Collections.png)

# Lists

Lists are groups of elements that are related to each other and have a determinated order. Their size is  dynamic (it can change over time) 

In Java there are different types of lists: 
    - ArrayLists
    - LinkedLists
    - Stack

# ArrayLists

Among the types of lists, one of the most used is the ArrayLists. It has the following characteristics: 
    - ArrayList is a class that is represented as a dynamic array that allows storage elements. 
    - It inherit from the AbstractList class, which implements the list interface. 
    - It allows collections of duplicated elements. 
    - The order of the elements is the same as the order in which they were added.
    - It allows random access (it has indices).
    - Manipulation is slow (it runs through the ArrayList to make a change) 

# LinkedLists

A LinkedList in Java is a data structure that represents a doubly linked list. It is different from an ArrayList because its elements are not stored in contiguous locations in memory.

In an LinkedList, each element, called a 'node', has a value and reference to the next node in the list. The first node is called the 'head', and the last node is called the 'tail'. If a one node does not have a next node, its reference is null, indicating the end of the list.

A Linkedlist provides methods to add, delete and access elements in the list. For example,it is possible to add elements at the first or last position in the list using methods like addFirst() and addLast(). You can also delete elements with methods like removeFirst() and removeLast().It is always possible to access  individual elements using the get() method or iterate through the list using an iterador or a for-each loop.

The main advantage of a LinkedList is that it allows efficient insertions and deletions of elements at any posittion in the list, as it only requires updating the refences of the surrounding nodes. However, accessing elements at a specific position is less efficient than in an array, since a LinkedList must traverse the nodes from the beginning to the desired element. 

# Differences between ArrayList and LinkedList

Arraylist and LinkedList are two implementations of the List interface in Java that are used to store and manage collections of elements. While both serve the same basic function, there are key differences in how they store and access elements, which affects their perfomance in different sutations.

An ArrayList uses an internal array to store the elements of the list in contiguous memory locations. This allows fast access to individual elements using indices, meaning that any element can be accessed directly by its position. However, inserting or deleting elements in middel positions can be costly, as the surrounding elements must be shifted to make space or fill the gap.

In summary, an ArrayList is ideal when fast access to specific elements is required and operations such as insertion and deletion are not frequent or critical for performance.

On the other hand, a LinkedList uses a linked list structure, where each element (node) contains a reference to the next node in the list. Elements are not stored contiguously in memory, which makes direct access to elements through indices less efficient than in an ArrayList. 

However, a LinkedList is efficient for interting and deleting elements at any position, as it only needs to update the reference to the surrounding nodes. 

In other words ,if it is necessary to perfrmo operatiions frequently for inserting or deleting elements at different positions in the list, a LinkedList can be more efficient. 

In conclusion, the choice between ArrayList and LinkedList depends on the operations that will be performed most frequently in your program. If you need fast access to individual elements and insertion and deletion operations are not frequent, an ArrayList is a good option. On the other hand, if insertions and deletion operations are more frequent and direct access to elements is not a priority, a LinkedList may be more efficient. 

![LinkedList vs ArrayList](/Images/Collections/LinkedList%20vs%20ArrayList.png)


# Stack (Pilas)

A stack, is a data structure in which elements are added and removed according to a principle knows as "LIFO" (Last-in, First-Out), meaning that the last element added is the first to be removed. 

Stacks use a series of specific methods to perform certain operations. Among them are: 
    - push: Adds an elements to the top of the stack. 
    - pop: Removes the las element from the stack.
    - isEmpty: Returns true or false depending on wheter the stack is empty or not. 
    - peek: Shows the top element of the stack
    - search: Searches for a specific element in the stack. 

# Introduction to Maps in Java

In Java, a map (or mapping) is an interace that is part of the collections framework (java.util) and represents a collection of key-value pairs, where each key is associated with a unique value. 

The key-value relationship provides an efficient way to access and manage data, as it allows for quick retrieval of a value associated with a key. 

In a map, both keys and values can be of any type of object, and each key must be unique; that is, there cannot be duplicate keys within the same map, althought duplicate values can be associated with different keys. 

The *map* interface in Java has several implementations, each with specific characteristics. Some of the most common implementations are HashMap, TreeMap, LinkedHashMap, Hashtable, and ConcurrentHashMap. Each implementation has its own features, such as search efficiency, sorting capability, and concurrency considerations. 

# Hash Map 

In Java, HashMap is an implementation of the Map interface that uses a hash table data structure to store key-values pairs. 

Among its main features are: 
    - Search Efficiency: The search, insertion, and deletion of elemets in a HashMap are average constant time operations (O(1)), as long as the hash function distributes the keys evenly.
    - No Guarantees on Order: The HashMap implementation does not guarantee the order of the elements. If you need a specific order, you might consider using LinkedHashMap
    - Allows Null Keys and Values: HashMap allows both keys and values to be null. 
    - Iteration through Entries: You can iterate through the entries of the HashMap using an Iterator or a for-each loop. 

