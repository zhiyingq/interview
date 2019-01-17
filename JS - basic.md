# JS - basic
#面试相关

### Scope:
In JavaScript there are two types of scope: 
1. Local scope 
2. Global scope (under window object)
JavaScript has function scope: Each function creates a new scope. Scope determines the accessibility (visibility) of these variables. Variable defined inside a function are not accessible (visible) from outside the function.

The current context of execution. The context in which values and expressions are "visible," or can be referenced. If a variable or other expression is not "in the current scope," then it is unavailable for use. Scopes can also be layered in a hierarchy, so that _child scopes have access to parent scopes, but not vice versa_.

map
```javascript
var arr = [1,2,3,4];
var newArray = arr.map(function(v) {
  return v * 2;
});
console.log(newArray);
```

### This
In JavaScript, this pointer is another difficult topic, to tackle this topic, we just have to understand the following rules. **This always points to the object that calls current function.**

Object-based this:
```js
var person = {
  name: "Zhiying",
  speak: function() {
    console.log("This is " + this.name);
  }
}
person.speak();
```

Prototype-based this:
```js
function Person() {
  this.name = "Zhiying";
  this.speak = function() {
    console.log("This is " + this.name);
  }
}

var zhiying = new Person();
var zspeak = zhiying.speak;
zspeak();
```

### Apply, bind, call

Use .bind() when you want that function to later be called with a certain context, useful in events. Use .call() or .apply() when you want to invoke the function immediately, and modify the context.

Call/apply call the function immediately, whereas bind returns a function that, when later executed, will have the correct context set for calling the original function. This way you can maintain context in async callbacks and events.

```js
function Person(name) {
  this.name = name;
  this.speak = function(message1, message2) {
    console.log("This is " + this.name+" and I want to say" + message1 + " and "+message2);
  }
}

var zhiying = new Person("Zhiying");
var jingyi = new Person("Jingyi");
zhiying.speak.call(jingyi, "hehe", "xixi");
zhiying.speak.apply(jingyi, ["hehe", "xixi"]);
var j = zhiying.speak.bind(jingyi);
j("hehe", "xixi");
```


### Closure
A closure is a function defined within another scope(function) that has access to all the variables within the outer scope.

```js
function outer(num) {
  var message = "num is: ";
  var inner = function() {
    console.log(message + num);
  }
  return inner;
}
var result = outer(1);
result();
var result2 = outer(2);
result2();

```

Application of closure:
Set the font-size
```js
/*
An IIFE (Immediately Invoked Function Expression) is a JavaScript function that runs as soon as it is defined. The first is the anonymous function with lexical scope enclosed within the Grouping Operator (). This prevents accessing variables within the IIFE idiom as well as polluting the global scope. The second part creates the immediately executing function expression () through which the JavaScript engine will directly interpret the function

advantage: The function becomes a function expression which is immediately executed. The variable within the expression can not be accessed from outside it.

*/
(function() {
  
})();

function makeSizer(size) {
  return function() {
    document.body.style.fontSize = size + 'px';
  };
}

var size12 = makeSizer(12);
var size14 = makeSizer(14);
var size16 = makeSizer(16);
```


### Hoisting
Conceptually, for example, a strict definition of hoisting suggests that variable and function declarations are physically moved to the top of your code, but this is not in fact what happens. **Instead, the variable and function declarations are put into memory during the compile phase, but stay exactly where you typed them in your code**.

One of the advantages of JavaScript putting function declarations into memory before it executes any code segment is that it allows you to use a function before you declare it in your code. For example:
```js
catName("Chloe");

function catName(name) {
  console.log("My cat's name is " + name);
}
/*
The result of the code above is: "My cat's name is Chloe"
*/
```

**JavaScript only hoists declarations, not initializations**. If a variable is declared and initialized after using it, the value will be undefined. 
```js
console.log(num)  //报错
```

```js
console.log(num);
var num = 6;
// undefined, only DECLARATION is hoisted, INITIALIZATION is not hoisted
```


### let and var
var and let are both used for function declaration in javascript but the difference between them is that var is **function scoped** and let is **block scoped**.
It can be said that a variable declared with var is defined throughout the program as compared to let.

### NodeJS
What is Node.js?
1. Node.js is an open source server environment
2. Node.js is free
3. Node.js runs on various platforms (Windows, Linux, Unix, Mac OS X, etc.)
4. Node.js uses JavaScript on the server



































