# Front Matter

**Title Page**
Advanced Java Programming

**Copyright Page**
© 2024 by Milav Dabgar
All rights reserved. No part of this publication may be reproduced, distributed, or transmitted in any form or by any means, including photocopying, recording, or other electronic or mechanical methods, without the prior written permission of the publisher, except in the case of brief quotations embodied in critical reviews and certain other noncommercial uses permitted by copyright law.

**Dedication**
[Optional: A short dedication to someone or something]

**Table of Contents**
[Automatically generated]

# Preface

Java is one of the most widely used programming languages in the world, with applications ranging from desktop software and mobile applications to enterprise systems and scientific computing. As the language and its ecosystem continue to evolve, developers need to stay up-to-date with the latest features, tools, and best practices to build robust, scalable, and efficient applications.

This book, "Advanced Java Programming," is designed to take your Java programming skills to the next level. It covers a wide range of advanced topics, including lambda expressions, generics, reflection, annotations, user interface development, data persistence, server-side programming, and modern Java frameworks.

The book is divided into five units, each covering a specific area of advanced Java programming. Unit 1 delves into advanced language features such as lambda expressions, generics, reflection, annotations, and parallel processing using the Streams API. Unit 2 focuses on user interface development, covering Swing, JavaFX, and various UI design patterns.

Unit 3 explores data persistence and access techniques, including JDBC, Hibernate, and the Java Persistence API (JPA). You'll learn about database design, object-relational mapping (ORM), query optimization, and performance tuning.

Unit 4 covers server-side development with servlets, filters, JavaServer Pages (JSP), and RESTful web services. You'll learn how to build dynamic web applications, handle form submissions, manage sessions, and design and implement RESTful APIs.

Finally, Unit 5 introduces you to modern Java frameworks like Spring (Core, MVC, Security, and Data) and Spring Boot for rapid application development. Additionally, you'll explore Java's role in the Internet of Things (IoT) domain, including interfacing with Arduino and Raspberry Pi, as well as IoT protocols like MQTT and CoAP.

Throughout the book, you'll find numerous code examples, practical exercises, and real-world scenarios to reinforce your understanding of the concepts. Whether you're a seasoned Java developer looking to expand your knowledge or a beginner seeking to master advanced Java topics, this book will provide you with the skills and insights needed to become a proficient Java programmer.

So, let's embark on this journey together and unlock the full potential of Java programming!

Milav Dabgar
Nnovember 16, 2024

# Unit 1: Advanced Java Language Features

Java has continuously evolved over the years, introducing new language features and enhancements to improve developer productivity and code quality. This unit explores some of the advanced features of the Java language, focusing on lambda expressions, generics, reflection, annotations, and parallel processing with the Streams API.

**Lambda Expressions and Functional Interfaces**

Lambda expressions, introduced in Java 8, provide a concise and expressive way to represent anonymous functions. They enable functional programming constructs in Java and promote a more declarative style of programming. In this chapter, you'll learn about the syntax and usage of lambda expressions, as well as functional interfaces, which are essential for working with lambda expressions. You'll also explore method references and their applications, which can further simplify your code.

**Java Generics and Type Inference**

Generics are a powerful feature in Java that allow you to write reusable and type-safe code. By using generics, you can create classes, interfaces, and methods that work with different types while providing compile-time type safety and eliminating the need for explicit type casting. This chapter covers the fundamentals of generics, including bounded type parameters, wildcards, and generic methods. You'll also learn about type inference and the diamond operator, which can help make your code more concise and readable.

**Java Reflection API and Annotations**

The Java Reflection API provides a way to inspect and manipulate classes, interfaces, fields, methods, and constructors at runtime. This powerful feature enables dynamic program behavior and is widely used in frameworks, tools, and libraries. In this chapter, you'll explore the Reflection API's capabilities and use cases, as well as its potential drawbacks and performance implications.

Annotations, introduced in Java 5, provide a way to associate metadata with code elements such as classes, methods, and fields. This metadata can be used by tools, frameworks, and libraries to modify the behavior of your code at runtime. You'll learn about built-in and custom annotations, as well as runtime annotation processing and its applications.

**Streams API and Parallel Processing**

The Streams API, introduced in Java 8, offers a functional-style approach to processing data streams. It provides a rich set of operations that can be chained together to perform complex data transformations and computations. This chapter covers the fundamentals of the Streams API, including intermediate and terminal operations, as well as parallel processing techniques for improved performance on modern multi-core systems.

**Java Debugging, Logging, and Testing**

Effective debugging, logging, and testing are crucial aspects of software development. In this chapter, you'll explore various debugging techniques and tools available in Java, as well as popular logging frameworks like Log4j and SLF4J. Additionally, you'll be introduced to unit testing with JUnit and the principles of test-driven development (TDD), which can help you write more robust and maintainable code.

By mastering the advanced language features covered in this unit, you'll be equipped with powerful tools and techniques to write more expressive, efficient, and maintainable Java code. These features will lay the foundation for the rest of the book, enabling you to tackle more complex topics and build robust applications.

## Lambda expressions and functional interfaces

Lambda expressions are anonymous functions that can be treated as values and passed around. They provide a concise way to represent a method's behavior or logic using an expression. Lambda expressions were introduced in Java 8 as a part of the Java Programming Language.

### Introduction to Lambda Expressions

A lambda expression is represented using the following syntax:

```java
(parameter list) -> { lambda body }
```

Here's a simple example of a lambda expression:

```java
Runnable runnable = () -> System.out.println("Hello, Lambda!");
```

In this example, `() -> System.out.println("Hello, Lambda!")` is a lambda expression that represents the behavior of the `run()` method in the `Runnable` interface. We can assign this lambda expression to a variable of type `Runnable` or pass it directly as an argument to a method that expects a `Runnable` instance.

Lambda expressions can have parameters, just like regular methods. Here's an example that takes two integers and returns their sum:

```java
BiFunction<Integer, Integer, Integer> adder = (a, b) -> a + b;
int sum = adder.apply(3, 4); // sum = 7
```

In this case, `(a, b) -> a + b` is a lambda expression that takes two `Integer` parameters `a` and `b`, and returns their sum. It is assigned to a variable `adder` of type `BiFunction<Integer, Integer, Integer>`.

Lambda expressions can also have a more complex body with multiple statements:

```java
Consumer<String> printWithPrefix = str -> {
    String prefix = "Value: ";
    System.out.println(prefix + str);
};
printWithPrefix.accept("Hello"); // Output: Value: Hello
```

Here, the lambda expression `str -> { String prefix = "Value: "; System.out.println(prefix + str); }` has a code block as its body, which defines a local variable `prefix` and uses it to print the string with a prefix.

### Functional Interfaces and Their Usage

Lambda expressions are primarily used in conjunction with functional interfaces. A functional interface is an interface that has a single abstract method. Some examples of functional interfaces in Java are `Runnable`, `Comparator`, `Callable`, and `ActionListener`.

Here's an example of using a lambda expression with the `Runnable` functional interface:

```java
Thread thread = new Thread(() -> System.out.println("Hello from a thread!"));
thread.start();
```

In this code, the lambda expression `() -> System.out.println("Hello from a thread!")` is passed as an argument to the `Thread` constructor, which expects a `Runnable` instance.

Lambda expressions can also be used with custom functional interfaces. Here's an example of a custom functional interface `Operation` and its usage with a lambda expression:

```java
@FunctionalInterface
interface Operation {
    int apply(int a, int b);
}

public class LambdaExample {
    public static void main(String[] args) {
        Operation addition = (a, b) -> a + b;
        Operation multiplication = (a, b) -> a * b;

        int result1 = performOperation(5, 3, addition);
        int result2 = performOperation(5, 3, multiplication);

        System.out.println("Result 1: " + result1); // Output: Result 1: 8
        System.out.println("Result 2: " + result2); // Output: Result 2: 15
    }

    private static int performOperation(int a, int b, Operation op) {
        return op.apply(a, b);
    }
}
```

In this example, we define a custom functional interface `Operation` with a single abstract method `apply(int a, int b)`. We then create two lambda expressions `(a, b) -> a + b` and `(a, b) -> a * b`, which implement the `Operation` interface. These lambda expressions are passed as arguments to the `performOperation` method, which invokes the `apply` method of the `Operation` instance with the provided arguments.

### Method References and Their Applications

Method references provide a shorthand notation for lambda expressions that invoke a specific method. They can make your code more concise and readable when working with existing methods.

There are four types of method references:

1. Static method reference: `ClassName::staticMethodName`
2. Instance method reference on a particular object: `objectInstance::instanceMethodName`
3. Instance method reference on an arbitrary object of a particular type: `ClassName::instanceMethodName`
4. Constructor reference: `ClassName::new`

Here's an example that demonstrates the usage of each type of method reference:

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class MethodReferences {
    public static void main(String[] args) {
        // Static method reference
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
        numbers.forEach(System.out::println); // Calls System.out.println() for each number

        // Instance method reference on a particular object
        String str = "Hello";
        int length = computeLength(str, String::length); // Calls str.length()

        // Instance method reference on an arbitrary object of a particular type
        List<String> strings = Arrays.asList("apple", "banana", "cherry");
        List<Integer> lengths = strings.stream()
                                       .map(String::length) // Calls str.length() for each string
                                       .collect(Collectors.toList());

        // Constructor reference
        List<Thread> threads = strings.stream()
                                      .map(str -> new Thread(str::toUpperCase)) // Calls new Thread(() -> str.toUpperCase())
                                      .collect(Collectors.toList());
    }

    private static int computeLength(String str, Function<String, Integer> lengthFunc) {
        return lengthFunc.apply(str);
    }
}
```

In this example:

- We use a static method reference `System.out::println` to print each number in the list.
- We use an instance method reference on a particular object `String::length` to compute the length of a string.
- We use an instance method reference on an arbitrary object of a particular type `String::length` to compute the lengths of strings in a list.
- We use a constructor reference `str::toUpperCase` to create a new `Thread` instance with a lambda expression that converts a string to uppercase.

Method references can make your code more concise and readable when working with existing methods, especially when combined with lambda expressions and functional interfaces.


Sure, let's explore Java Generics and Type Inference in detail with code examples.

## Java Generics and Type Inference

Generics were introduced in Java 5 to provide a way to write reusable code that can work with different types while maintaining type safety. This means you can create classes, interfaces, and methods that can work with any data type, promoting code reusability and eliminating the need for explicit type casting.

### Understanding Generics and Their Benefits

Before generics, Java relied on object types, which meant that objects of any non-primitive type could be stored in collections like `ArrayList` or `HashSet`. However, this approach led to potential runtime errors due to type casting and lack of type safety.

With generics, you can define type parameters for classes and interfaces, allowing you to specify the type of objects they will work with. This ensures type safety at compile-time, catching potential errors early and making your code more robust.

Here's an example of a generic class `Box` that can hold any type of object:

```java
public class Box<T> {
    private T item;

    public void set(T item) {
        this.item = item;
    }

    public T get() {
        return item;
    }
}
```

In this example, `T` is a type parameter that represents the type of object the `Box` class will hold. We can create instances of `Box` for different types, like so:

```java
Box<String> stringBox = new Box<>();
stringBox.set("Hello");
String value = stringBox.get(); // value = "Hello"

Box<Integer> intBox = new Box<>();
intBox.set(42);
int number = intBox.get(); // number = 42
```

By using generics, we can write reusable code that works with different types without needing to resort to object types and explicit type casting. This improves code safety, readability, and maintainability.

### Type Inference and Diamond Operator

Java 7 introduced type inference and the diamond operator (`<>`) to make working with generics more concise and readable.

Type inference allows the compiler to automatically infer the type arguments based on the context, eliminating the need to explicitly specify them in certain cases.

Here's an example of type inference:

```java
List<String> names = new ArrayList<>(); // Type inferred from the left-hand side
```

In this case, the compiler can infer that the `ArrayList` should be created with a type parameter of `String` based on the declaration of the `names` variable.

The diamond operator is a shorthand syntax for specifying type arguments when creating instances of generic classes or constructor calls.

```java
Box<Integer> intBox = new Box<>(); // Diamond operator
```

Instead of specifying the type parameter `<Integer>` on both sides, we can use the diamond operator `<>` on the right-hand side, and the compiler will infer the type from the left-hand side.

### Bounded Type Parameters and Wildcards

Sometimes, you may want to restrict the types that can be used as type arguments for a generic class or method. This is where bounded type parameters and wildcards come into play.

**Bounded Type Parameters**

Bounded type parameters allow you to specify a bound (or constraint) on the type parameter, restricting the types that can be used as arguments.

For example, you can define a generic class that only accepts types that extend a certain class or implement a certain interface:

```java
public class NumberBox<T extends Number> {
    private T item;

    public void set(T item) {
        this.item = item;
    }

    public T get() {
        return item;
    }
}
```

In this example, the type parameter `T` is bounded to extend the `Number` class, which means that only classes that extend `Number` (like `Integer`, `Double`, `Float`, etc.) can be used as type arguments for `NumberBox`.

**Wildcards**

Wildcards are used to represent an unknown type in generic programming. They provide a way to specify flexible type constraints when working with generic classes or methods.

There are three types of wildcards:

1. Unbounded wildcard (`?`): Represents any type.
2. Upper bounded wildcard (`? extends Type`): Represents any type that extends or implements the specified type.
3. Lower bounded wildcard (`? super Type`): Represents any type that is a supertype of the specified type.

Here's an example that demonstrates the use of wildcards:

```java
public static void printList(List<? extends Number> list) {
    for (Number number : list) {
        System.out.println(number);
    }
}

public static void main(String[] args) {
    List<Integer> intList = Arrays.asList(1, 2, 3);
    List<Double> doubleList = Arrays.asList(1.0, 2.0, 3.0);

    printList(intList); // Valid, Integer extends Number
    printList(doubleList); // Valid, Double extends Number

    List<Object> objectList = new ArrayList<>();
    objectList.add(new Object());
    printList(objectList); // Invalid, Object does not extend Number
}
```

In this example, the `printList` method takes a list of any type that extends `Number`. This means we can pass lists of `Integer`, `Double`, or any other class that extends `Number`. However, we cannot pass a list of `Object` because `Object` does not extend `Number`.

Wildcards provide flexibility when working with generic types, allowing you to specify constraints on the types that can be used in a particular context.

### Generic methods and classes

Absolutely, let's cover generic methods and classes in detail.

#### Generic Methods

In addition to generic classes and interfaces, Java also supports generic methods. Generic methods allow you to define methods that can work with different types, providing type safety and code reusability.

Here's an example of a generic method that takes two arguments of the same type and returns the maximum value:

```java
public static <T extends Comparable<T>> T max(T a, T b) {
    return a.compareTo(b) > 0 ? a : b;
}
```

In this example:

- `<T extends Comparable<T>>` defines the type parameter `T`, which is bounded by the `Comparable<T>` interface. This ensures that the `compareTo` method can be called on objects of type `T`.
- The method `max` takes two arguments of type `T` and returns an object of type `T`.
- Inside the method, we use the `compareTo` method of the `Comparable` interface to compare the two arguments and return the maximum value.

You can call this generic method with different types that implement the `Comparable` interface:

```java
System.out.println(max(3, 5)); // Output: 5
System.out.println(max("apple", "banana")); // Output: "banana"
```

In the first example, we call `max` with two `int` values, and the method returns `5` (the maximum value). In the second example, we call `max` with two `String` objects, and the method returns `"banana"` (the maximum value based on lexicographic ordering).

Generic methods promote code reusability by allowing you to write a single method that can work with multiple types, rather than creating separate overloaded methods for each type.

#### Generic Classes

As we've seen earlier, you can define generic classes by introducing type parameters. These type parameters can be used throughout the class to define fields, method arguments, and return types.

Here's an example of a generic class called `Pair` that holds two objects of potentially different types:

```java
public class Pair<T, U> {
    private T first;
    private U second;

    public Pair(T first, U second) {
        this.first = first;
        this.second = second;
    }

    public T getFirst() {
        return first;
    }

    public U getSecond() {
        return second;
    }
}
```

In this example, the `Pair` class has two type parameters: `T` and `U`. The class has two fields, `first` of type `T` and `second` of type `U`, along with a constructor and getter methods for each field.

You can create instances of the `Pair` class with different type arguments:

```java
Pair<String, Integer> pair1 = new Pair<>("hello", 42);
System.out.println(pair1.getFirst()); // Output: "hello"
System.out.println(pair1.getSecond()); // Output: 42

Pair<Double, Boolean> pair2 = new Pair<>(3.14, true);
System.out.println(pair2.getFirst()); // Output: 3.14
System.out.println(pair2.getSecond()); // Output: true
```

In the first example, we create a `Pair` instance with types `String` and `Integer`. In the second example, we create a `Pair` instance with types `Double` and `Boolean`.

Generic classes provide a way to write reusable and type-safe code that can work with different types. They promote code reusability, type safety, and flexibility in your applications.

Generics, type inference, bounded type parameters, and wildcards are powerful features in Java that promote code reusability, type safety, and flexibility. By understanding and using these features effectively, you can write more robust and maintainable code.

## Java Reflection API and Annotations

The Java Reflection API provides a way to inspect and manipulate classes, interfaces, fields, methods, and constructors at runtime. This powerful feature allows you to write highly dynamic and flexible code, enabling scenarios such as:

1. Analyzing the structure of classes at runtime
2. Creating instances of classes dynamically
3. Invoking methods and accessing fields dynamically
4. Modifying the behavior of classes, methods, and fields at runtime

### Reflection API Basics and Use Cases

The core classes in the Reflection API are:

- `Class`: Represents a class or an interface.
- `Field`: Represents a field of a class.
- `Method`: Represents a method of a class.
- `Constructor`: Represents a constructor of a class.

Here's an example that demonstrates how to use the Reflection API to inspect a class and its members:

```java
import java.lang.reflect.Field;
import java.lang.reflect.Method;

public class ReflectionExample {
    private int value = 42;
    private static final double PI = 3.14159;

    public void sayHello(String name) {
        System.out.println("Hello, " + name + "!");
    }

    public static void main(String[] args) throws Exception {
        // Get the Class instance for ReflectionExample
        Class<?> clazz = ReflectionExample.class;

        // Get all declared fields
        Field[] fields = clazz.getDeclaredFields();
        for (Field field : fields) {
            System.out.println("Field: " + field.getName());
        }

        // Get all declared methods
        Method[] methods = clazz.getDeclaredMethods();
        for (Method method : methods) {
            System.out.println("Method: " + method.getName());
        }

        // Create an instance of ReflectionExample
        ReflectionExample instance = (ReflectionExample) clazz.getDeclaredConstructor().newInstance();

        // Invoke the sayHello method
        Method sayHelloMethod = clazz.getDeclaredMethod("sayHello", String.class);
        sayHelloMethod.invoke(instance, "Alice");
    }
}
```

Output:
```
Field: value
Field: PI
Method: sayHello
Method: main
Hello, Alice!
```

In this example, we first obtain the `Class` instance for `ReflectionExample` using `ReflectionExample.class`. We then use various methods of the `Class` class to inspect the declared fields and methods of the class.

Next, we create an instance of `ReflectionExample` using the `getDeclaredConstructor().newInstance()` method. Finally, we invoke the `sayHello` method dynamically using the `getDeclaredMethod` and `invoke` methods.

### Annotations and Their Applications

Annotations are a form of metadata that can be associated with various elements in Java code, such as classes, methods, fields, and parameters. They provide a way to attach additional information to these elements, which can be accessed at runtime using reflection.

Some common use cases for annotations include:

1. Configuration and deployment settings
2. Code generation and processing
3. Compiler instructions and validations
4. Runtime behavior modifications

Here's an example of a custom annotation and its usage:

```java
import java.lang.annotation.ElementType;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.annotation.Target;

@Target(ElementType.METHOD)
@Retention(RetentionPolicy.RUNTIME)
@interface LogMethod {
    String value() default "Method called";
}

public class AnnotationExample {
    @LogMethod("Entering sayHello method")
    public void sayHello(String name) {
        System.out.println("Hello, " + name + "!");
    }

    public static void main(String[] args) throws Exception {
        AnnotationExample instance = new AnnotationExample();
        instance.sayHello("Alice");

        // Get the Method instance for sayHello
        Method method = AnnotationExample.class.getDeclaredMethod("sayHello", String.class);

        // Check if the method is annotated with LogMethod
        if (method.isAnnotationPresent(LogMethod.class)) {
            LogMethod annotation = method.getAnnotation(LogMethod.class);
            System.out.println(annotation.value());
        }
    }
}
```

Output:
```
Entering sayHello method
Hello, Alice!
```

In this example, we define a custom annotation `@LogMethod` using the `@interface` syntax. The `@Target` annotation specifies that the `@LogMethod` annotation can only be applied to methods, and the `@Retention` annotation specifies that the annotation should be retained at runtime.

We then apply the `@LogMethod` annotation to the `sayHello` method, providing a custom message as the annotation value.

In the `main` method, we first invoke the `sayHello` method. Then, we use reflection to get the `Method` instance for `sayHello` and check if it is annotated with `@LogMethod`. If the annotation is present, we retrieve its value using the `getAnnotation` method and print it.

### Runtime Annotation Processing

Annotations can be processed at runtime using reflection and annotation processing tools. The `java.lang.reflect.AnnotatedElement` interface provides methods to access annotations associated with various program elements, such as classes, methods, and fields.

Here's an example that demonstrates runtime annotation processing:

```java
import java.lang.annotation.ElementType;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.annotation.Target;

@Target(ElementType.TYPE)
@Retention(RetentionPolicy.RUNTIME)
@interface LogClass {
    String value();
}

@LogClass("This is the MyClass annotation")
public class MyClass {
    public void doSomething() {
        System.out.println("Doing something...");
    }

    public static void main(String[] args) {
        MyClass instance = new MyClass();
        instance.doSomething();

        LogClass annotation = MyClass.class.getAnnotation(LogClass.class);
        System.out.println(annotation.value());
    }
}
```

Output:
```
Doing something...
This is the MyClass annotation
```

In this example, we define a custom annotation `@LogClass` that can be applied to classes. We then apply this annotation to the `MyClass` class, providing a custom message as the annotation value.

In the `main` method, we create an instance of `MyClass` and invoke the `doSomething` method. Then, we use the `getAnnotation` method of the `Class` class to retrieve the `@LogClass` annotation associated with the `MyClass` class and print its value.

Runtime annotation processing is widely used in various frameworks and libraries for configuration, dependency injection, and other purposes.

### Dynamic Class Loading and Object Creation

The Reflection API also provides the capability to dynamically load classes and create instances of objects at runtime. This is particularly useful in scenarios where the class names or types are not known until runtime, such as plugin systems or dynamic module loading.

Here's an example that demonstrates dynamic class loading and object creation:

```java
public class DynamicClassLoading {
    public static void main(String[] args) throws Exception {
        // Load a class dynamically
        ClassLoader classLoader = DynamicClassLoading.class.getClassLoader();
        Class<?> clazz = classLoader.loadClass("com.example.MyClass");

        // Create an instance of the loaded class
        Object instance = clazz.getDeclaredConstructor().newInstance();

        // Invoke a method on the instance
        Method method = clazz.getDeclaredMethod("doSomething");
        method.invoke(instance);
    }
}
```

In this example, we first obtain the `ClassLoader` instance using the `getClassLoader` method of the `DynamicClassLoading` class. We then use the `loadClass` method of the `ClassLoader` to dynamically load the `com.example.MyClass` class.

Next, we create an instance of the loaded class using the `getDeclaredConstructor().newInstance()` method. Finally, we obtain the `Method` instance for the `doSomething` method of the loaded class and invoke it using the `invoke` method.

Note that for this example to work, you need to have a class named `com.example.MyClass` with a default constructor and a `doSomething` method in your classpath.

Dynamic class loading and object creation are powerful features of the Reflection API, enabling scenarios such as plugin systems, dynamic class reloading, and more.

## Streams API and parallel processing

The Streams API, introduced in Java 8, provides a functional-style approach to processing collections of data. It offers a powerful and expressive way to perform operations on streams of elements, such as filtering, mapping, sorting, and reducing. Streams can be created from various data sources, including collections, arrays, and I/O channels.

### Introduction to Streams API

A stream is a sequence of elements that supports various operations to transform or perform calculations on those elements. Unlike traditional collections, streams do not store elements; instead, they compute elements on-the-fly as they are consumed.

Here's a simple example that demonstrates the basic usage of streams:

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class StreamsExample {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

        // Filter out even numbers
        List<Integer> evenNumbers = numbers.stream()
                                           .filter(n -> n % 2 == 0)
                                           .collect(Collectors.toList());
        System.out.println("Even numbers: " + evenNumbers); // [2, 4, 6, 8, 10]

        // Calculate the sum of all numbers
        int sum = numbers.stream()
                         .mapToInt(n -> n)
                         .sum();
        System.out.println("Sum: " + sum); // 55
    }
}
```

In this example, we create a list of integers and perform two operations using streams:

1. Filter out even numbers using the `filter` operation and collect the results into a new list.
2. Calculate the sum of all numbers using the `mapToInt` and `sum` operations.

Streams provide a declarative and concise way to express data processing operations, making the code more readable and maintainable.

### Intermediate and Terminal Operations

Streams operations can be classified into two categories: intermediate and terminal operations.

**Intermediate Operations**:
Intermediate operations are lazy, meaning they do not perform any actual computations until a terminal operation is invoked. They transform the stream into another stream by applying operations like `filter`, `map`, `sorted`, and `distinct`. Some common intermediate operations include:

- `filter(Predicate)`: Filters elements based on a given predicate.
- `map(Function)`: Applies a function to each element and returns a new stream.
- `sorted()`: Sorts the elements of the stream.
- `distinct()`: Returns a stream with distinct elements.
- `skip(long n)`: Skips the first `n` elements of the stream.
- `limit(long maxSize)`: Limits the stream to the first `maxSize` elements.

**Terminal Operations**:
Terminal operations consume the stream and perform a final computation, such as aggregating elements, finding a specific element, or storing elements in a collection. Some common terminal operations include:

- `forEach(Consumer)`: Performs an action on each element of the stream.
- `reduce(BinaryOperator)`: Reduces the elements of the stream to a single value using a binary operator.
- `collect(Collector)`: Collects the elements of the stream into a collection (e.g., `List`, `Set`, or `Map`).
- `count()`: Returns the count of elements in the stream.
- `anyMatch(Predicate)`: Returns `true` if any element matches the given predicate.
- `allMatch(Predicate)`: Returns `true` if all elements match the given predicate.

Here's an example that demonstrates the use of intermediate and terminal operations:

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class StreamOperations {
    public static void main(String[] args) {
        List<String> words = Arrays.asList("apple", "banana", "cherry", "date", "elderberry");

        // Intermediate operations
        List<String> longWords = words.stream()
                                      .filter(w -> w.length() > 5)
                                      .sorted()
                                      .map(String::toUpperCase)
                                      .distinct()
                                      .collect(Collectors.toList());
        System.out.println("Long words: " + longWords); // [BANANA, CHERRY, ELDERBERRY]

        // Terminal operations
        long count = words.stream()
                          .filter(w -> w.startsWith("a"))
                          .count();
        System.out.println("Words starting with 'a': " + count); // 1

        boolean hasLongWord = words.stream()
                                   .anyMatch(w -> w.length() > 10);
        System.out.println("Has a word longer than 10 characters: " + hasLongWord); // false
    }
}
```

In this example, we perform various stream operations on a list of strings:

1. Use intermediate operations like `filter`, `sorted`, `map`, and `distinct` to obtain a list of distinct, uppercase, sorted words with more than 5 characters.
2. Use the terminal operation `count` to count the number of words starting with 'a'.
3. Use the terminal operation `anyMatch` to check if there is any word longer than 10 characters.

### Parallel Processing with Streams

One of the powerful features of the Streams API is the ability to leverage parallel processing to improve performance on modern multi-core systems. Parallel streams can significantly speed up certain types of operations, such as filtering, mapping, and reduction operations, by dividing the work among multiple threads.

To create a parallel stream, you can use the `parallelStream()` method instead of `stream()`. Here's an example that demonstrates parallel processing with streams:

```java
import java.util.Arrays;
import java.util.List;

public class ParallelStreams {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

        // Sequential sum
        long startTime = System.currentTimeMillis();
        int sequentialSum = numbers.stream()
                                   .mapToInt(n -> n)
                                   .sum();
        long sequentialTime = System.currentTimeMillis() - startTime;

        // Parallel sum
        startTime = System.currentTimeMillis();
        int parallelSum = numbers.parallelStream()
                                 .mapToInt(n -> n)
                                 .sum();
        long parallelTime = System.currentTimeMillis() - startTime;

        System.out.println("Sequential sum: " + sequentialSum + " (Time: " + sequentialTime + " ms)");
        System.out.println("Parallel sum: " + parallelSum + " (Time: " + parallelTime + " ms)");
    }
}
```

In this example, we calculate the sum of a list of integers using both sequential and parallel streams. The `parallelStream()` method splits the stream into multiple sub-streams, and each sub-stream is processed by a separate thread. The results from the sub-streams are then combined to produce the final result.

The output will show the sum and the execution time for both sequential and parallel streams. Typically, the parallel stream execution time will be shorter than the sequential stream execution time, especially for larger data sets and computationally intensive operations.

It's important to note that parallel streams may not always provide better performance, as there is some overhead involved in creating and merging sub-streams. Additionally, certain operations, such as those involving significant data sharing or synchronization, may not benefit from parallel processing.

When using parallel streams, it's recommended to follow best practices, such as avoiding side-effects, stateless operations, and avoiding unnecessary boxing and unboxing operations, to ensure optimal performance and correctness.

The Streams API and parallel processing provide a powerful and expressive way to process data in Java, enabling more concise and efficient code while taking advantage of modern multi-core hardware.

## Java Debugging, Logging, and Testing

Debugging is an essential part of the software development process. It involves identifying and fixing errors or defects in your code. Java provides several debugging techniques and tools to help you troubleshoot and resolve issues.

### Debugging Techniques and Tools

**1. Print Statements**
One of the simplest debugging techniques is using print statements to output variable values or trace the execution flow of your program. This can help you understand where the issue might be occurring.

```java
System.out.println("Value of x: " + x);
```

**2. Debugger**
Java provides a powerful debugger that allows you to step through your code line by line, set breakpoints, inspect variable values, and more. Most IDEs (Integrated Development Environments) like Eclipse, IntelliJ IDEA, and NetBeans have built-in debuggers that make debugging easier.

**3. Logging**
Logging is a more structured and efficient way of debugging than using print statements. Logging frameworks like Log4j and SLF4J provide a flexible and configurable way to log messages, errors, and other information during program execution.

**4. Profilers**
Profilers are tools that help you analyze the performance of your application. They can identify performance bottlenecks, such as slow methods, excessive memory usage, or inefficient algorithms. Popular profilers for Java include VisualVM, JProfiler, and YourKit.

**5. Debugging with IDEs**
Most IDEs provide powerful debugging features, including breakpoints, step-through execution, variable inspection, and expression evaluation. These tools can significantly aid in the debugging process.

### Logging Frameworks (e.g., Log4j, SLF4J)

Logging frameworks provide a structured and configurable way to log messages, errors, and other information during program execution. Two popular logging frameworks in Java are Log4j and SLF4J.

**Log4j**
Log4j is a widely used logging framework for Java. It provides a flexible and configurable logging system that allows you to control the level of logging, log message formatting, and log message destinations (console, file, database, etc.).

Here's an example of using Log4j:

```java
import org.apache.logging.log4j.LogManager;
import org.apache.logging.log4j.Logger;

public class LoggingExample {
    private static final Logger logger = LogManager.getLogger(LoggingExample.class);

    public static void main(String[] args) {
        logger.debug("This is a debug message");
        logger.info("This is an info message");
        logger.warn("This is a warning message");
        logger.error("This is an error message");
    }
}
```

**SLF4J**
SLF4J (Simple Logging Facade for Java) is a logging abstraction layer that allows you to use different logging frameworks (like Log4j or Logback) without modifying your code. It provides a clean and simple API for logging.

Here's an example of using SLF4J with Logback as the underlying logging framework:

```java
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

public class LoggingExample {
    private static final Logger logger = LoggerFactory.getLogger(LoggingExample.class);

    public static void main(String[] args) {
        logger.debug("This is a debug message");
        logger.info("This is an info message");
        logger.warn("This is a warning message");
        logger.error("This is an error message");
    }
}
```

Both Log4j and SLF4J provide features like log level filtering, log message formatting, and log message routing to different destinations (console, file, database, etc.). Choosing between them often comes down to personal preference, project requirements, and the logging framework used by other libraries in your project.

### Unit Testing with JUnit

Unit testing is the practice of testing individual units or components of your code to ensure they work as expected. JUnit is a popular unit testing framework for Java that provides a simple and powerful way to write and run unit tests.

#### Introduction to Unit Testing with JUnit

JUnit provides annotations and assertions to help you write and organize your unit tests. Here's an example of a simple unit test using JUnit:

```java
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.assertEquals;

public class CalculatorTest {
    @Test
    public void testAdd() {
        Calculator calculator = new Calculator();
        int result = calculator.add(2, 3);
        assertEquals(5, result, "2 + 3 should equal 5");
    }
}
```

In this example, we have a test case for the `add` method of the `Calculator` class. The `@Test` annotation marks the method as a test case, and `assertEquals` is an assertion that checks whether the actual result matches the expected result.

JUnit provides various annotations and assertions for different scenarios, such as:

- `@BeforeEach` and `@AfterEach`: Methods annotated with these are executed before and after each test case, respectively.
- `@BeforeAll` and `@AfterAll`: Methods annotated with these are executed once before and after all test cases in a test class, respectively.
- `assertNotNull`, `assertTrue`, `assertFalse`: Assertions for checking null values, boolean conditions, and more.
- `assertArrayEquals`, `assertIterableEquals`: Assertions for comparing arrays and iterables.

JUnit also provides features for test execution, test suites, parameterized tests, and integration with build tools like Maven and Gradle.

### Test-driven Development (TDD) Principles

Test-driven Development (TDD) is a software development process that emphasizes writing tests before writing the actual code. It follows a cycle of:

1. **Write a failing test**: Start by writing a test case for a specific feature or functionality that you want to implement.
2. **Write the code**: Write the minimum code necessary to make the test pass.
3. **Refactor**: Once the test passes, refactor the code to improve its design, readability, and maintainability.
4. **Repeat**: Repeat the cycle for the next feature or functionality.

TDD has several benefits, including:

- **Better code design**: By writing tests first, you are forced to think about the design and interface of your code from the beginning.
- **Regression prevention**: Having a comprehensive suite of tests helps prevent regressions when making changes to the codebase.
- **Documentation**: Well-written tests can serve as documentation for the expected behavior of your code.
- **Confidence in refactoring**: With a solid suite of tests, you can refactor your code with confidence, knowing that any changes won't break existing functionality.

Here's an example of how the TDD cycle might look for implementing a simple `StringUtils` class with a `reverse` method:

1. **Write a failing test**:

```java
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.assertEquals;

public class StringUtilsTest {
    @Test
    public void testReverse() {
        String input = "hello";
        String expected = "olleh";
        String actual = StringUtils.reverse(input);
        assertEquals(expected, actual, "The reverse of 'hello' should be 'olleh'");
    }
}
```

2. **Write the code to make the test pass**:

```java
public class StringUtils {
    public static String reverse(String input) {
        StringBuilder sb = new StringBuilder();
        for (int i = input.length() - 1; i >= 0; i--) {
            sb.append(input.charAt(i));
        }
        return sb.toString();
    }
}
```

3. **Refactor (if necessary)**
4. **Repeat for the next feature or functionality**

By following the TDD principles, you can build high-quality, well-designed, and maintainable code with a comprehensive suite of tests.

Debugging, logging, and testing are essential practices in software development that help ensure code quality, maintainability, and reliability. Java provides powerful tools and frameworks for each of these areas, including debuggers, logging frameworks like Log4j and SLF4J, and unit testing frameworks like JUnit. Additionally, adopting methodologies like Test-Driven Development can further improve code quality and design.

# Unit 2: User Interface Development

In modern software development, user interfaces (UIs) play a crucial role in providing an intuitive and engaging experience for end-users. Whether you're building desktop applications, mobile apps, or web-based solutions, a well-designed UI can greatly enhance the overall usability and appeal of your software.

This unit will delve into Java's powerful UI technologies, focusing on two widely used frameworks: Swing and JavaFX. You'll learn how to create visually appealing and interactive user interfaces that cater to various platforms and devices.

**Java Swing**

Swing is a comprehensive set of GUI (Graphical User Interface) components and libraries for building cross-platform desktop applications in Java. It provides a rich set of widgets, such as buttons, menus, text fields, and tables, as well as advanced components like trees, sliders, and tabbed panes. In this unit, you'll explore the fundamentals of Swing, including:

- Swing components and containers
- Layout managers and custom layouts
- Event handling mechanisms
- Threading and concurrency in Swing applications
- Advanced Swing features like drag-and-drop, undo/redo, and accessibility

**JavaFX and FXML**

JavaFX is a modern, feature-rich UI toolkit for creating rich client applications that can run across various platforms, including desktops, mobile devices, and web browsers. It offers a wide range of UI components, graphics, and multimedia capabilities, making it a powerful choice for building visually stunning and interactive applications.

In this unit, you'll learn about:

- JavaFX architecture and components
- Creating user interfaces with FXML (JavaFX Markup Language)
- Styling and skinning JavaFX applications with CSS
- Working with JavaFX charts, graphs, and 3D graphics
- Animations and media support in JavaFX
- Leveraging tools like Scene Builder for visual UI design

**Event Handling and UI Design Patterns**

Effective event handling is crucial for building responsive and interactive user interfaces. This unit will cover event-driven programming concepts and explore various UI design patterns that promote code reusability, maintainability, and separation of concerns.

You'll learn about:

- Event handling mechanisms in Java
- Common UI design patterns like Model-View-Controller (MVC), Model-View-Presenter (MVP), and Model-View-ViewModel (MVVM)
- Implementing design patterns in Swing and JavaFX applications
- Best practices for UI design and usability

Throughout this unit, you'll gain hands-on experience by building various UI components, layouts, and complete applications using both Swing and JavaFX. You'll learn how to create visually appealing interfaces, handle user interactions, and apply design patterns to ensure a well-structured and maintainable codebase.

By the end of this unit, you'll have a solid understanding of Java's UI technologies and the ability to create modern, responsive, and user-friendly applications that deliver an exceptional user experience.

## Introduction to Java UI Technologies

Java provides several technologies and frameworks for building user interfaces (UIs) for desktop applications, web applications, and mobile applications. In this section, we'll explore some of the key UI technologies in Java, their limitations, alternatives, and the differences between them.

### Overview of JFC, Applet, AWT, Swing, JavaFX and SWT

**Java Foundation Classes (JFC)**: JFC is an umbrella term that encompasses several UI packages in Java, including Swing, Java 2D, Accessibility, Drag and Drop, and other utilities.

**Applet**: An Applet is a small Java program that can be embedded in a web page and executed by a Java-enabled web browser. Applets were designed to provide interactive content on web pages, but they are now considered a deprecated technology due to security concerns and lack of support in modern browsers.

**Abstract Window Toolkit (AWT)**: AWT is one of the earliest UI toolkits in Java, providing a set of lightweight components for building user interfaces. It was designed to be platform-independent and serves as the foundation for other UI toolkits like Swing.

**Swing**: Swing is a more advanced and comprehensive UI toolkit built on top of AWT. It provides a rich set of components, such as buttons, menus, tables, trees, and sliders, as well as advanced features like pluggable look-and-feel, drag-and-drop support, and accessibility features.

#### Limitations and Alternatives of AWT & Swing

While AWT and Swing have been widely used for building desktop applications in Java, they have some limitations:

1. **Performance**: AWT and Swing can sometimes suffer from performance issues, especially when dealing with complex UIs or graphics-intensive applications.
2. **Limited support for modern UI designs**: AWT and Swing were designed in the early days of Java and may not provide the best support for modern UI design patterns and aesthetics.
3. **Lack of modern features**: With the advent of new technologies and user expectations, AWT and Swing may lack support for features like hardware acceleration, multi-touch support, and high-resolution displays.

To address these limitations, alternative UI technologies have emerged:

1. **JavaFX**: JavaFX is a modern UI toolkit introduced by Oracle that provides a rich set of UI components, graphics, media, and web technologies. It supports hardware acceleration, high-performance rendering, and modern UI designs.
2. **SWT (Standard Widget Toolkit)**: SWT is a UI toolkit developed by the Eclipse Foundation that provides a lightweight and platform-native widget set. It integrates well with the Eclipse IDE and is often used for building Eclipse-based applications.
3. **Third-party libraries and frameworks**: There are various third-party libraries and frameworks that provide alternative UI solutions, such as Apache Pivot, SmartGWT, and Vaadin.

### Comparison of various Java UI technologies

| Feature | AWT | Swing | JavaFX | SWT |
| --- | --- | --- | --- | --- |
| Architecture | Lightweight, platform-native | Heavyweight, cross-platform | Cross-platform, hardware-accelerated | Lightweight, platform-native |
| Component Set | Basic components (buttons, labels, etc.) | Rich set of advanced components (tables, trees, sliders, etc.) | Rich set of modern components, graphics, and multimedia support | Basic components mapped to native widgets |
| Look and Feel | Inherits native platform look and feel | Customizable cross-platform look and feel (Metal, Third-party libraries) | Customizable modern look and feel (CSS, built-in themes) | Inherits native platform look and feel |
| Event Handling | Event delegation model | Event delegation model with lightweight UI controls | Event handling based on the JavaFX Scene Graph | Event delegation model |
| Threading Model | Not thread-safe (Single Threaded) | Single-threaded model (Event Dispatch Thread) | Thread-safe, supports multithreading | Thread-safe, supports multithreading |
| Graphics | Basic 2D graphics (java.awt.Graphics) | Improved 2D graphics (java.awt.Graphics2D) | Advanced 2D and 3D graphics (JavaFX Scene Graph, hardware acceleration) | Lightweight graphics based on platform-native rendering |
| Multimedia | Limited support | Limited support | Rich multimedia support (audio, video, animations, etc.) | Limited support |
| Web Integration | Applets (deprecated) | Java Web Start (deprecated) | WebView component for rendering web content | Browser Integration (Eclipse, RAP) |
| IDE Integration | Limited | Supported by most IDEs | Supported by most IDEs, Scene Builder for visual design | Tightly integrated with Eclipse IDE |
| Deployment | Desktop applications | Desktop applications | Desktop, mobile, and web applications | Desktop applications |
| Performance | Limited, platform-dependent | Better than AWT, but can be slow for complex UIs | Designed for high performance, hardware acceleration | Lightweight, decent performance |
| Community and Support | Mature, but declining | Mature, but declining | Actively developed and supported by OpenJavaFX | Active community support (Eclipse Foundation) |
| Cross-Platform Support | Limited to platforms with Java support | Cross-platform with consistent look and feel | Cross-platform with modern look and feel | Limited to platforms with Java support |
| Modern UI Design | Limited support | Limited support | Designed for modern UI design patterns and aesthetics | Limited support |

This table highlights the key differences and features of the various UI toolkits available for Java. While AWT and Swing have been the traditional choices for desktop applications, JavaFX and SWT offer more modern and feature-rich alternatives, particularly for cross-platform support, graphics, multimedia, and modern UI design.

It's important to note that the choice of UI toolkit often depends on the specific requirements of your project, such as the target platform, performance needs, UI design goals, and integration with existing frameworks or IDEs.

## Java Swing

Swing is a comprehensive GUI toolkit for building desktop applications in Java. It provides a rich set of components, containers, layout managers, event handling mechanisms, and threading models to create interactive and visually appealing user interfaces.

### Swing Components and Containers

Swing offers a wide range of components that can be used to build user interfaces. These components are organized into different categories based on their functionality:

1. **Basic Controls**: Components like buttons, labels, text fields, and checkboxes.
2. **Complex Controls**: Components like tables, trees, sliders, and progress bars.
3. **Containers**: Components that can hold other components, such as frames, panels, and dialogs.

Here's an example that demonstrates the usage of some basic Swing components:

```java
import javax.swing.*;
import java.awt.*;

public class SwingComponentsExample extends JFrame {
    public SwingComponentsExample() {
        setTitle("Swing Components Example");
        setSize(400, 300);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new FlowLayout());

        // Add basic components
        JButton button = new JButton("Click Me");
        add(button);

        JLabel label = new JLabel("Enter your name:");
        add(label);

        JTextField textField = new JTextField(20);
        add(textField);

        JCheckBox checkBox = new JCheckBox("Subscribe to newsletter");
        add(checkBox);
    }

    public static void main(String[] args) {
        SwingUtilities.invokeLater(new Runnable() {
            public void run() {
                new SwingComponentsExample().setVisible(true);
            }
        });
    }
}
```

In this example, we create a `JFrame` and add various Swing components to it, including a `JButton`, `JLabel`, `JTextField`, and `JCheckBox`. The components are added to the frame using the `add` method, and the layout is set to `FlowLayout`.

### Layout Managers and Custom Layouts

Layout managers in Swing are responsible for arranging and positioning components within a container. Swing provides several built-in layout managers, such as `FlowLayout`, `BorderLayout`, `GridLayout`, `BoxLayout`, and `GridBagLayout`. You can also create custom layout managers by implementing the `LayoutManager` interface.

Here's an example that demonstrates the usage of the `GridLayout` layout manager:

```java
import javax.swing.*;
import java.awt.*;

public class GridLayoutExample extends JFrame {
    public GridLayoutExample() {
        setTitle("Grid Layout Example");
        setSize(400, 300);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // Create a panel with a 3x3 grid layout
        JPanel panel = new JPanel(new GridLayout(3, 3));

        // Add buttons to the panel
        for (int i = 1; i <= 9; i++) {
            JButton button = new JButton("Button " + i);
            panel.add(button);
        }

        // Add the panel to the frame
        add(panel, BorderLayout.CENTER);
    }

    public static void main(String[] args) {
        SwingUtilities.invokeLater(new Runnable() {
            public void run() {
                new GridLayoutExample().setVisible(true);
            }
        });
    }
}
```

In this example, we create a `JPanel` with a `GridLayout` of 3 rows and 3 columns. We then add nine `JButton` instances to the panel, and the panel is added to the `JFrame` using the `BorderLayout.CENTER` position.

### Swing Event Handling

Swing provides an event handling mechanism based on the Observer design pattern. Components can generate events, and other objects can register as listeners to receive and handle these events.

Here's an example that demonstrates event handling in Swing:

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class SwingEventHandlingExample extends JFrame implements ActionListener {
    private JLabel label;

    public SwingEventHandlingExample() {
        setTitle("Event Handling Example");
        setSize(400, 300);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new FlowLayout());

        JButton button = new JButton("Click Me");
        button.addActionListener(this);
        add(button);

        label = new JLabel("No button clicked yet");
        add(label);
    }

    public void actionPerformed(ActionEvent e) {
        label.setText("Button clicked!");
    }

    public static void main(String[] args) {
        SwingUtilities.invokeLater(new Runnable() {
            public void run() {
                new SwingEventHandlingExample().setVisible(true);
            }
        });
    }
}
```

In this example, we create a `JFrame` with a `JButton` and a `JLabel`. The `JButton` is registered with an `ActionListener` (which is implemented by the `SwingEventHandlingExample` class itself). When the button is clicked, the `actionPerformed` method of the `ActionListener` is called, and the text of the `JLabel` is updated to "Button clicked!".

### Swing Threading and Concurrency

Swing follows a single-threaded model, where all UI updates must be performed on the Event Dispatch Thread (EDT) to ensure thread safety and prevent race conditions. If you attempt to update the UI from a non-EDT thread, you may encounter threading issues or even deadlocks.

Here's an example that demonstrates how to update the UI from a non-EDT thread:

```java
import javax.swing.*;
import java.awt.*;
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class SwingThreadingExample extends JFrame {
    private JLabel label;

    public SwingThreadingExample() {
        setTitle("Threading Example");
        setSize(400, 300);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new FlowLayout());

        label = new JLabel("Initial text");
        add(label);

        // Update the label from a non-EDT thread
        ExecutorService executor = Executors.newSingleThreadExecutor();
        executor.execute(new Runnable() {
            public void run() {
                try {
                    Thread.sleep(2000); // Simulate some long-running task
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }

                // Update the UI on the EDT
                SwingUtilities.invokeLater(new Runnable() {
                    public void run() {
                        label.setText("Updated text");
                    }
                });
            }
        });
    }

    public static void main(String[] args) {
        SwingUtilities.invokeLater(new Runnable() {
            public void run() {
                new SwingThreadingExample().setVisible(true);
            }
        });
    }
}
```

In this example, we create a `JLabel` and add it to the `JFrame`. We then start a new thread using an `ExecutorService`, which simulates a long-running task by sleeping for 2 seconds. After the task is completed, we update the text of the `JLabel` by calling `SwingUtilities.invokeLater` to ensure that the UI update is performed on the EDT.

By following the single-threaded model and using the `SwingUtilities.invokeLater` method, you can safely update the UI from non-EDT threads, preventing threading issues and ensuring a smooth user experience.

Swing provides a comprehensive set of components, layout managers, event handling mechanisms, and threading models to build robust and interactive desktop applications. By understanding and leveraging these features, you can create visually appealing and user-friendly interfaces that meet your application's requirements.

## JavaFX and FXML

### Introduction to JavaFX architecture

### Creating user interfaces with FXML

### Styling with CSS

### JavaFX charts, graphs, 3D, and animations

### Using Scene Builder for visual design

## Event Handling and UI Design Patterns

### Event-driven programming concepts

### UI design patterns (e.g., MVC, MVP, MVVM)

### Implementing design patterns in JavaFX

# Unit 3: Data Persistence and Access

## Database Design and JDBC

### Two-Tier and Three-Tier Database Design

### JDBC basics and database connectivity

### Connection pooling concepts and implementation

### Prepared statements and result set handling

### Transaction management with JDBC

## Object-Relational Mapping (ORM) with Hibernate

### Introduction to ORM and Hibernate

### Mapping entities and relationships

### Hibernate query language (HQL) and criteria API

### Caching and performance optimization with Hibernate

## Java Persistence API (JPA)

### JPA concepts and entity lifecycle

### Entity relationships and inheritance

### JPA query language (JPQL) and native queries

### JPA caching and performance tuning

## Query Optimization and Performance Tuning

### Optimization techniques for JDBC, Hibernate, and JPA

### Identifying and resolving performance bottlenecks

### Indexing and query plan analysis

### Caching strategies and cache invalidation

# Unit 4: Server-Side Development

## Java Servlets and Filters

### Servlet lifecycle and API

### Creating and configuring servlets

### Implementing filters for request processing

### Servlet security and authentication

## JavaServer Pages (JSP)

### JSP syntax and directives

### Expression Language (EL) and JSTL

### MVC pattern with JSP and servlets

### JSP best practices and performance optimization

## Integration of Servlets and JSP

### Combining servlets and JSP for dynamic web pages

### Handling form submissions and validations

### Session management and state maintenance

## RESTful Web Services

### Introduction to REST principles and architecture

### Designing RESTful APIs

### Implementing RESTful endpoints with JAX-RS

### Consuming RESTful services with Java clients

# Unit 5: Modern Java Frameworks & Java for IoT

## Spring Framework (Core, MVC, Security, Data)

### Spring Core concepts (DI, IoC, AOP, POJO)

### Spring MVC for web application development

### Spring Security for authentication and authorization

### Spring Data for data access and persistence

## Spring Boot for Rapid Application Development

### Introduction to Spring Boot

### Auto-configuration and starter dependencies

### Creating RESTful APIs with Spring Boot

### Spring Boot Actuator and monitoring

## Java for IoT

### Overview of IoT concepts and protocols

### Interfacing with Arduino and NodeMCU using Java

### Raspberry Pi programming with Pi4J library

### IoT protocols (MQTT, CoAP) with Java

### Security considerations for IoT applications
