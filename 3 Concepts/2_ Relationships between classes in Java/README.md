# Relationship between classes in Java 

In Java, relationships between classes are established using object-oriented programming concepts such as inheritance, composition, and association. 

These relationships allow the creation of connections and dependencies between different classes to model the structure and behavior of a system. 

We've already seen how inheritance works; now let's explore one-to-one (1:1), one-to-many(1:n), and many-to-many (n:n) relationships between classes.

# One-to-One Relationship

This type of relationships is established by creating an object as an attribute or instance variable within a class. In thi type of relationship, each object of the first calss has a unique and exclusive reference to an object of the second class, and viceversa. For example: 

![1:1 Relationship](/Images/Relationships%20between%20classes/Relation11.png)

# One-to-Many Relationship

In object-oriented programming (OOP), a one-to-many relationship implies that an object of one class is related to multiple objects of another class. 

In this type of relationship, an object from the first class can have multiple references to object from the second class, but each object from the second class is associated with only one object from the first. This is generally achieved using Colletions such as *List*, *ArrayList*, *LikedList*, *HashSet*, etc. 

For example, if we wanted to relate the *Purchase* class with the *Item* class, where each purchase can have multiple items, we would do it as follows: 

![One-to-Many relationship](/Images/Relationships%20between%20classes/One-To-Many.png)

# Many-to-Many relationship

A many-to-many relationship in Java with OOP means that multiple objects of one class can be related to multiple objects of another class, and vice versa. 

This it typically achieved using Collections on both sides of the relationship, meaning in both classes that need to be related. Remember that many-to-many relationships are essentially two one-to-many relationships set up in opposite directions.

Furthermore, since many-to-many relationships are often mapped on databases, there are cases where a middle class can be created to add extra information to the relationships between both classes. However, when using ORMs (like JPA + Hibernate), the need to create an intermediate class in usually unnecessary because the ORM automatically handles this.

For example, suppose we have a class *Student* with a many-to-many relationshi to a class *Course*, where many students can be enrolled in many courses, and many courses can have many students: 

![Many-to-Many 1](/Images/Relationships%20between%20classes/Many-to-many%201.png)
![Many-to-Many 2](/Images/Relationships%20between%20classes/Many-to-many%202.png)