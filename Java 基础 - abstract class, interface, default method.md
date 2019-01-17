# Java 基础 - abstract class, interface, default method
#java
#面试相关

### Abstract Class
An abstract class is a class which **cannot be instantiated**. An abstract class is used by creating an inheriting subclass that can be instantiated. An abstract class does a few things for the inheriting subclass:

1. Define methods which can be used by the inheriting subclass.
2. Define abstract methods which the inheriting subclass must implement.
3. Provide a common interface which allows the subclass to be interchanged with all other subclasses.

```java
abstract public class AbstractClass {
    abstract public void abstractMethod();
    public void implementedMethod() { System.out.print("implementedMethod()"); } 
    final public void finalMethod() { System.out.print("finalMethod()"); }
}
```

Features:
1. At least one of the methods is marked as abstract.
2. The class is marked as abstract

### Difference between Abstract class and Interface 

1. Type of methods: 
Interface can have only abstract methods. Abstract class can have abstract and non-abstract methods. From Java 8, it can have default and static methods also.

2. Final Variables: 
Variables declared in a Java interface are by default final. An abstract class may contain non-final variables.

3. Type of variables
Abstract class can have final, non-final, static and non-static variables. Interface has only static and final variables

4. Implementation
Abstract class can provide the implementation of interface. Interface can’t provide the implementation of abstract class. A Java interface can be implemented using keyword “implements” and abstract class can be extended using keyword “extends”.

5. Multiple implementation
An interface can extend another Java interface only, an abstract class can extend another Java class and implement multiple Java interfaces.

6. Accessibility of Data Members
Members of a Java interface are public by default. A Java abstract class can have class members like private, protected, etc.

### Default method in interface
Before Java 8, interfaces could have only abstract methods. The implementation of these methods has to be provided in a separate class. So, if a new method is to be added in an interface, then its implementation code has to be provided in the class implementing the same interface. To overcome this issue, Java 8 has introduced the concept of default methods which allow the interfaces to have methods with implementation without affecting the classes that implement the interface.



















