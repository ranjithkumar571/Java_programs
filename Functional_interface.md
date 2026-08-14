# Functional Interface

A functional interface is an interface that contains only one abstract method.It can have any number of default or static methods, but it is restricted to a single abstract behavior. 
This design allows the interface to serve as the target type for lambda expressions and method references.
# Key Rules of Functional Interfaces 
 1. Single Abstract Method: The interface must declare only one abstract method (often called a SAM type).
 2. Optional @FunctionalInterface Annotation: You can use the @FunctionalInterface documentation annotation to prompt the compiler to enforce this rule, throwing an error if a second abstract method is added.
 3. Object Methods Exception: Abstract methods that override public methods from java.lang.Object (like equals() or toString()) do not count toward the single abstract method total.
 4. Default and Static Methods: You can include multiple non-abstract default or static methods without breaking the functional contract.

    Core Built-In Functional Interfaces in Java
  
| Interface | Purpose | Single Method | Example Lambda |
| :--- | :--- | :--- | :--- |
| `Predicate<T>` | Takes one input, returns a boolean | `test(T t)` | `s -> s.isEmpty()` |
| `Function<T, R>` | Takes one input, returns a result | `apply(T t)` | `s -> s.length()` |
| `Consumer<T>` | Takes one input, returns no result | `accept(T t)` | `s -> System.out.println(s)` |
| `Supplier<T>` | Takes no input, provides a result | `get()` | `() -> Math.random()` |





```
@FunctionalInterface
public interface Calculator {
    int calculate(int x, int y);
}

// Usage with a lambda expression
Calculator add = (a, b) -> a + b;
int result = add.calculate(5, 3);
```
