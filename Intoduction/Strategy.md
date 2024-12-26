Design Pattern in Java, emphasizing its importance in low-level design. It contrasts traditional inheritance with the strategy pattern, showcasing how it allows for flexible and reusable code

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
