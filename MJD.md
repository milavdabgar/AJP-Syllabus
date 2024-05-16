- Java Generics
- Java Assertions
- Java Logging
- Java Swing
- JavaFX
- Java Lambda Expressions and Functional Interfaces
- Java Modules: Module declaration, Module dependencies, Modular JARs
- Java Enumerations, Autoboxing, and Annotations
- Java Serialization and Deserialization: ObjectInputStream, ObjectOutputStream, Serializable interface, RMI
- Java Remote Method Invocation (RMI)
- RESTful web services using JAX-RS
- Java Reflections
- Java NIO (New I/O): Buffers, Channels, Selectors, File I/O with NIO: Reading and Writing files, FileChannel, ByteBuffer
- Java Networking
- Java Event Handling
- Java AWT
- Java Applets
- Java Servlets
- Java Beans
- Introduction to Java Concurrency API:  Executors, Callables, Futures.
- Introduction to Web Services:  RESTful API Concepts, RESTful web services, JAX-RS and Jersey framework
- Introduction to Design Patterns:  - Creational patterns (e.g., Singleton, Factory), Structural patterns (e.g., Adapter, Facade), Behavioral patterns (e.g., Observer, Strategy), Builder, Decorator, MVC
- Introduction to Spring Framework: Spring Core Features like Dependency Injection, Autowiring.
- Introduction to Spring Boot:  Rapid Application Development with Spring Boot.
- JDBC & ODBC
- Java Hybernate
- Java Servlets: Introduction & Development
- JavaServer Pages (JSP): Introduction & Development
- Integration of Servlets and JSP:  Developing a Complete Web Application with MVC pattern.


## Advanced Java Programming Syllabus
1. Advanced Java Language Features
   1. Java Enumerations, Autoboxing, and Annotations
   2. Lambda expressions and functional interfaces
   3. Java modules and modular programming
   4. Java Serialization and Deserialization
   5. Java Reflection API
   6. Java Concurrency API (Executors, Callables, Futures)
   7. Java Generics
   8. Java Remote Method Invocation (RMI) 
   9.  Java Networking Basics: Socket programming and network protocols
   10. Java NIO (New I/O) and non-blocking I/O
   11. Java Assertions and unit testing
   12. Java Debugging and logging
2. User Interface Development
   1. Java Applets
   2. Event handling
   3. Java AWT (Abstract Window Toolkit)
   4. Java Swing for Desktop Applications
   5. difference between AWT and Swing
   6. Building Rich User Interfaces with JavaFX
3. Java Persistence
   1. ODBC
   2. JDBC
   3. ODBC-JDBC bridge
   4. Object-Relational Mapping (ORM) with Hibernate
   5. Java Persistence API (JPA)
4. Web Development and Frameworks
   1. Java Servlets
   2. JavaServer Pages (JSP)
   3. Integration of Servlets and JSP
   4. RESTful Web Services using JAX-RS
5.  Modern Java Frameworks, Design Patterns & Practices
    1. Design Patterns
      2. Creational patterns (e.g., Singleton, Factory, Builder)
      3. Structural patterns (e.g., Adapter, Facade, Decorator)
      4. Behavioral patterns (e.g., Observer, Strategy, Template Method)
    5. Model-View-Controller (MVC) pattern
    6. Spring Framework (Core, MVC, Data, Security)
    7. Spring Boot for rapid application development
    8. Inversion of Control (IoC) and Dependency Injection (DI)
    9. Aspect-Oriented Programming (AOP)
    10. Microservices Architecture
        1.  Principles of microservices
        2.  Containerization with Docker
        3.  Orchestration with Kubernetes
    11. Continuous Integration and Deployment (CI/CD)
         1.  Jenkins, Travis CI, or similar tools
         2.  Automated testing and deployment pipelines
    12. Java Build Tools:  Introduce build tools like Maven or Gradle for project automation.





Unit 1: Advanced Java Language Features

- Lambda expressions and functional interfaces
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





Unit 1: Advanced Java Language Features (8 hours lecture, 6 hours lab)
- Lambda expressions and functional interfaces (2 hours lecture, 1 hour lab)
  - Introduction to lambda expressions
  - Functional interfaces and their usage
  - Method references and their applications
  - Streams API and parallel processing
- Java Generics and Type Inference (2 hours lecture, 2 hours lab)
  - Understanding generics and their benefits
  - Type inference and diamond operator
  - Bounded type parameters and wildcards
  - Generic methods and classes
- Java Reflection API and Annotations (2 hours lecture, 1 hour lab)
  - Reflection API basics and use cases
  - Annotations and their applications
  - Runtime annotation processing
  - Dynamic class loading and object creation
- Java Debugging & logging (1 hour lecture, 1 hour lab)
  - Debugging techniques and tools
  - Logging frameworks (e.g., Log4j, SLF4J)
  - Best practices for debugging and logging
  - Troubleshooting common Java issues
- Java Unit testing with JUnit (1 hour lecture, 1 hour lab)
  - Introduction to unit testing concepts
  - Writing and running tests with JUnit
  - Test-driven development (TDD) principles
  - Mocking and stubbing with Mockito

Unit 2: User Interface Development (9 hours lecture, 6 hours lab)
- Brief intro of UI Development using Applet & AWT (1 hour lecture)
  - Overview of JFC, Applet, AWT and Swing
    - Features of the Java Foundation Classes
  - Limitations and alternatives
  - Difference between AWT and Swing
- Java Swing (2 hours lecture, 2 hours lab)
  - Swing components and containers
    - Swing Classes Hierarchy, Commonly used Methods of Component class (add(), setSize(), setLayout(), and setVisible()), JApplet, JFrame, JLabel, JTextField, JTextArea, JButton, JCheckBox, JRadioButton, JComboBox, JMenu
  - Layout managers and custom layouts
    - Layout Management: Flow Layout, Border Layout, Card Layout, Box Layout, Grid Layout, Gridbag Layout, Group Layout, Spring Layout
  - Swing event handling
    - Event Handling: Introduction, Action Events, Key Events, Focus Events, Window Event, Mouse Event, Item Events
    - EventListener Interface: ActionListener, KeyListener, FocusListener, WindowListener, MouseListener, MouseMotionListener, ItemListener
  - Swing threading and concurrency
- JavaFX and FXML (4 hours lecture, 2 hours lab)
  - Introduction to JavaFX architecture
  - Creating user interfaces with FXML
  - Styling with CSS
  - JavaFX charts and graphs
  - JavaFX 3D and animations
- Scene Builder for visual design (1 hour lecture, 1 hour lab)
  - Using Scene Builder for UI design
  - Integrating Scene Builder with IDE
  - Best practices for UI design with Scene Builder
- Event Handling and UI Design Patterns (1 hour lecture, 1 hour lab)
  - Event-driven programming concepts
  - UI design patterns (e.g., MVC, MVP, MVVM)
  - Implementing design patterns in JavaFX

Unit 3: Data Persistence and Access (8 hours lecture, 4 hours lab)
- Two-Tier Database Design, Three-Tier Database Design
- JDBC and Connection Pooling (2 hours lecture, 1 hour lab)
  - JDBC basics and database connectivity
  - Connection pooling concepts and implementation
  - Prepared statements and result set handling
  - Transaction management with JDBC
  - The JDBC API: The API components, database operations like creating tables, CRUD (Create, Read, Update, Delete) operations using SQL
  - JDBC - advantages and disadvantages, JDBC drivers, JDBC-ODBC bridge
- Object-Relational Mapping (ORM) with Hibernate (3 hours lecture, 2 hours lab)
  - Introduction to ORM and Hibernate
    - ORM working model, advantages, and ORM tools
    - Architecture of Hibernate and installation steps for IDE
    - Hibernate Properties and supported databases
  - Mapping entities and relationships
  - Hibernate query language (HQL) and criteria API
  - Caching and performance optimization with Hibernate
- Java Persistence API (JPA) (2 hours lecture, 1 hour lab)
  - JPA concepts and entity lifecycle
  - Entity relationships and inheritance
  - JPA query language (JPQL) and native queries
  - JPA caching and performance tuning
- Query optimization and performance tuning (1 hour lecture)
  - Optimization techniques for JDBC, Hibernate, and JPA
  - Identifying and resolving performance bottlenecks
  - Indexing and query plan analysis
  - Caching strategies and cache invalidation

Unit 4: Server Side Development (8 hours lecture, 6 hours lab)
- Java Servlets and Filters (2 hours lecture, 2 hours lab)
  - Servlet lifecycle and API
  - The Java Servlet Development Kit
  - Creating and configuring servlets
    - The Simple Servlet: create and compile servlet source code, start a web browser and request the servlet, example of echo servlet and deployment in Tomcat server
    - The javax.servlet Package: reading database/table records and displaying them using a servlet
  - Implementing filters for request processing
  - Servlet security and authentication
- JavaServer Pages (JSP) (2 hours lecture, 1 hour lab)
  - JSP syntax and directives
    - Components of JSP page: Directives, Comments, Expression, Scriptlets, Declarations, Implicit Objects, Standard Actions and Tag Extensions
    - Elements Created with the INPUT Tag, Elements Created with select and option, textarea Element
  - Implement web applications using JSP Form input elements and validation.
  - Implement web applications using JSP database connection.
    - Create Table using JSP, SELECT, INSERT, DELETE and UPDATE
  - Expression Language (EL) and JSTL
  - MVC pattern with JSP and servlets
  - JSP best practices and performance optimization
- Integration of Servlets and JSP (1 hour lecture, 1 hour lab)
  - Combining servlets and JSP for dynamic web pages
  - Best practices for servlet and JSP integration
  - Handling form submissions and validations
    -  JSP form validation
  - Session management and state maintenance
    - Read and Delete data from cookies, maintain session and track session id, Core tags, SQL tags, XML tags, JSTL functions
    - Implement web applications using JSP Cookies and Session tracking.
- Introduction to RESTful Web Services (1 hour lecture)
  - REST principles and architecture
  - Comparison with SOAP-based web services
  - Designing RESTful APIs
- RESTful Web Services with JAX-RS (2 hours lecture, 2 hours lab)
  - JAX-RS API and annotations
  - Implementing RESTful endpoints
  - Consuming RESTful services with Java clients
  - Exception handling and error responses in JAX-RS

Unit 5: Modern Java Frameworks & Java for IoT (9 hours lecture, 6 hours lab)
- Spring Framework (Core, MVC, Security, Data) (4 hours lecture, 2 hours lab)
  - Spring Core concepts: Dependency Injection (DI), Inversion of Control (IoC), Aspect-oriented programming (AOP), Plain Old Java Object (POJO)
  - Spring MVC for web application development
    - Describe MVC Architecture Layers. Model layer, View layer, and Controller layer.
  - Spring Security for authentication and authorization
  - Spring Data for data access and persistence
- Spring Boot for rapid application development (3 hours lecture, 2 hours lab)
  - Introduction to Spring Boot
  - Auto-configuration and starter dependencies
  - Creating RESTful APIs with Spring Boot
  - Spring Boot Actuator and monitoring
- Java for IoT (2 hours lecture, 2 hours lab)
  - Overview of IoT concepts and protocols
  - Interfacing with Arduino and NodeMCU using Java
  - Raspberry Pi programming with Pi4J library
  - Java frameworks for IoT (e.g., Eclipse IoT, Apache IoTDB)
  - IoT protocols (MQTT, CoAP) with Java
  - Security considerations for IoT applications

Total: 42 hours lecture, 28 hours lab


Unit 1: Advanced Java Language Features (8 hours lecture, 6 hours lab)
1. Lambda expressions and functional interfaces (2 hours lecture, 1 hour lab)
  1. Introduction to lambda expressions
  2. Functional interfaces and their usage
  3. Method references and their applications
2. Java Generics and Type Inference (2 hours lecture, 2 hours lab)
  - Understanding generics and their benefits
  - Type inference and diamond operator
  - Bounded type parameters and wildcards
  - Generic methods and classes
3. Java Reflection API and Annotations (2 hours lecture, 1 hour lab)
  - Reflection API basics and use cases
  - Annotations and their applications
  - Runtime annotation processing
  - Dynamic class loading and object creation
4. Streams API and parallel processing (1 hour lecture, 1 hour lab)
  - Introduction to Streams API
  - Intermediate and terminal operations
  - Parallel processing with Streams
5. Java Debugging, Logging, and Testing (1 hour lecture, 1 hour lab)
  - Debugging techniques and tools
  - Logging frameworks (e.g., Log4j, SLF4J)
  - Introduction to unit testing with JUnit
  - Test-driven development (TDD) principles

Unit 2: User Interface Development (9 hours lecture, 6 hours lab)
- Introduction to Java UI Technologies (1 hour lecture)
  - Overview of JFC, Applet, AWT, and Swing
  - Limitations and alternatives
  - Differences between AWT and Swing
- Java Swing (3 hours lecture, 2 hours lab)
  - Swing components and containers
  - Layout managers and custom layouts
  - Swing event handling
  - Swing threading and concurrency
- JavaFX and FXML (4 hours lecture, 3 hours lab)
  - Introduction to JavaFX architecture
  - Creating user interfaces with FXML
  - Styling with CSS
  - JavaFX charts, graphs, 3D, and animations
  - Using Scene Builder for visual design
- Event Handling and UI Design Patterns (1 hour lecture, 1 hour lab)
  - Event-driven programming concepts
  - UI design patterns (e.g., MVC, MVP, MVVM)
  - Implementing design patterns in JavaFX

Unit 3: Data Persistence and Access (8 hours lecture, 5 hours lab)
- Database Design and JDBC (2 hours lecture, 1 hour lab)
  - Two-Tier and Three-Tier Database Design
  - JDBC basics and database connectivity
  - Connection pooling concepts and implementation
  - Prepared statements and result set handling
  - Transaction management with JDBC
- Object-Relational Mapping (ORM) with Hibernate (3 hours lecture, 2 hours lab)
  - Introduction to ORM and Hibernate
  - Mapping entities and relationships
  - Hibernate query language (HQL) and criteria API
  - Caching and performance optimization with Hibernate
- Java Persistence API (JPA) (2 hours lecture, 1 hour lab)
  - JPA concepts and entity lifecycle
  - Entity relationships and inheritance
  - JPA query language (JPQL) and native queries
  - JPA caching and performance tuning
- Query Optimization and Performance Tuning (1 hour lecture, 1 hour lab)
  - Optimization techniques for JDBC, Hibernate, and JPA
  - Identifying and resolving performance bottlenecks
  - Indexing and query plan analysis
  - Caching strategies and cache invalidation

Unit 4: Server-Side Development (9 hours lecture, 6 hours lab)
- Java Servlets and Filters (2 hours lecture, 2 hours lab)
  - Servlet lifecycle and API
  - Creating and configuring servlets
  - Implementing filters for request processing
  - Servlet security and authentication
- JavaServer Pages (JSP) (3 hours lecture, 2 hours lab)
  - JSP syntax and directives
  - Expression Language (EL) and JSTL
  - MVC pattern with JSP and servlets
  - JSP best practices and performance optimization
- Integration of Servlets and JSP (2 hours lecture, 1 hour lab)
  - Combining servlets and JSP for dynamic web pages
  - Handling form submissions and validations
  - Session management and state maintenance
- RESTful Web Services (2 hours lecture, 1 hour lab)
  - Introduction to REST principles and architecture
  - Designing RESTful APIs
  - Implementing RESTful endpoints with JAX-RS
  - Consuming RESTful services with Java clients

Unit 5: Modern Java Frameworks & Java for IoT (8 hours lecture, 5 hours lab)
- Spring Framework (Core, MVC, Security, Data) (4 hours lecture, 2 hours lab)
  - Spring Core concepts (DI, IoC, AOP, POJO)
  - Spring MVC for web application development
  - Spring Security for authentication and authorization
  - Spring Data for data access and persistence
- Spring Boot for Rapid Application Development (2 hours lecture, 1 hour lab)
  - Introduction to Spring Boot
  - Auto-configuration and starter dependencies
  - Creating RESTful APIs with Spring Boot
  - Spring Boot Actuator and monitoring
- Java for IoT (2 hours lecture, 2 hours lab)
  - Overview of IoT concepts and protocols
  - Interfacing with Arduino and NodeMCU using Java
  - Raspberry Pi programming with Pi4J library
  - IoT protocols (MQTT, CoAP) with Java
  - Security considerations for IoT applications