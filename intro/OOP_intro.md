In this excerpt, the lecturer is discussing the roadmap of topics for Object-Oriented Programming (OOP) in JavaScript. Here is a summary of those topics and some illustrative snippets:

1. **Objects in JavaScript:**

JavaScript objects are containers for named values called properties or methods. An object property is essentially a variable attached to the object. An object method is a function that is a property of an object.

```javascript
let person = {
    firstName: "John",
    lastName: "Doe",
    age: 50,
    eyeColor: "blue",
    fullName: function() {
      return this.firstName + " " + this.lastName;
    }
};
```

2. **Defining Classes in JavaScript:**

Classes are a template for creating objects. They encapsulate data with code to manipulate that data. Classes in JavaScript are introduced in ECMAScript 6 and are syntactical sugar over JavaScript's existing prototype-based inheritance.

```javascript
class Rectangle {
    constructor(height, width) {
        this.height = height;
        this.width = width;
    }
    area() {
        return this.height * this.width;
    }
}
let myRectangle = new Rectangle(5, 7);
console.log(myRectangle.area());  // outputs: 35
```

3. **Creating Object Instances:**

We can use the `new` keyword to create instances of a class. Each instance will have its own copy of the data, and is able to call the methods defined by the class.

```javascript
let rectangle2 = new Rectangle(8, 9);
console.log(rectangle2.area());  // outputs: 72
```

4. **Constructor Functions:**

Constructor functions are the old way to define classes in JavaScript before the class keyword was introduced.

```javascript
function Circle(radius) {
    this.radius = radius;
    this.area = function() {
        return Math.PI * this.radius * this.radius;
    };
}
let myCircle = new Circle(5);
console.log(myCircle.area());  // outputs: 78.53981633974483
```

5. **Inheritance:**

In JavaScript, we can use `extends` keyword to create a class which is a child of another class. The child class inherits all properties and methods from the parent class.

```javascript
class Square extends Rectangle {
    constructor(sideLength) {
        super(sideLength, sideLength);
    }
}
let mySquare = new Square(5);
console.log(mySquare.area());  // outputs: 25
```

6. **Encapsulation:**

Encapsulation is the principle of bundling the data, and the methods that operate on that data, into a single unit. This can be accomplished in JavaScript using classes.

7. **Polymorphism:**

Polymorphism is the ability of an object to take on many forms. In JavaScript, all objects inherit from `Object.prototype` and can be instances of more than one class.

```javascript
console.log(mySquare instanceof Square);  // outputs: true
console.log(mySquare instanceof Rectangle);  // outputs: true
console.log(mySquare instanceof Object);  // outputs: true
```

This overview provides a brief introduction to each topic. Each of these topics is broad and has a lot more to explore. The code snippets provided are designed to give a basic understanding and a starting point for further study.