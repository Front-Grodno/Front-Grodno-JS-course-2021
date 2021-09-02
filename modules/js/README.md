# JavaScript
##### In the current module we should get familiar with the JavaScript language
## Topics:
1. Fundamentals of JavaScript language
1. Advanced working with JavaScript functions
1. Objects, Classes, Inheritance, Prototypes in JavaScript
1. Asynchronous JavaScript
1. Events in JavaScript
1. Handling Errors, Debugging, Profiling in JavaScript
----------
### Topic 1: Fundamentals of JavaScript language
##### Materials:
1. [Variables](https://javascript.info/variables)
1. [Data types](https://javascript.info/types)
1. [Type Conversions](https://javascript.info/type-conversions)
1. [Basic operators, maths](https://javascript.info/operators)
1. [Conditional operators](https://javascript.info/ifelse), [Logical operators](https://javascript.info/logical-operators)
1. [Loops: while and for](https://javascript.info/while-for)
1. [Functions](https://javascript.info/function-basics), [Functions Expressions](https://javascript.info/function-expressions)
##### Tasks:
1. Declare two variables: admin and name. Assign the value "John" to name. Copy the value from name to admin. Show the value of admin using alert (must output “John”).
1. Write an if condition to check that __age__ is NOT between 14 and 90 inclusively.
1. Rewrite the code changing the __for__ loop to __while__ without altering its behavior (the output should stay same).
    ```javascript
    for (let i = 0; i < 3; i++) {
      alert( `number ${i}!` );
    }
    ```
1. Write a loop which prompts for a number greater than __100__. If the visitor enters another number – ask them to input again.
1. Write a function __min(a,b)__ which returns the least of two numbers a and b:
    ```javascript
    min(2, 5) == 2
    min(3, -1) == -1
    min(1, 1) == 1
    ```
1. Rewrite the function using __'?'__ and __'||'__.
    ```javascript
    function checkAge(age) {
        if (age > 18) {
            return true;
        } else {
            return confirm('Did parents allow you?');
        }
    }
    ```
The loop must ask for a number until either the visitor enters a number greater than 100 or cancels the input/enters an empty line.

Here we can assume that the visitor only inputs numbers. There’s no need to implement a special handling for a non-numeric input in this task.
Create two variants: the first one using NOT !, the second one – without it.
----------
### Topic 2: Advanced working with JavaScript functions
##### Materials:
1. [Advanced working with functions](https://javascript.info/advanced-functions)
1. Scope ([Link 1](https://www.w3schools.com/js/js_scope.asp), [Link 2](https://developer.mozilla.org/en-US/docs/Glossary/Scope))
1. Hoisting ([Link 1](https://www.w3schools.com/js/js_hoisting.asp), [Link 2](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting))
1. Closures ([Link 1](https://www.w3schools.com/js/js_function_closures.asp), [Link 2](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures))
1. [Context](https://javascript.info/bind)
1. [this](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)
##### Tasks:
1. Create a function __runningAverage()__ that returns a callable function object:
    ```javascript
    // Example how it should work:
    runningAverage(10); //Outputs 10.0
    runningAverage(11); //Outputs 10.5
    runningAverage(12); //Outputs 11
    ```
1. Write a __sum()__ function which will work properly when invoked using syntax below:
    ```javascript
    sum(2,3); // Outputs 5
    sum(2)(3); // Outputs 5
    sum(1)(2)(3)(4); // Outputs 10
    ```
1. Create a function __NamedOne()__ which takes first & last names as parameters and returns an object with *firstName*, *lastName* and *fullName*. If *.firstName* or *.lastName* are changed, then *.fullName* should also be changed. If *.fullName* is changed, then *.firstName* and *.lastName* should also be changed.
__Note:__ "input format" to *.fullName* will be __firstName + space + lastName__. If given *fullName* isn't valid then no property is changed.
    ```javascript
    //Examples:
    var	namedOne = new NamedOne("Naomi","Wang");
    namedOne.firstName = "John"
    namedOne.lastName = "Doe"
    //...then...
    namedOne.fullName // -> "John Doe"
    // -- And:
    namedOne.fullName = "Bill Smith"
    //...then...
    namedOne.firstName // -> "Bill"
    namedOne.lastName // -> "Smith"
    // -- But:
    namedOne.fullName = "Tom" // -> no: lastName missing
    namedOne.fullName = "TomDonnovan" // -> no: no space between first & last names
    namedOne.fullName // -> "Bill Smith" (unchanged)
    ```
----------
### Topic 3: Objects, Classes, Inheritance, Prototypes in JavaScript:
##### Materials:
1. [Object](https://javascript.info/object-basics)
1. [Class](https://javascript.info/classes)
1. [Prototypes](https://javascript.info/prototypes)
1. [Constructor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/constructor)
1. ['new' operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new)
1. [Inheritance](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Inheritance)
1. [Inheritance and the prototype chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)
##### Tasks:
1. Create a __Vector__ object that supports addition, subtraction, dot products, and norms. So, for example. If you try to add, subtract, or dot two vectors with different lengths, you must throw an error. 
__Also provide:__ a *toString* method, so that using the vectors from above, *a.toString()	===	'(1,2,3)'* an equals method, to check that two vectors that have the same components are equal.
    ```javascript
    var a = new Vector([1, 2, 3]);
    var b = new Vector([3, 4, 5]);
    var c = new Vector([5, 6, 7, 8]);
    a.add(b); // should return a new Vector([4, 6, 8])
    a.subtract(b); // should return a new Vector([-2, -2, -2])
    a.dot(b); // should return 1*3 + 2*4 + 3*5 = 26
    a.norm(); // should return sqrt(1^2 + 2^2 + 3^2) = sqrt(14)
    a.add(c); // throws an error
    ```
1. Write a __myNew__ function that replicates all the behavior of the new operator. This function should take one function parameter (the constructor), plus an unknown number of additional parameters of any type (arguments for the constructor). When invoked, __myNew__ should do everything new does and return the same object new would evaluate to, as specified below:
    ```javascript
    var john = myNew(Person, 'John', 30); // should work the same as:
    var john = new Person('John', 30);

    //Note: use the code below for your task:
    function Person(name, age) {
        this.name = name;
    	this.age = age;
    }
    Person.prototype.introduce = function(){
        return 'My name is ' + this.name + ' and I am ' + this.age;
    };
    var john = new Person('John', 30);
    var jack = new Person('Jack', 40);
    console.log(john.introduce()); //My name is John and I am 30
    console.log(jack.introduce()); //My name is Jack and I am 40
    ```
----------
### Topic 4: Asynchronous JavaScript
##### Materials:
1. [Asynchronous JS](https://javascript.info/async)
1. [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
1. [Using Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)
1. [async](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
##### Tasks:
 1. Write your own __MyPromise__ class with syncThen method.
    ```javascript
    //Example:
    let promise = new MyPromise((resolve) => {
        console.log(1);
        resolve();
    }).synchThen(()	=> {
        console.log(2);
    }).then(() => {
        console.log(3);
    })
    console.log(4);
    //1, 2, 4, 3
    ```
1.	Write __ReversePromise__ class so that ‘then’ functions are calling from the end to the start
    ```javascript
    //Example:
    let promise = new ReversePromise((resolve) => {
        console.log(1);
        resolve();
    })
    .then(() => console.log(2))
    .then(() => console.log(3))
    .then(() => console.log(4))
    //1, 4, 3, 2
    ````
----------
### Topic 5: Events in JavaScript
##### Materials:
1. [Introduction to Events](https://javascript.info/events)
1. [Event](https://developer.mozilla.org/en-US/docs/Web/API/Event)
##### Tasks:
1. Create a table 100x100. Compare performance in adding listener to each cell click and event delegation.
1. Apply drag&drop functionality to each cell.
----------
### Topic 6: Handling Errors, Debugging, Profiling in JavaScript
##### Materials:
1. [Error handling](https://javascript.info/error-handling)
1. [JavaScript Errors](https://www.w3schools.com/js/js_errors.asp)
1. [JavaScript Debugging](https://www.w3schools.com/js/js_debugging.asp)
##### Tasks:
1. Create your custom error and trigger it.
1. Choose 3 sites and analyze it using DevTools console:
    - Do they have memory leaks?
    - What functions are taking more time for execution?
    - What time does it take for rendering first meaningful page?
----------
## Additional materials
1. [javascript.info](https://javascript.info/)
1. [exploringjs.com](https://exploringjs.com/impatient-js/toc.html)
1. [stateofjs.com](https://stateofjs.com/)
1. [JS Core](http://dmitrysoshnikov.com/ecmascript/ru-javascript-the-core/)
1. [V8](https://mrale.ph/v8/resources.html)
