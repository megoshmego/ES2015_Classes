Sure, I can help to break down this script. The tutorial you've been listening to is an introduction to classes in JavaScript, particularly focusing on the constructor method.

Here's a simplified breakdown of the key points:

1. **Defining a Class**: In JavaScript, a class is defined using the `class` keyword followed by the name of the class. The class acts as a blueprint or template from which objects (instances) are created.

```javascript
class Triangle {
  //...
}
```

2. **Constructor Method**: Within a class, you can define a constructor method which is a special method for creating and initializing objects created within a class. When a new object is created from a class using the `new` keyword, the constructor method is automatically called. 

```javascript
class Triangle {
  constructor(a, b, c) {
    this.a = a;
    this.b = b;
    this.c = c;
  }
}
```

3. **Instance Properties**: Inside the constructor, you can assign properties to the object being created using the `this` keyword. In the example above, `a`, `b`, and `c` are properties of each Triangle object created, and they are initialized with the values passed in when the object is created.

4. **Creating Instances**: You can create a new object (or instance) from a class using the `new` keyword. The arguments you pass in when creating the object will be used as arguments for the constructor method.

```javascript
let t1 = new Triangle(3, 4, 5);
```

5. **Method Definition**: Classes can also contain methods. These methods can be used on any object created from the class.

```javascript
class Triangle {
  constructor(a, b, c) {
    this.a = a;
    this.b = b;
    this.c = c;
  }

  display() {
    console.log(`Triangle with sides of ${this.a}, ${this.b} and ${this.c}`);
  }
}
```

6. **Data Validation**: It's common to include some data validation within the constructor. In this case, the instructor is ensuring that the sides of the triangle are positive numbers. If the data is invalid, the constructor throws an error which stops execution and prevents the creation of an invalid object.

```javascript
class Triangle {
  constructor(a, b, c) {
    if (!Number.isFinite(a) || a <= 0
        || !Number.isFinite(b) || b <= 0
        || !Number.isFinite(c) || c <= 0) {
      throw new Error('Sides must be positive numbers.');
    }

    this.a = a;
    this.b = b;
    this.c = c;
  }

  display() {
    console.log(`Triangle with sides of ${this.a}, ${this.b} and ${this.c}`);
  }
}
```

These are the basics of using classes in JavaScript. As you continue learning, you'll encounter more advanced topics such as inheritance, static methods, and private fields.