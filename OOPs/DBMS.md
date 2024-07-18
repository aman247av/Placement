# Abstraction
Abstraction is the process in which we only show essential details/functionality to the user. The non-essential implementation details are not displayed to the user.

- In Java, abstraction is achieved by interfaces and abstract classes

## Abstract Classes
An abstract class cannot be instantiated directly. It serves as a blueprint for other classes.

- It can have abstract methods (methods without a body) and concrete methods (methods with a body)

```
abstract class Animal {
    abstract void makeSound();
    void breathe() {
        System.out.println("Breathing...");
    }
}
```
> When to use abstract classes and abstract methods? <br>
There are situations in which we will want to define a superclass that declares the structure of a given abstraction without providing a complete implementation of every method. Sometimes we will want to create a superclass that only defines a generalization form that will be shared by all of its subclasses, leaving it to each subclass to fill in the details.

```
abstract class Shape { 

	String color; 
	abstract double area(); 
	public abstract String toString(); 

	public Shape(String color) { 
		System.out.println("Shape constructor called"); 
		this.color = color; 
	} 

	public String getColor() {
        return color;
    } 
} 

class Circle extends Shape { 
	double radius; 

	public Circle(String color, double radius) { 
        super(color); 
		System.out.println("Circle constructor called"); 
		this.radius = radius; 
	} 

	@Override
    double area() { 
		return Math.PI * Math.pow(radius, 2); 
	} 

	@Override
    public String toString() { 
		return "Circle color" + super.getColor() + "area" + area(); 
	} 
} 

public class Test { 
	public static void main(String[] args) { 
		Shape s1 = new Circle("Red", 2.2); 
		System.out.println(s1.toString()); 
	} 
}

```

### Benefits of Abstraction
- Simplification - reduces complexity by hiding unnecessary details
- Security - By exposing only necessary details, abstraction can enhance security by preventing access to implementation details.
- Code Reusability

## Interface:
An interface is a completely abstract type that can only contain abstract methods (prior to Java 8) and constants.

- Cannot have constructors.

### Difference b/t Abstract Class and Interface:
- Abstract Class: A class can inherit from only one abstract class (single inheritance). Can extend other classes and implement multiple interfaces.
- Interface: A class can implement multiple interfaces (multiple inheritance of type).
An interface can extend multiple other interfaces.

```
interface Animal {
    void eat();
}

interface Pet {
    void play();
}

```
    class Dog implements Animal, Pet {
        String name;

        Dog(String name) {
            this.name = name;
        }

        @Override
        public void eat() {
            System.out.println(name + " is eating.");
        }

        @Override
        public void play() {
            System.out.println(name + " is playing.");
        }
    }

    public class Main {
        public static void main(String[] args) {
            Dog myDog = new Dog("Buddy");
            
            // Using methods from Animal interface
            myDog.eat();
            
            // Using methods from Pet interface
            myDog.play();
        }
    }

>Default methods enable interfaces to have behavior while maintaining backward compatibility.

#### 1. What is an interface? How is it different from an abstract class?

An interface is a reference type in Java that can contain abstract methods, constants, default methods, and static methods. It is different from an abstract class because it cannot have instance variables or constructors, and a class can implement multiple interfaces but can only extend one abstract class.
