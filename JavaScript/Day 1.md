# Day 1

[Day 1 Resource](https://www.freecodecamp.org/news/var-let-and-const-whats-the-difference)

### Printing in JavaScript

```js
console.log(message);
```

### Variable Declaration

```js
var varVariable;
console.log(varVariable); // Prints undefined
---------------------------------------------
let letVariable;
console.log(letVariable); // Prints undefined
```

### Scope of variable

```js
var tester = "hey hi";
function func() {
	var hello = "hi";
}
console.log(hello); // Error - hello not declared
```

### Declaration

- var can be redeclared
- let cannot be redeclared
- const cannot be reassigned

## 'var' variable

### Problem with '__var__'

```js
var times = 4;
if (times > 3) {
	var greeter = "say Hello instead";
}
console.log(greeter); // Error
--------------------------------------------
var greeter = "hey hi";
var times = 4;
if (times > 3) {
	var greeter = "say Hello instead";
}
console.log(greeter); // "say Hello instead"
```

If a variable is not declared then if the variable is declared in the scope.  
Accessing it outside the scope will give an error.

But if a variable is declared beforehand, it will have updated value inside smaller scope


## 'let' variable

```js
let greeting = "say hi";
let times = 4;
if (times > 3) {
	let hello = "say hello instead";
	console.log(hello); // "say hello instead"
}
console.log(hello); // hello is not defined
```

- '__let__' variables can be updated but not redeclared

```js
let greeting = "say Hi";
if (true) {
	let greeting = "say Hello instead";
	console.log(greeting); // "say Hello instead"
}
console.log(greeting); // "say Hi"
```

## 'const' variable

- These cannot be redefined or redeclared

```js
const greeting = "Hi";
greeting = "Hello"; // Error
----------------------------------
const greeting = "Hi";
const greeting = "Hello"; // Error
```

- A const object cannot be updated. But the properties of the const object can be updated.

```js
const greeting = {
	message: "say hi",
	times: 4
}
greeting.message = "Hello"; // Changes message property of greeting
-------------------------------------------------------------------
greeting = {
	message: "Hello",
	times: 1
} // Error
```

## == and === in JavaScript

- '__==__' only checks if the values are same or not.
- '__===__' checks if the values are same or not and if the types of data compared are same or not.

```js
// Double equals
console.log(2 == "2"); // true
console.log(0 == ""); // true
console.log("A" == "A"); // true
console.log(null == undefined); // true
console.log([] == ""); // true
-----------------------------------------
// Triple equals
console.log(2 === "2"); // false
console.log(0 === ""); // false
console.log("A" === "A"); // true
console.log(null === undefined); // false
console.log([] === ""); // false
```

