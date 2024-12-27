## Observer Design Pattern (notify system)

run a function with data of subscriber.

```js
// Observer class
class Newsletter {
    constructor() {
        this.subscribers = []; // List of observers
    }

    // Add an observer
    subscribe(observer) {
        this.subscribers.push(observer);
    }

    // Remove an observer
    unsubscribe(observer) {
        this.subscribers = this.subscribers.filter((sub) => sub !== observer);
    }

    // Notify all observers
    notify(message) {
        this.subscribers.forEach((subscriber) => subscriber(message));
    }
}

// Usage
const newsletter = new Newsletter();

// Subscribers (Observers)
const user1 = (message) => console.log(`User1 received: ${message}`);
const user2 = (message) => console.log(`User2 received: ${message}`);

// Subscribe users
newsletter.subscribe(user1);
newsletter.subscribe(user2);

// Notify subscribers
newsletter.notify("New edition of the newsletter is available!");

// Unsubscribe a user
newsletter.unsubscribe(user1);

// Notify again
newsletter.notify("Second edition is out!");

```


### Diagram

<img src="images/UML.png" />
















