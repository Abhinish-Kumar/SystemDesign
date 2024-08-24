## Gang of Four (GoF)

 "Design Patterns: Elements of Reusable Object-Oriented Software"

Authored by Erich Gamma, Richard Helm, Ralph Johnson, and John Vlissides, this book was published in 1994.
The book introduces 23 classic design patterns, which are proven solutions to common software design problems. These patterns are categorized into three types: Creational, Structural, and Behavioral, each addressing different aspects of object-oriented design.

### Types of Design pattern

1. Creational Patterns.
2. Structural Patterns.
3. Behavioral Patterns.

| **Category**          | **Design Patterns**                                           |
|-----------------------|---------------------------------------------------------------|
| **Creational Patterns** | - Abstract Factory  <br> - Builder <br> - Factory Method <br> - Prototype <br> - Singleton |
| **Structural Patterns** | - Adapter <br> - Bridge <br> - Composite <br> - Decorator <br> - Facade <br> - Flyweight <br> - Proxy |
| **Behavioral Patterns** | - Chain of Responsibility <br> - Command <br> - Interpreter <br> - Iterator <br> - Mediator <br> - Memento <br> - Observer <br> - State <br> - Strategy <br> - Template Method <br> - Visitor |


### Is there any other type of design patterns other then oop design pattern ?

Yes, there are several other types of design patterns beyond Object-Oriented Programming (OOP) design patterns. These patterns are applicable in various programming paradigms and domains. Here are some examples:

1. Functional Design Patterns
2. Concurrency Patterns
3. Architectural Patterns
4. Behavioral Patterns (Non-OOP)
5. Data Patterns
6. Enterprise Integration Patterns
7. Security Patterns
8. User Interface Patterns

| **Category**                   | **Design Patterns**                                                                                   |
|--------------------------------|-------------------------------------------------------------------------------------------------------|
| **Functional Design Patterns** | - Higher-Order Functions: Functions that take other functions as arguments or return them.<br> - Currying: Breaking down a function that takes multiple arguments into a series of functions that each take a single argument.<br> - Memoization: Caching the results of expensive function calls to optimize performance. |
| **Concurrency Patterns**       | - Producer-Consumer: A pattern where one or more producers generate data that one or more consumers process.<br> - Future/Promise: A pattern for handling asynchronous operations that may return a result in the future.<br> - Observer: Manages asynchronous event streams, often in reactive programming. |
| **Architectural Patterns**     | - MVC (Model-View-Controller): Separates the application into three interconnected components.<br> - MVVM (Model-View-ViewModel): Separates the UI from business logic, often used in UI frameworks.<br> - Microservices: Structures an application as a collection of loosely coupled services. |
| **Behavioral Patterns (Non-OOP)** | - Pipeline: A series of processing stages where the output of one stage is the input to the next.<br> - Event Sourcing: Logs state changes as a series of events rather than overwriting the state. |
| **Data Patterns**              | - Data Access Object (DAO): Provides an abstract interface to a database or other persistence mechanism.<br> - Repository: Mediates between the domain and data mapping layers. |
| **Enterprise Integration Patterns** | - Message Broker: Handles message distribution, routing, and transformation in a distributed system.<br> - Event-Driven Architecture: Determines program execution flow based on events. |
| **Security Patterns**          | - Singleton: Ensures only one instance of a security-related object exists.<br> - Role-Based Access Control (RBAC): Restricts system access to authorized users based on their role. |
| **User Interface Patterns**    | - Model-View-Controller (MVC): Separates input logic, business logic, and interface in UI.<br> - Mediator: Manages communication between different UI components to decouple them. |



### What is the difference between system design and design pattern?

System Design and Design Patterns are both crucial concepts in software engineering, but they operate at different levels of abstraction and serve different purposes.

#### Key Differences

1. **Level of Abstraction**: System design is about the big picture and how the entire system will work as a cohesive unit, while design patterns are more about solving specific problems within that system.
2. **Purpose**: System design focuses on building a scalable, reliable, and maintainable system architecture, while design patterns provide solutions to specific design problems that arise during the implementation phase.
3. **Context**: System design is used during the initial stages of software development to plan the architecture, while design patterns are often applied during the coding phase to solve design challenges.


# Example: Designing an Online Bookstore

## System Design

### Objective
You are tasked with designing the architecture for an online bookstore that allows users to browse books, add them to a shopping cart, place orders, and make payments.

### Components
- **Frontend**: A web interface where users can search for books, view details, and manage their shopping cart.
- **Backend Services**:
  - **User Service**: Manages user accounts, authentication, and profiles.
  - **Book Service**: Manages the catalog of books, including searching, filtering, and categorizing.
  - **Order Service**: Handles order processing, order history, and order status tracking.
  - **Payment Service**: Integrates with payment gateways to process payments securely.
- **Database**: Stores user data, book catalog, orders, and payment information.
- **Caching Layer**: Caches frequently accessed data like book details to improve performance.
- **Load Balancer**: Distributes incoming traffic across multiple backend servers to ensure scalability and reliability.
- **Microservices Architecture**: You decide to use microservices to enable independent development and scaling of different services (e.g., User Service, Book Service).

### Considerations
- **Scalability**: Ensuring the system can handle a large number of users and transactions.
- **Fault Tolerance**: Designing the system to be resilient to server failures, ensuring high availability.
- **Security**: Protecting user data, especially during payment processing.

## Design Patterns

### Objective
Within the Book Service, you need to implement specific functionalities such as ensuring that only one instance of a shopping cart exists per user session and allowing the system to notify users when a book in their cart becomes available at a discount.

### Patterns Used
- **Singleton Pattern**:
  - **Problem**: You need to ensure that only one instance of the shopping cart exists per user session.
  - **Solution**: Implement the Singleton pattern to ensure that every user session only ever interacts with a single instance of their shopping cart object.
- **Observer Pattern**:
  - **Problem**: You want to notify users when a book in their cart goes on sale.
  - **Solution**: Implement the Observer pattern where the shopping cart (subject) notifies users (observers) of any changes in the price of books they’ve added.

## Summary of Differences
- **System Design**: In this example, the system design involves planning the overall architecture of the online bookstore, including components like services, databases, and caching strategies. The focus is on how different parts of the system interact, ensuring scalability, fault tolerance, and security.
  
- **Design Patterns**: Design patterns are applied within the individual components, such as using the Singleton pattern in the shopping cart service to manage user sessions or the Observer pattern to handle notifications. These patterns address specific design challenges at a more granular level within the system.











