This is an overview of JavaScript objects and some of the properties, methods, and behaviours associated with them. Below I will elaborate and provide snippets to learn the material:

1. **Object Literal Syntax**: This is a way to create objects in JavaScript, using curly braces `{}`.

    ```javascript
    let myObject = {};  // Creates an empty object
    ```

2. **Plain Old JavaScript Object (POJO)**: This term refers to a JavaScript object that doesn't inherit from other objects, and isn't extended or altered in any way.

3. **Adding properties**: Properties can be added to an object after it's been created, using the `.` or `[]` notation.

    ```javascript
    let obj = {};
    let color = 'teal';
    
    obj.color = '#007F7F';  // Using the dot notation
    obj[color] = '#007F7F';  // Using the square bracket notation
    
    console.log(obj);  // Output: {color: "#007F7F", teal: "#007F7F"}
    ```

    The difference between the two notations is that `.` takes the literal name provided as the key, while `[]` evaluates the expression inside before using it as the key. In the above example, `obj.color` added a key "color", while `obj[color]` evaluated `color` to its value "teal" and added a key "teal".

4. **Object.keys()**: This method returns an array of a given object's own enumerable property names, iterated in the order that the properties were defined.

    ```javascript
    console.log(Object.keys(obj));  // Output: ["color", "teal"]
    ```

5. **Object.values()**: This method returns an array of a given object's own enumerable property values, in the same order as the keys returned by `Object.keys()`.

    ```javascript
    console.log(Object.values(obj));  // Output: ["#007F7F", "#007F7F"]
    ```

6. **Object.entries()**: This method returns an array of a given object's own enumerable string-keyed property [key, value] pairs.

    ```javascript
    console.log(Object.entries(obj));  // Output: [["color", "#007F7F"], ["teal", "#007F7F"]]
    ```

    We can also use this method to iterate through the object.

    ```javascript
    for (let [key, value] of Object.entries(obj)) {
        console.log(`${key}: ${value}`);
    }
    ```

7. **Undefined properties**: If you try to access a property that doesn't exist on an object, JavaScript will return `undefined`.

    ```javascript
    console.log(obj.red);  // Output: undefined
    ```

8. **String keys**: All keys in a JavaScript object are converted to strings. Even if you don't explicitly use a string as the key, JavaScript will convert it to a string internally.

    ```javascript
    obj[-11] = 'negative 11';
    
    console.log(obj['-11']);  // Output: "negative 11"
    console.log(obj[-11]);  // Output: "negative 11"
    ```

I hope this breakdown helps! The next topic is about methods on objects.