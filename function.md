1. Function Declaration

function greet(name) {
  return "Hello " + name;
}

greet("Alex");

Key Points
	•	Hoisted (can be used before declaration)
	•	Named function


2. Function Expression

const greet = function(name) {
  return "Hello " + name;
};

Key Points
	•	Stored in a variable
	•	Not hoisted like function declarations


3. Arrow Functions (ES6)

const add = (a, b) => a + b;

Multi-line:

const multiply = (a, b) => {
  return a * b;
};

Key Points
	•	Shorter syntax
	•	No own this



4. Callback Functions

A function passed as an argument to another function.

function processUser(name, callback) {
  console.log("Processing " + name);
  callback();
}

function done() {
  console.log("Finished!");
}

processUser("Alex", done);

Example with async:

setTimeout(() => {
  console.log("Runs later");
}, 1000);


5. Higher-Order Functions

A function that:
	•	Takes another function as argument
	•	Returns a function

function operate(a, b, fn) {
  return fn(a, b);
}

const add = (x, y) => x + y;

operate(3, 4, add);

Common examples:
	•	map()
	•	filter()
	•	reduce()
	•	forEach()


6. Closures

A function remembering variables from its outer scope.

function counter() {
  let count = 0;

  return function () {
    count++;
    return count;
  };
}

const increment = counter();

increment(); // 1
increment(); // 2

Used for:
	•	Private variables
	•	Data persistence
	•	Function factories


7. Default Parameters

function greet(name = "Guest") {
  return "Hello " + name;
}

greet(); // Hello Guest


8. Rest Parameters

Allows unlimited arguments.

function sum(...numbers) {
  return numbers.reduce((a, b) => a + b);
}

sum(1,2,3,4);



9. Immediately Invoked Function Expression (IIFE)

Runs immediately after creation.

(function () {
  console.log("Runs immediately");
})();

Arrow version:

(() => {
  console.log("IIFE with arrow");
})();



10. Pure Functions

A function that:
	•	Always returns same output for same input
	•	Has no side effects

function add(a, b) {
  return a + b;
}



11. Array Higher-Order Methods

map()

const nums = [1,2,3];
const doubled = nums.map(n => n * 2);

filter()

const nums = [1,2,3,4];
const even = nums.filter(n => n % 2 === 0);

reduce()

const nums = [1,2,3];

const total = nums.reduce((sum, n) => sum + n, 0);



Quick Interview Summary

Concept	Key Idea
Function Declaration	Hoisted function
Function Expression	Function stored in variable
Arrow Function	Short syntax
Callback	Function passed to another
Closure	Function remembers outer variables
Higher-Order	Function using other functions
IIFE	Runs immediately
Pure Function	No side effects


Most Asked Interview Concept

Example combining closure + higher-order function

function multiplier(x) {
  return function(y) {
    return x * y;
  };
}

const double = multiplier(2);

double(5); // 10

	•	Higher-order function ✅
	•	Closure ✅
