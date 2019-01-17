# Java 基础 - overloading, overriding, signature
#java
#面试相关

## Overloading
Overloading allows different methods to have same name, but different signatures where signature can differ by **number of input parameters or type of input parameters or both**. Overloading is related to compile time (or static) polymorphism.

## Difference with overriding
Overloading is about same function have different signatures. Overriding is about same function, same signature but different classes connected through inheritance.

## Signature
In Java, a method signature is part of the method declaration. It's the **combination of the method name and the parameter list**. （the method's name and the parameter types).
1 - same name with different number of parameters
2 - same name with different type of parameters
3 - same name with different type and number of parameters
4 - same name with different order (regarding to type) of parameters

The reason for the emphasis on just the method name and parameter list is because of overloading. It's the ability to write methods that have the same name but accept different parameters. The Java compiler is able to discern the difference between the methods through their method signatures.



















