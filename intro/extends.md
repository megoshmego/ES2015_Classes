In this transcript, they explain the concepts of inheritance, classes, and the `super` keyword in JavaScript. 

Inheritance is a principle in object-oriented programming where you create a new class that's based on an existing class. In this context, a class is a blueprint for creating objects that encapsulate data and behaviors. The `super` keyword is used to call the parent class with the `this` value of the new object being constructed.

Here's a summary of the steps to achieve this:

1. Create a parent class, `Triangle`, with basic properties and methods:

```javascript
class Triangle {
    constructor(a, b, c) {
        if (typeof a !== "number" || typeof b !== "number" || typeof c !== "number" || a <= 0 || b <= 0 || c <= 0) {
            throw new Error("Invalid sides");
        }

        this.a = a;
        this.b = b;
        this.c = c;
    }

    display() {
        return `Triangle with sides of ${this.a}, ${this.b}, and ${this.c}`;
    }

    // Add other methods for Triangle here
}
```

2. Create a child class, `RightTriangle`, that extends `Triangle`, adds additional validation in its constructor, and overwrites some parent methods:

```javascript
class RightTriangle extends Triangle {
    constructor(a, b, c) {
        if (a * a + b * b !== c * c) {
            throw new Error("Invalid C side");
        }

        super(a, b, c);
        this.hypot = c;
    }

    display() {
        return 'Right ' + super.display();
    }

    // Add other methods specific for RightTriangle here
}
```

In the `RightTriangle` class, we first validate whether the given sides form a right triangle (i.e., if a² + b² = c²). If not, an error is thrown. Then, we call `super(a, b, c)` to run the constructor of `Triangle`. This helps to avoid duplication and keeps the code cleaner. The `super.display()` method is used to call the `display` method of the parent `Triangle` class.

3. Instantiate the classes and test the methods:

```javascript
const myTriangle = new Triangle(3, 4, 5);
console.log(myTriangle.display());

const myRightTriangle = new RightTriangle(3, 4, 5);
console.log(myRightTriangle.display());
```

Remember that if a method is not found on the child class (`RightTriangle`), it will look for it on the parent class (`Triangle`). This is one of the key benefits of inheritance - code reusability. The child class inherits all the properties and methods from the parent class but also has the flexibility to add or override them.