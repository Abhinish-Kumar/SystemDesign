
---

# Interface Segregation Principle (ISP)

**Definition:**
The Interface Segregation Principle states that no client should be forced to depend on methods it does not use. This principle aims to keep interfaces small and focused, ensuring that implementing classes only need to be concerned with the methods that are relevant to them.

**Key Points:**
1. **Clients should depend on the smallest set of interface features.**
2. **Interfaces should have the fewest methods and attributes necessary.**

**Problems with Violating ISP:**
1. **Client code will be bound to irrelevant methods.**
2. **Changes in one part of the code can cause ripple effects in other parts.**

**Analogy:**
Imagine a restaurant where employees have specific roles. If we have a `RestaurantEmployee` class with methods like `washDishes`, `serveCustomer`, and `cookFood`, and we create a `Waiter` class that inherits from `RestaurantEmployee`, the `Waiter` class will inherit all three methods. However, it's not the waiter's job to wash dishes or cook food. This makes the `Waiter` class unnecessarily complex and violates the ISP.

**Example in JavaScript:**

Let's consider a scenario where we have different types of workers in a restaurant.

### Without ISP:

```javascript
class RestaurantEmployee {
    washDishes() {
        console.log("Washing dishes");
    }

    serveCustomer() {
        console.log("Serving customer");
    }

    cookFood() {
        console.log("Cooking food");
    }
}

class Waiter extends RestaurantEmployee {
    // Inherits washDishes, serveCustomer, and cookFood
}

const waiter = new Waiter();
waiter.serveCustomer(); // Relevant
waiter.washDishes(); // Irrelevant
waiter.cookFood(); // Irrelevant
```

In this example, the `Waiter` class inherits methods that are not relevant to its role, violating the ISP.

### With ISP:

```javascript
// Define smaller, more specific interfaces
class DishWasher {
    washDishes() {
        console.log("Washing dishes");
    }
}

class Server {
    serveCustomer() {
        console.log("Serving customer");
    }
}

class Chef {
    cookFood() {
        console.log("Cooking food");
    }
}

// Implement only the relevant interface
class Waiter extends Server {
    // Inherits only serveCustomer
}

const waiter = new Waiter();
waiter.serveCustomer(); // Relevant
```

In this example, the `Waiter` class only inherits the `serveCustomer` method, adhering to the ISP.

**Summary:**
The Interface Segregation Principle helps in creating more maintainable and understandable code by ensuring that classes are not burdened with methods they do not need. By breaking down large interfaces into smaller, more specific ones, we can avoid unnecessary dependencies and make our code more modular and flexible.

---


(1) Interface Segregation Principle: Everything You Need to Know - Reflectoring. https://reflectoring.io/interface-segregation-principle/.
(2) Interface Segregation with Code Examples Explained- Stackify. https://stackify.com/interface-segregation-principle/.
(3) SOLID Principles Series: Embracing the Interface Segregation Principle .... https://dev.to/ruben_alapont/solid-principles-series-embracing-the-interface-segregation-principle-isp-in-typescript-59n6.
(4) Interface segregation principle - Wikipedia. https://en.wikipedia.org/wiki/Interface_segregation_principle.
