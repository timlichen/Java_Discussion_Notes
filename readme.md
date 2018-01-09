# Day 1

Java is an statically typed, OOP lanauge that is compiled and then interpreted. Java was designed with the mentality of being able to "Write Once, Run Anywhere". This is possible through the implementation of JVM's for specific OS's. OSX, Linux, Windows. However, since the code for the VM/OS differs for each host additional testing is needed for each target system, slogan is more like, "Write Once, Debug Everywhere".

Life Cycle of a Java Program - All java programs follow this life cycle.

### Java Life Cycle:

The code is written, it's then compiled, once it's compiled and all dependencies are imported, the resulting bytecode is then run through the interpreter in the Java Virtual Machine which is hosted on an operating system.

* ```java```  - interpreter
* ```javac``` - compiler
* ```jar``` - archiver
* ```jvm``` - java virtual machine

**What is static?** -  A method that can be run without out an object. Ask yourslf does the purpose of the method require and object to make sense, e.g. convert mpgToKpg vs. defineTheMileage of a car.

**What is void?** - Specifying the return type, void means don't return anything.

**What is the main entry point for a java program?** - Public Static void main(String[] arg) is the method called when a Java application beings, not every java class needs to have it, but when you test and run your java program you will need to create this method inorder for you to actually "run" the program.
HelloWorld.java & HelloWorldTest.java

Make note of the difference between Class data types and primitive non-class data types.

Reading the Java Docs
How to use import and for loops.

# Day 2

### Object Oriented Programming with Java

**Stack 2 Algorithms**:
Warmup - insert at given index and value insert value, remove at index

Binary Search - given a sorted array search for a value

**What is an object?**
Consider real world objects ... 
What possible attributes can this object have?
What possible behavior can this object perform?

Software objects are conceptually similar to real world objects; they consist of a state and related behavior. An object uses fields to store its state and its methods as the primary mechanism for object-object communication. 

Circle Diagram - inner circle fields, outer circle segments methods

**What are some advantages of bundling Java code into objects:**

**Modularity** - source code objects can be written and maintained independently. Once created, an object can be easily passed around inside of the system.

**Information hiding** - Methods provide a layer of protection from fields that hold information, thus protecting and hiding from the outside world (i.e. other code).

**Code re-use** - You can use other people's objects and they can use yours.

**Plugability and debugging ease** - if an object starts to break your code,you can remove it and plug in another object. Similar to mechanical objects, if a bolt breaks you can replace the bolt rather than the entire machine.

**Understanding Member Variables (fields, methods, nested classes)**
Fields are attributes
Methods define behavior of the object.
    
Nested classes are classes written within another class. Non static nested classes are called inner classes
    
For right now, just know that this is possible so when you come across a situtaion where logically grouping classes so that are only used in one place you'll know it possible. You cannot write classes sibling to each other in one file.

**Understanding Constructors** 

Constructors are special methods that are run when an object is instantiated. Constructor declarations look like method declarations—except that they must have the same name of the class and have no return type

```Java

    class Hamburger{
        public Hamburger(int _patties, String[] _toppings){
            patties = _patties;
            toppings = _toppings
        }
    }
```

**Understanding Method Overloading and Signatures** -  Two of the components of a method declaration comprise the method signature—the method's name and the parameter types. See the example in the course platform.

**Encapsulation** - wrapping data in a class that is relevant to that class.

**Inheritance** - How classes acquire the methods and fields of another class. Java is designed to not include multiple inheritance, class C cannot inherit from class B and A, it can only have one "superclass". Every object unless specified will implicitly inherit from the Object class. When you inherit, you bring in the fields and methods of the parent class. Java prevents name collisions and problem that arise from conflicting fields and method by only allowing single inheritance.

A -> B -> C - C will have all the fields/methods included in A and B

B -> C <- A, C cannot directly inherit from B and A.

# DAY 3 

### Interfaces, Polymorphism & Abstraction

**Polymorphism** - Subclasses of a class can define their own unique behaviors and yet share some of the same functionality of the parent class. An instance of a class or object can behave or function as if it were a different class or type of object, but have it’s own specific attributes and methods. Along with overloading methods, another form of polymorphism is overriding methods. https://docs.oracle.com/javase/tutorial/java/IandI/polymorphism.html

**Abstraction** - The process of hiding the implementation details and showing only the functionality. Java provides Abstract classes and Interfaces as an implementation of Abstraction. When should you use an interface and when should you use an abstract? An interface should be used when you want to provide classes with specific methods to implement, classes can implement multiple interfaces but they don’t have to share a similar class hierarchy. An abstract class provides a base providing a model from which a subclass should follow. It will be the one and only superclass, but can provide a base that allows for abstract methods to be implemented in various ways while providing some methods predefined in the abstract class.

**Interfaces** are pretty important in the world of Java and they go pretty deep, we won't need to know everything an interface can do but there are a few core principlies and design patterns you should know.  Interfaces act as a contract between two classes, each class that interfaces with the interface should be able to write their code without any knowledge of how the other group's code is written.

Consider this, Noelle is working on a software project, she want to let me help out, but while I work on something she wants to work on other parts of her project. She writes and interface that defines the method signature and tell me that my Java class has to use this interface. She doesn't really care how I write my code, but it's gotta work and it's got to fit the standards of her software.

Interfaces are also a way to gain some of the advantages of multiple inheritence of Classes in Java without some of the concerns that come with direct multiple inheritence since interfaces cannot be instantiated. Class can implement more than once interface. The way they avoid the disadvantages of multiple inheritence is by making interfaces have no state and no implementation i.e. they cannot be instantiated.

https://docs.oracle.com/javase/tutorial/java/IandI/createinterface.html

**Abstract Class** - They can contain state such as member variables and methods that do not have to be implemented by subclasses. Also, subclasses do not have to implement abstract methods of the parent class.

https://docs.oracle.com/javase/tutorial/java/IandI/abstract.html 

#### Consider using abstract classes if any of these statements apply to your situation:
 You want to share code among several closely related classes.
* You expect that classes that extend your abstract class have many common methods or fields, or require access modifiers other than public (such as protected and private).
* You want to declare non-static or non-final fields. This enables you to define methods that can access and modify the state of the object to which they belong.
#### Consider using interfaces if any of these statements apply to your situation:
* You expect that unrelated classes would implement your interface. For example, the interfaces Comparable and Cloneable are implemented by many unrelated classes.
* You want to specify the behavior of a particular data type, but not concerned about who implements its behavior.
* You want to take advantage of multiple inheritance of type.

**POJO & Java Beans** - Normal objects instantiated from a class.
* Member variables must be private, but accessible using get and set
* Must have a zero argument constructor
* Must implement the serializable interface

    