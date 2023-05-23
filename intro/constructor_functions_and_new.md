The instructor in this video is explaining the concept of constructors in object-oriented programming, specifically within JavaScript classes. Here's a script to reflect the tutorial:

```javascript
class Triangle {
    // Class constructor
    constructor(a, b, c) {
        if (!Number.isFinite(a) || a <= 0 || 
            !Number.isFinite(b) || b <= 0 || 
            !Number.isFinite(c) || c <= 0) {
            throw new Error("Sides must be positive numbers.");
        }
        
        this.a = a;
        this.b = b;
        this.c = c;
    }

    // Class methods
    greet() {
        console.log("Hello, I am a triangle.");
    }

    display() {
        console.log(`Triangle with sides of ${this.a}, ${this.b}, and ${this.c}`);
    }
}

// Example usage
try {
    const t1 = new Triangle(5, 6, 7);
    t1.display();  // Triangle with sides of 5, 6, and 7

    const t2 = new Triangle(9, 20, 50);
    t2.display();  // Triangle with sides of 9, 20, and 50

    const t3 = new Triangle(-3, 4, 5);  // Throws an error
    t3.display();
} catch(e) {
    console.log(e.message);
}
```

This script provides a `Triangle` class in JavaScript, which models a triangle with sides `a`, `b`, and `c`. In the constructor, it validates that the inputs are finite numbers and greater than zero, throwing an error otherwise. It also includes two methods: `greet`, which simply logs a greeting, and `display`, which logs a message including the lengths of the triangle's sides.

Remember, in JavaScript, `this` is a special keyword that refers to the instance of the object being created by the class. The `constructor` is a special method used to create and initialize an object created with a class. It runs when an object is instantiated with the `new` keyword, and it allows the class to accept parameters.

When creating new instances of the `Triangle` class, you need to use `try-catch` block to handle possible errors thrown by the constructor.