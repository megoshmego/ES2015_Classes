Based on the transcript you've provided, the instructor is explaining the concept of methods within classes in JavaScript, with a specific focus on instance methods and the `this` keyword. They illustrate these concepts using a `Triangle` class and its methods.

Let's summarize the main points and provide code snippets to facilitate the learning process:

1. **Methods**: A method is a function as a property on an object. When added to classes, these methods are referred to as instance methods because they're associated with specific instances of the class. For example:

```javascript
class Triangle {
  constructor(a, b, c) {
    this.a = a;
    this.b = b;
    this.c = c;
  }

  display() {
    console.log(`Triangle sides: ${this.a}, ${this.b}, ${this.c}`);
  }
}
```
In this `Triangle` class, `display` is an instance method.

2. **The `this` keyword**: In instance methods, `this` refers to the specific instance the method is called on. So, if you have an instance `t1` of the Triangle class, `this` within `display()` would refer to `t1` when you call `t1.display()`.

3. **Calling methods from within a class**: You can define a method within a class that calls another method of the same class. However, you must use the `this` keyword to properly reference the other method. For example:

```javascript
class Triangle {
  // ...

  getArea() {
    const s = (this.a + this.b + this.c) / 2;
    return Math.sqrt(s * (s - this.a) * (s - this.b) * (s - this.c)); // Heron's formula
  }

  isBig() {
    return this.getArea() > 50;
  }
}
```
In the `Triangle` class, `isBig()` calls `this.getArea()` to calculate the area and then checks if it's greater than 50. Without `this`, `getArea` wouldn't be recognized because `this` provides the necessary context.

4. **Returning values from methods**: Besides performing actions, methods can also return values. For instance, the `getArea()` method calculates and returns the area of the triangle.

5. **Accepting arguments**: Instance methods can also accept arguments. Although the instructor doesn't provide an example, here's a modification to the `display` method that accepts a prefix argument:

```javascript
class Triangle {
  // ...

  display(prefix) {
    console.log(`${prefix} Triangle sides: ${this.a}, ${this.b}, ${this.c}`);
  }
}
```
Now, you can provide a string prefix when calling `display`, like `t1.display('My')`, which would output "My Triangle sides: a, b, c" (with `a`, `b`, and `c` replaced with the actual side lengths).