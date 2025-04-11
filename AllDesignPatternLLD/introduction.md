
**🎓 Khan Sir’s Node.js Design Patterns Class (Creational, Structural, Behavioral) 🎓**  

*(Doston, aaj hum seekhenge **Design Patterns** ko Node.js mein, bilkul zero se! Sab students attention rakho!)*  

---

## **🚩 Class Shuru!**  

### **Student:** Khan Sir, **Design Patterns** kyun padhna hai?  
**Khan Sir:** Beta, jaise **"Ghar banane ka blueprint"** hota hai, waise hi **code ko structured banane ka blueprint** hota hai!  
- **Benefits:**  
  - **Reusable Code:** Baar-baar same logic nahi likhna padta.  
  - **Scalable:** Aage jakke change karna easy ho jata hai.  
  - **Clean Code:** Sab samajh mein aata hai, debugging easy hai!  

*(Chalo, ab **teen prakar ke patterns** samajhte hain!)*  

---

# **1️⃣ Creational Patterns – "Object Kaise Banega?"**  
*(Jaise **"Ghar ka naksha"** banane se pehle decide karna hota hai ki kamra kaise banega!)*  

### **Student:** Khan Sir, **Factory Pattern** kya hai?  
**Khan Sir:** Beta, maan lo tumhare paas ek **"Pizza Factory"** hai:  
```javascript
class PizzaFactory {
  createPizza(type) {
    switch (type) {
      case "veg": return new VegPizza();
      case "nonveg": return new NonVegPizza();
      default: throw new Error("Invalid pizza!");
    }
  }
}
```
- **Use Case:** Multiple objects ko **ek common interface** se banana.  

### **Student:** Aur **Singleton Pattern**?  
**Khan Sir:** Jaise **"Ek School ka Principal"** sirf ek hi ho sakta hai!  
```javascript
class Principal {
  constructor() {
    if (!Principal.instance) {
      Principal.instance = this;
    }
    return Principal.instance;
  }
}
const principal1 = new Principal();
const principal2 = new Principal();
console.log(principal1 === principal2); // true (Sirf 1 instance!)
```
- **Use Case:** Database connection, Logger, Config settings.  

---

# **2️⃣ Structural Patterns – "Objects Kaise Judenge?"**  
*(Jaise **"Lego blocks"** jodkar kuch naya banana!)*  

### **Student:** Khan Sir, **Adapter Pattern** ka matlab?  
**Khan Sir:** Beta, jaise **"Mobile Charger"** jo 220V ko 5V mein convert karta hai!  
```javascript
class OldAPI {
  request() { return "Data in XML"; }
}

class Adapter {
  constructor(oldAPI) {
    this.oldAPI = oldAPI;
  }
  request() {
    const data = this.oldAPI.request();
    return `${data} → Converted to JSON`;
  }
}
```
- **Use Case:** Incompatible systems ko connect karna.  

### **Student:** **Decorator Pattern**?  
**Khan Sir:** Jaise **"Samosa + Extra Chutney"** dena!  
```javascript
class Samosa {
  cost() { return 10; }
}

class ExtraChutney {
  constructor(samosa) {
    this.samosa = samosa;
  }
  cost() { return this.samosa.cost() + 5; }
}
const masalaSamosa = new ExtraChutney(new Samosa());
console.log(masalaSamosa.cost()); // 15
```
- **Use Case:** Existing objects ko **modify karna** without changing original class.  

---

# **3️⃣ Behavioral Patterns – "Objects Kaise Baat Karenge?"**  
*(Jaise **"YouTube Subscription"** – jab video upload hota hai, sabko pata chalta hai!)*  

### **Student:** **Observer Pattern** kaise kaam karta hai?  
**Khan Sir:** Jaise **"Khan Sir ka YouTube Channel"**!  
```javascript
class YouTubeChannel {
  constructor() {
    this.subscribers = [];
  }
  subscribe(user) {
    this.subscribers.push(user);
  }
  notify() {
    this.subscribers.forEach(sub => sub.update());
  }
}

class User {
  update() { console.log("New video uploaded! 📢"); }
}

const khanSir = new YouTubeChannel();
const student1 = new User();
khanSir.subscribe(student1);
khanSir.notify(); // "New video uploaded! 📢"
```
- **Use Case:** Event handling, Notifications.  

### **Student:** **Strategy Pattern**?  
**Khan Sir:** Jaise **"Exam mein Short Trick vs Long Method"**!  
```javascript
class ExamSolver {
  constructor(strategy) {
    this.strategy = strategy;
  }
  solve() { this.strategy.execute(); }
}

class ShortTrick {
  execute() { console.log("Solved in 2 steps!"); }
}
class LongMethod {
  execute() { console.log("Solved in 10 steps!"); }
}

const solver = new ExamSolver(new ShortTrick());
solver.solve(); // "Solved in 2 steps!"
```
- **Use Case:** Different algorithms ko dynamically use karna.  

---

## **🏆 Khan Sir’s Final Gyan:**  
| Pattern Type | Real-Life Example | Node.js Use Case |  
|--------------|------------------|------------------|  
| **Creational** | Pizza Factory | Database Models, Logger |  
| **Structural** | Lego Blocks | API Adapters, Middleware |  
| **Behavioral** | YouTube Notifications | Event Handling, Payment Gateways |  

**"Beta, Design Patterns seekh lo, life mein kabhi code fatne ka darr nahi hoga!"** 😎  

*(Agar samajh aaya ho toh share karo, warna phir se padhna padega! 😂🚀)*
