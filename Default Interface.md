# Default interface
In Java, default methods are methods inside an interface that include a body (an implementation), introduced in Java 8 using the default keyword. They allow developers to add 
new functionality to existing interfaces without breaking backward compatibility or forcing implementing classes to rewrite their code.

```interface Vehicle {
    // Abstract method (must be implemented)
    void startEngine();

    // Default method (optional to override)
    default void honk() {
        System.out.println("Beep! Beep!");
    }
}

class Car implements Vehicle {
    @Override
    public void startEngine() {
        System.out.println("Car engine started.");
    }
    // honk() is inherited automatically!
}```
