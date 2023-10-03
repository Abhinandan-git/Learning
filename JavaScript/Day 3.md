# Day 3

[Day 3 Resource](https://www.freecodecamp.org/news/object-oriented-javascript-for-beginners/)

## Object - Oriented Programming (OOPS)

- Prototype
- Constructor Function
- Classes

## Prototype

```js
let vehicle = {
    wheel : 4,
    brand : "BMW",
    color : "white"
};
let car = {
    __proto__ : vehicle,
    seat : 5
};
console.log(vehicle, vehicle.__proto__)
console.log(car, car.__proto__)
// { wheel: 4, brand: 'BMW', color: 'white' } [Object: null prototype] {}
// { seat: 5 } { wheel: 4, brand: 'BMW', color: 'white' }
Object.setPrototypeOf(destination, source);
```

## Constructor Function

```js
function FunctionName(param1, param2, ...) {
    this.param1 = param1;
    this.param2 = param2;
    .
    .
}
let constructedVariable = new FunctionName(param1, param2, ...);
```

Example -

```js
function Student(name, age, branch, mobile) {
    this.name = name;
    this.age = age;
    this.branch = branch;
    this.mobile = mobile;
}
let student_one = new Student("Abhinandan", 19, "CSE", 1234567890);
console.log(student_one.name);  // Abhinandan
console.log(student_one.age);  // 19
console.log(student_one.branch);  // CSE
console.log(student_one.mobile);  // 1234567890
```

"this" in the constructor function is replaced with the variable name when values are assigned to the variable's properties.  
Arrow functions cannot be used as Constructor functions. These are treated as normal functions.

### Encapsulation

Methods inside the Constructor function cannot be called as a stand-alone.  
These need the object called beforehand to work.  
Example - Getter / Setter functions -

```js
function Student(name, age) {
	this.name = name;
	this.age = age;
	// Setter functions
	this.setAge = age => this.age = age,
	this.setName = name => this.name = name,
	// Getter functions
	this.getName = () => this.name;
	this.getAge = () => this.age;
}
student_one = new Student("Abhi", 20);
console.log(student_one.name); // Abhi
student_one.setName("Abhi Jain");
console.log(student_one.name); // Abhi Jain
```

### Static Variable

A variable which has same value over the entire class. It can be declared as a static variable instead of instance variable.

```js
function Student(param1, param2) {
	this.instanceVariale = param1;
}
Student.staticVariable = value;
student_one = new Student(1, 2);
```

### Using Classes

```js
class ClassName {
	constructor(param1, param2) {
		this.param1 = param1;
		this.param2 = param2;
		this.setParam1 = param1 => {
			this.param1 = param1;
		}
		this.getParam2 = () => this.param2;
	}
	functionName() {
		console.log(this.param1 + " " + this.param2);	
	}
}
class_one = new ClassName("param1", "param2");
functionName(); // Error as the function is encapsulated inside the class
class_one.functionName();
```