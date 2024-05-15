# Unit 1: Advanced Java Language Features

## Lambda expressions and functional interfaces

Certainly! Let's dive into Lambda expressions and functional interfaces in Java.

Lambda Expressions:
Lambda expressions, introduced in Java 8, provide a concise way to represent anonymous functions. They allow you to treat functionality as a method argument or code as data. Lambda expressions are used to implement functional interfaces.

The syntax of a lambda expression is as follows:
(parameters) -> expression
or
(parameters) -> { statements; }

Here's an example of a lambda expression that takes two integer parameters and returns their sum:
(int a, int b) -> a + b

Functional Interfaces:
A functional interface is an interface that contains only one abstract method. They serve as the basis for lambda expressions. Java provides several built-in functional interfaces in the java.util.function package, such as Predicate, Consumer, Function, and Supplier.

Here are a few examples of functional interfaces and their usage with lambda expressions:

1. Predicate<T>:
The Predicate<T> interface represents a predicate (boolean-valued function) of one argument. It has a single method named test that accepts an argument of type T and returns a boolean.

Example:
```java
Predicate<Integer> isEven = (number) -> number % 2 == 0;
System.out.println(isEven.test(4)); // Output: true
System.out.println(isEven.test(7)); // Output: false
```

2. Consumer<T>:
The Consumer<T> interface represents an operation that accepts a single input argument and returns no result. It has a single method named accept that takes an argument of type T.

Example:
```java
Consumer<String> printUpperCase = (str) -> System.out.println(str.toUpperCase());
printUpperCase.accept("hello"); // Output: HELLO
```

3. Function<T, R>:
The Function<T, R> interface represents a function that accepts one argument of type T and produces a result of type R. It has a single method named apply that takes an argument of type T and returns a value of type R.

Example:
```java
Function<Integer, String> intToString = (num) -> String.valueOf(num);
System.out.println(intToString.apply(42)); // Output: "42"
```

4. Supplier<T>:
The Supplier<T> interface represents a supplier of results. It has a single method named get that takes no arguments and returns a value of type T.

Example:
```java
Supplier<Double> randomDouble = () -> Math.random();
System.out.println(randomDouble.get()); // Output: a random double between 0.0 and 1.0
```

You can also create your own functional interfaces. Here's an example:

```java
@FunctionalInterface
interface MyOperation {
    int perform(int a, int b);
}

// Usage
MyOperation addition = (a, b) -> a + b;
MyOperation subtraction = (a, b) -> a - b;

System.out.println(addition.perform(5, 3)); // Output: 8
System.out.println(subtraction.perform(10, 7)); // Output: 3
```

Lambda expressions and functional interfaces provide a way to write more concise and expressive code. They enable functional programming paradigms in Java, allowing you to pass behavior as arguments, create higher-order functions, and simplify code readability.

I hope this explanation with examples helps you understand lambda expressions and functional interfaces better!

- Java Generics and Type Inference
- Java Reflection API and Annotations
- Java Debugging & logging
- Java Unit testing with JUnit

Unit 2: User Interface Development

- Brief intro of UI Development using Applet & AWT
- Java Swing
- JavaFX and FXML
- Scene Builder for visual design
- Event Handling and UI Design Patterns
- Integration with CSS and multimedia

Unit 3: Data Persistence and Access

- JDBC and Connection Pooling
- Object-Relational Mapping (ORM) with Hibernate
- Java Persistence API (JPA)
- Query optimization and performance tuning

Unit 4: Server Side Development

- Java Servlets and Filters
- JavaServer Pages (JSP)
- Integration of Servlets and JSP
- Introduction to RESTful Web Services
- RESTful Web Services with JAX-RS

Unit 5: Modern Java Frameworks & Java for IoT

- Spring Framework (Core, MVC, Security, Data)
  - Model-View-Controller (MVC) pattern
- Dependency Injection and Inversion of Control (IoC)
- Spring Boot for rapid application development
  - Implementing RESTful APIs with Spring Boot
- Java for IoT
  - Interfacing with Arduino and NodeMCU using Java
  - Raspberry Pi programming with Pi4J library
  - Java Framework for IoT (Eclipse IoT, Apache IoTDB)
  - IoT Protocols (MQTT, CoAP) with Java