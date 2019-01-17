# Java 基础 static, final
#面试相关
#java

## static
1. Static methods cannot be overridden!
Static methods cannot be overridden because method overriding only occurs in the context of dynamic (i.e. runtime) lookup of methods. Static methods (by their name) are **looked up statically** (i.e. at compile-time).

2. Static variable’s value can be changed
3. Static class can only be declared inside a class (as a nested class)

## final
The final keyword in java is used to restrict the user, it can be used in many context, such as variable, method and class.

A final variable that have no value is called blank final variable or uninitialized final variable. It can be initialized in the constructor **only**. The blank final variable can be static also which will be initialized in the static block only.

### Java final method
If you make any method as final, you cannot override it.
### Java final class
If you make any class as final, you cannot extend it.
