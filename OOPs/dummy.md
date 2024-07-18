### Question related to Abstraction
> How does Java handle multiple inheritance of behavior with interfaces, and what problems does it solve compared to multiple inheritance with classes?
- Answer: Java handles multiple inheritance of behavior using interfaces. A class can implement multiple interfaces, allowing it to inherit behavior from multiple sources without the complexities and ambiguities of multiple class inheritance. This approach avoids issues like the "diamond problem" where a class inherits conflicting behaviors from multiple parent classes.

> What is an interface? How is it different from an abstract class?

- An interface is a reference type in Java that can contain abstract methods, constants, default methods, and static methods. It is different from an abstract class because it cannot have instance variables or constructors, and a class can implement multiple interfaces but can only extend one abstract class.

> When to use abstract classes and abstract methods? <br>
- There are situations in which we will want to define a superclass that declares the structure of a given abstraction without providing a complete implementation of every method. Sometimes we will want to create a superclass that only defines a generalization form that will be shared by all of its subclasses, leaving it to each subclass to fill in the details.



> Creating multiple objects by one type only (A good practice) 

- ANSWER: In real-time, we need different objects of a class in different methods. Creating a number of references for storing them is not a good practice and therefore we declare a static reference variable and use it whenever required. In this case, the wastage of memory is less. The objects that are not referenced anymore will be destroyed by the Garbage Collector of Java. 