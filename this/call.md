It seems the instructor is introducing some important methods that allow you to control the context of `this` in JavaScript: `call()` and `bind()`. 

The `call()` function allows you to call a function with a given `this` value and arguments provided individually. The instructor uses `call()` to execute a function in the context of different objects.

Here's a simplified breakdown of the concepts:

**Example 1: Usage of `call()`**

```javascript
let cat = {
  name: 'Blue',
  breed: 'Scottish Fold',
  dance: function(style) {
    console.log(`Meow, I am a ${this.breed} and I like to ${style}`);
  }
};

cat.dance('salsa'); // Output: Meow, I am a Scottish Fold and I like to salsa

let dog = {
  name: 'Elton',
  breed: 'Black lab'
};

cat.dance.call(dog, 'jitterbug'); // Output: Meow, I am a Black lab and I like to jitterbug
```

In this example, we have a `cat` object with a `dance` function. Normally, when we call `cat.dance('salsa')`, it executes with `this` as the `cat` object. However, if we want to change the context and make `this` the `dog` object, we can use `call()`: `cat.dance.call(dog, 'jitterbug')`.

**Example 2: Usage of `call()` with multiple arguments**

```javascript
let cat = {
  name: 'Blue',
  breed: 'Scottish Fold',
  play: function(...toys) {
    for (let toy of toys) {
      console.log(`${this.name} plays with ${toy}`);
    }
  }
};

let dog = {
  name: 'Elton',
  breed: 'Black lab'
};

cat.play.call(dog, 'bone', 'my cat'); 
// Output: Elton plays with bone
// Output: Elton plays with my cat
```

In this second example, the `play` function in the `cat` object takes a rest parameter `...toys`. This lets us pass in any number of toys when we call the function. When we call `cat.play.call(dog, 'bone', 'my cat')`, it's as if we're running `dog.play('bone', 'my cat')`.

Lastly, it's important to note that the `call()` function doesn't alter the function permanently. It only changes the context of `this` for that particular function call.

The instructor also mentions the `bind()` function, which is similar to `call()` but instead of immediately invoking the function, it returns a new function with the context of `this` bound to the object we pass in. They say they'll discuss this method in more detail later on.