From your text, it seems like you are discussing how constructors and prototypes are used in JavaScript, and how methods can be added to these prototypes. To summarize:

A **constructor** in JavaScript is a special method that is used to create and initialize an object within a class.

The **prototype** is a property of a function in JavaScript that can be used to define methods and properties that will be shared among all instances created with that function.

In the video you're watching, the person is explaining how JavaScript's `new` keyword can be used to create new instances of a constructor function, and how the prototype of that function can be modified to add new methods.

Here's a breakdown of what they're doing, and some code snippets to help illustrate each point:

1. **Defining a constructor function:**

    This is a function that is used to create new objects. Here's an example of a constructor function for a "triangle" object:

    ```javascript
    function Triangle(a, b) {
      this.a = a;
      this.b = b;
    }
    ```

    The `this` keyword here refers to the new object that is being created. 

2. **Creating new instances:**

    The `new` keyword is used to create new instances of a constructor function. Here's how you can create a new "triangle":

    ```javascript
    let triangleOne = new Triangle(3, 4);
    ```

    This will create a new Triangle object, where `a` is 3 and `b` is 4.

3. **Adding methods to the prototype:**

    Methods can be added to the prototype of a constructor function, which means that all instances of that function will share those methods. Here's how to add a `getArea` method to the Triangle constructor function:

    ```javascript
    Triangle.prototype.getArea = function() {
      return 0.5 * this.a * this.b;
    }
    ```

    This `getArea` method can now be called on any Triangle object:

    ```javascript
    console.log(triangleOne.getArea());  // Outputs: 6
    ```

4. **Accessing the Prototype:**

    Every object in JavaScript has a `__proto__` property that points to the object's prototype. The prototype contains all the methods that are shared among all instances of that constructor function. For example:

    ```javascript
    console.log(triangleOne.__proto__);  // Outputs the prototype of the Triangle function
    ```

5. **Caution on Modifying Built-in Prototypes:**

    While it's possible to modify built-in prototypes in JavaScript (like Array.prototype or String.prototype), it's generally considered bad practice because it can lead to unexpected behavior. There's one exception to this, which is when using "polyfills". A polyfill is code that implements a feature on web browsers that do not support the feature. Most often, it refers to a JavaScript library that implements HTML5 web standard features, especially in older browsers.

In the next video, it seems like they will cover JavaScript's `class` keyword, which is a more recent addition to the language that provides a simpler and more intuitive way to create objects and deal with inheritance.