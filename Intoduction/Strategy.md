Design Pattern in Java, emphasizing its importance in low-level design. It contrasts traditional inheritance with the strategy pattern, showcasing how it allows for flexible and reusable code


## WHat is Strategy Design pattern?
The Strategy Design Pattern is a behavioral design pattern that enables an object to choose a specific algorithm from a family of algorithms at runtime. This pattern is particularly useful for encapsulating various algorithms within separate classes, allowing for interchangeable behaviors without altering the clients that use them.

<img src="https://media.geeksforgeeks.org/wp-content/uploads/20240207172937/StrategyDesignPatternExampleSet2.webp" min-width="100%" max-width="500px"/>

## How does strategy pattern improves the resusability?
The Strategy Pattern improves code reusability in several key ways:

1. Encapsulation of Algorithms: By encapsulating different algorithms or behaviors within separate strategy classes, the Strategy Pattern allows you to reuse these classes in different contexts without duplicating code. Each strategy can be developed, tested, and maintained independently.

2. Interchangeable Strategies: Since strategies are interchangeable, you can easily swap one implementation for another without changing the code that uses them. This means you can reuse the same context class with different strategies, promoting flexibility and reducing redundancy.

3. Single Responsibility Principle: Each strategy class has a single responsibility, focusing solely on its specific algorithm. This separation makes it easier to understand, modify, and reuse individual strategies without affecting others.

4. Dynamic Behavior: The ability to change strategies at runtime allows for more adaptable and reusable code. For example, a single context can work with multiple strategies based on user input or other conditions, reducing the need for multiple context classes.

5. Reduced Code Duplication: By defining common interfaces and using concrete strategy classes, you avoid duplicating similar code across different parts of your application. This leads to a cleaner codebase that is easier to maintain and extend.

Example:
In a payment processing system, you might have multiple payment strategies (e.g., credit card, PayPal, bank transfer). Instead of writing separate code for each payment method, you can create a single context class that uses different strategy classes for each payment type. This way, you can easily add new payment methods in the future without modifying existing code.

```js
// Strategy Interface  
class DriveStrategy {  
    drive() {  
        throw new Error("This method must be overridden!");  
    }  
}  

// Concrete Strategies  
class DriveWithGasoline extends DriveStrategy {  
    drive() {  
        console.log("Driving with gasoline engine.");  
    }  
}  

class DriveWithElectric extends DriveStrategy {  
    drive() {  
        console.log("Driving with electric engine.");  
    }  
}  

class DriveWithHybrid extends DriveStrategy {  
    drive() {  
        console.log("Driving with hybrid engine.");  
    }  
}  

// Context  
class Vehicle {  
    constructor(driveStrategy) {  
        this.driveStrategy = driveStrategy;  
    }  

    setDriveStrategy(driveStrategy) {  
        this.driveStrategy = driveStrategy;  
    }  

    drive() {  
        this.driveStrategy.drive();  
    }  
}  

// Client code  
const vehicle = new Vehicle(new DriveWithGasoline());  
vehicle.drive(); // Output: Driving with gasoline engine.  

// Change to electric drive  
vehicle.setDriveStrategy(new DriveWithElectric());  
vehicle.drive(); // Output: Driving with electric engine.  

// Change to hybrid drive  
vehicle.setDriveStrategy(new DriveWithHybrid());  
vehicle.drive(); // Output: Driving with hybrid engine.  
```


## Key Terminology:

| **Component**          | **Description**                                                   | **Example in Context**                      |
|-------------------------|-------------------------------------------------------------------|---------------------------------------------|
| **Strategy Interface**  | Defines the interface for all strategies.                        | `DriveStrategy` defines the `drive()` method. |
| **Concrete Strategies** | Implements the strategy interface with specific algorithms.      | `DriveWithGasoline`, `DriveWithElectric`, `DriveWithHybrid` |
| **Context**             | Maintains a reference to a strategy and delegates its behavior.  | `Vehicle` class uses a `DriveStrategy`.     |
| **Client**              | Configures the context and selects the desired strategy.         | Code creating a `Vehicle` and setting a strategy. |


