# Day 2

[Day 2 Resource](https://www.educative.io)

```js
var trueValue = true;
var falseValue = new Boolean(false);
console.log(typeof(trueValue)); // boolean
console.log(typeof(falseValue)); // object
```

'__new__' creates a new object.

```js
var falseValue = new Boolean(false);
console.log(falseValue);
// [Boolean: false]
------------------------------------
console.log(falseValue.valueof());
// false
```

```js
var num1 = new Number(2e-3); // 0.002
var num2 = new Number(10e4); // 10000
--------------------------------------------
var str1 = "String-1"; // string
var str1 = new String("String-1"); // object
var str1 = new String(1234); // object
--------------------------------------------
var sym1 = new Symbol(); // Symbol object
var sym2 = new Symbol(); // Symbol object
```

__null__ is an object.  
__undefined__ is undefined. We do not know if its a primitive datatype or an object.

Strings can be defined with __'...'__ (Single Quotes), __"..."__ (Double Quotes), __\`...\`__ (Backticks)

### Backtick Usage

```js
// Traditional Approach
'This is a ' + variable + ' and this is ' + anotherVariable
// Using Backticks
`This is a ${variable} and this is ${anotherVariable}`
```

### Objects

- Number
- String
- Boolean
- Symbol
- Date
- Array

## Arrays

```js
var arr1 = [1, 2, 3, 4];
var arr2 = (arr1);
arr2[0] = 5;
console.log(arr1, arr2);
// arr1 and arr2 is identical and will be updated together
```

```js
// Creating copy of an array
var arr1 = [1, 2, 3, 4];
var arr2 = arr1.slice(); // Shallow Copy
var arr3 = [...arr1]; // Doesn’t safely copy multi-dimensional arrays.
var arr4 = [];
arr4 = arr4.concat(arr1); // Concatenates the emptry array arr4 with arr1
```

__Shallow Copy__ - The copy stores the reference of the objects being copied.  
__Deep Copy__ - The copy stores the values of the objects being copied.

```js
var arr1 = [[1, 2], [3, 4]];
var arr2; // Shallow copied to arr1
arr2[0][0] = 5;
console.log(arr1, arr2);
// [ [ 5, 2 ], [ 3, 4 ] ] [ [ 5, 2 ], [ 3, 4 ] ]
------------------------------------------------
var arr3; // Deep copied to arr1
arr3[0][0] = 5;
console.log(arr1, arr3);
// [ [ 1, 2 ], [ 3, 4 ] ] [ [ 5, 2 ], [ 3, 4 ] ]
```

### Threading

__Multi-Threaded__ - Any two lines which are independent from other code lines can be divided into multiple threads so that the code can run faster.  
__Single-Threaded__ - Any two lines which are independent from other code lines cannot be divinded into other threads and will only execute after the code before it has finished executing.

## Functions

### Syntax:
```js
funciton functionName(<arguments>) {
	statements;
}
```
Normal function. Can be called later in the code.

### Anonymous Function Syntax:
```js
let functionVariable = funciton (<arguments>) {
	<statements>;
}
```
Does not have names. Can only be used once.

### Arrow Function Syntax:
```js
let arrowVariable = (<arguments>) => {
	<statements>;
}
```
Short-hand way of writing an anonymous function.

### Function given as argument to another function

```js
function printHello() {
	console.log("Hello");
}
function foo(func) {
	console.log("Inside foo Function");
	func(); // Invoke the function passed as argument
	console.log("Execution Done");
}
foo(printHello);
// Inside foo Function
// Hello
// Execution Done
-----------------------------------------------------
function foo(func) {
	console.log("Inside foo Function");
	func(); // Invoke the function passed as argument
	console.log("Execution Done");
}
foo(() => console.log("Hello"));
// Inside foo Function
// Hello
// Execution Done
-----------------------------------------------------
// A function is calling other function which
// returns the result of the function called inside
useState(() => createTodos());
```

### Function as the Returned Object

```js
const foo = () => {
	var add = (num1, num2) => {
		console.log(num1 + num2);
	}
	return add; // Returns function
}
var func = foo();
// Recieves the add function which was returned
func(1, 2); // 3
-----------------------------------------------------------
const foo = () => (num1, num2) => console.log(num1 + num2);
foo()(1, 2); // 3
```

## forEach method

__forEach method__ is used to iterate an array in loops.

### Syntax:

```js
array.forEach(<function>); // takes function as argument
```

Example -

```js
var array = [10, 20, 30, 40, 50];
function printArrayDetails(value, index, array) {
	console.log(`Value: ${value} Index: ${index} Array: ${array}`);
}
for (var i = 0; i < array.length; i++) {
	printArrayDetails(array[i], i, array);
}
-------------------------------------------------------------------
var array = [10, 20, 30, 40, 50];
array.forEach((value, index, array) => {
	console.log(`Value: ${value} Index: ${index} Array: ${array}`);
});
// Value: 10 Index: 0 Array: [ 10, 20, 30, 40, 50 ]
// Value: 20 Index: 1 Array: [ 10, 20, 30, 40, 50 ]
// Value: 30 Index: 2 Array: [ 10, 20, 30, 40, 50 ]
// Value: 40 Index: 3 Array: [ 10, 20, 30, 40, 50 ]
// Value: 50 Index: 4 Array: [ 10, 20, 30, 40, 50 ]
```

## filter method

__filter method__ filters elements in an array that pass a certain test and then returns it in a new array.  
The original array is left unchanged.

### Syntax:

```js
arr.filter(<function>);
```

Example -

```js
var arrOriginal = [1, 2, 3, 4, 5, 6];
var arrFiltered = arrOriginal.filter(element => element % 2 == 0);
console.log(arrOriginal); // Prints original array [ 1, 2, 3, 4, 5, 6 ]
console.log(arrFiltered); // Prints filtered array [ 2, 4, 6 ]
```

## find method

__find method__ returns the value of element which satisfies the condition given as the argument.

### Syntax:

```js
array.find(<function>);
```

Example -

```js
var array = [1, 2, 3, 4, 5, 6];
var foundElement = array.find(element => element % 2 == 0);
console.log(foundElement); // Prints element 2
```

## Map method

__map method__ applies a function to each element of the array and creates a new array of the return values.

### Syntax:

```js
arr.map(<function>);
```

Example -

```js
var arrOriginal = [10, 20, 30, 40, 50];
var arrayMapped = arrOriginal.map(element => element * 2);
console.log(arrOriginal); // Prints original array [ 10, 20, 30, 40, 50 ]
console.log(arrayMapped); // Prints mapped array [ 20, 40, 60, 80, 100 ]
```

## Reduce method

__reduce method__ gives a single final value using the previous reduced value with the current value from the original array.

### Syntax:

```js
arr.reduce(<function>);
```

Example -

```js
var arrOriginal = [10, 20, 30, 40, 50];
var arrReduced = arrOriginal.reduce((prev, curr) => prev + curr);
console.log(arrReduced); // Prints 150
```

## Map and Reduce method Example

```js
// Initialise the array of elements
var arr = ['Hello', 1, true, NaN, 'Bye'];
// Map to 0 and 1
var countArr = arr.map(ele => typeof ele === 'string' ? 1 : 0);
// Reduce for Sum
var sum = countArr.reduce((prev, curr) => prev + curr);
console.log('Array:', arr); // [ 'Hello', 1, true, NaN, 'Bye' ]
console.log('Array from map:', countArr); // [ 1, 0, 0, 0, 1 ]
console.log('Number of Strings:', sum); // 2
```

```js
// Initialise a 2D array
var arr = [
	[1, 2, 3, 4],
	[1, 2],
	[1, 2, 3, 4, 5, 6],
	[]
]
// Maps and Reduces in same call
var sum = arr.map(element => {
	return element.length;
}).reduce((prev, curr) => {
	return prev + curr;
});
console.log(arr);
// [ [ 1, 2, 3, 4 ], [ 1, 2 ], [ 1, 2, 3, 4, 5, 6 ], [] ]
console.log(sum); // 12
```