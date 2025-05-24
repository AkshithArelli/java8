# java8

A **functional interface** in Java is an interface that contains exactly one abstract method (unimplemented method). Functional interfaces are used primarily as the basis for lambda expressions and method references, which were introduced in Java 8 to support functional programming.

### Key Points:
- **Exactly One Abstract Method:** A functional interface can only have one abstract method. However, it can have multiple default or static methods.
- **@FunctionalInterface Annotation:** You can annotate an interface with `@FunctionalInterface` to indicate that it is intended to be a functional interface. This is optional but helps the compiler catch errors if the interface does not meet the requirements.
- **Usage:** Commonly used as the target for lambda expressions and method references.

### Example

```java
@FunctionalInterface
public interface MyFunctionalInterface {
    void m1(); // Only one abstract method

    // Default methods are allowed
    default void m2() { System.out.println("Default method"); }

    // Static methods are allowed
    static void m3() { System.out.println("Static method"); }
}
```

### Why Functional Interfaces?
Functional interfaces enable you to write concise code using lambda expressions:
```java
MyFunctionalInterface func = () -> System.out.println("Hello from m1!");
func.m1(); // Outputs: Hello from m1!
```

### Common Examples in Java
- `Runnable` (single `run()` method)
- `Callable` (single `call()` method)
- `Comparator` (single `compare()` method)
- Java 8 interfaces in `java.util.function` package like `Predicate<T>`, `Function<T, R>`, `Supplier<T>`, etc.

**In summary:**  
A functional interface in Java is an interface with a single abstract method, used as the foundation for lambda expressions and functional programming features.

```java
//traditional way
public class Main implements Calculator{

    @Override
    public void switchOn() {
        System.out.println("Turned On");
    }

    public static void main(String args[]) {
        Main obj = new Main();
        obj.switchOn();
    }
}

//using lambda expression
public class Main{
    public static void main(String[] args) {
        Calculator cal = () -> System.out.println("Turned On");
        cal.switchOn();
    }
}

interface Calculator {
    void switchOn();
}
```








Java 8 features

Differences between Java 8 Map() Vs flatMap() :

map() | flatMap() | 
--- | --- |  
It processes stream of values. | It processes stream of stream of values. 
It does only mapping. | It performs mapping as well as flattening.
It’s mapper function produces single value for each input value. | It’s mapper function produces multiple values for each input value. 
It is a One-To-One mapping. | It is a One-To-Many mapping. 
Data Transformation : From Stream<T> to Stream<R> | Data Transformation : From Stream<Stream<T> to Stream<R> 
Use this method when the mapper function is producing a single value for each input value. | Use this method when the mapper function is producing multiple values for each input value. 

