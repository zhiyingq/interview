# Java 基础 - JVM, JRE, JDK, Stack, Heap, Memory Management
#java
#面试相关

## JVM
JVM (Java Virtual Machine) is an abstract machine. It provides the **runtime environment** in which java byte-code can be executed.

## JRE
JRE (Java Runtime Environment) is the environment within which the java virtual machine runs. JRE contains Java virtual Machine(JVM), class libraries, and other files excluding development tools such as compiler and debugger.

## JDK
JDK is a superset of JRE, it contains everything that JRE has along with development tools such as compiler, debugger etc.

## Java Stack and Heap
https://www.journaldev.com/4098/java-heap-space-vs-stack-memory
1. Java Heap space is used by java runtime to allocate memory to Objects and JRE classes. Whenever we create any object, it’s always **created in the Heap space**.

Garbage Collection runs on the heap memory to free the memory used by objects that doesn’t have any reference. Any object created in the heap space has global access and can be referenced from anywhere of the application.

2. Java Stack memory is used for execution of a thread. They contain method specific values that are short-lived and references to other objects in the heap that are getting referred from the method.

Stack memory is always referenced in LIFO (Last-In-First-Out) order. Whenever a method is invoked, a new block is created in the stack memory for the method to hold **local primitive values and reference to other objects in the method**.

As soon as method ends, the block becomes unused and become available for next method.
Stack memory size is very less compared to Heap memory.

## Difference between Stack and Heap in Java
1. Heap memory is used by all the parts of the application whereas stack memory is used only by one thread of execution.
2. Whenever an object is created, it’s always stored in the Heap space and stack memory contains the reference to it. Stack memory only contains local primitive variables and reference variables to objects in heap space.
3. Objects stored in the heap are globally accessible whereas stack memory can’t be accessed by other threads.
4. **Memory management in stack is done in LIFO manner whereas it’s more complex in Heap memory because it’s used globally**. Heap memory is divided into Young-Generation, Old-Generation etc, more details at Java Garbage Collection.
5. Stack memory is short-lived whereas heap memory lives from the start till the end of application execution.
6. We can use -Xms and -Xmx JVM option to define the startup size and maximum size of heap memory. We can use -Xss to define the stack memory size.
7. When stack memory is full, Java runtime throws java.lang.StackOverFlowError whereas if heap memory is full, it throws java.lang.OutOfMemoryError: Java Heap Space error.
8. Stack memory size is very less when compared to Heap memory. Because of simplicity in memory allocation (LIFO), stack memory is very fast when compared to heap memory.




























