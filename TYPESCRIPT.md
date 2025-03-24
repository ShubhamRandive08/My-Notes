
What is TYPESCRIPT ? <br>
- TS is a programming language which is developed by Microsoft.<br>
- TS is a programming language that builds on JS by adding static types.<br>

Why use TYPESCRIPT ?<br>
- Type Safety - Catches error before running the code<br>
- Better code suggestions<br>
- Works with JS<br>
- Scalability<br>
Ex ,<br>

``` JS
function add ( a, b ){
	 return a + n
}
```

```TS
function add ( a : number , b : number ) : number {
	return a + b;
}
```

Different between JS ad TS<br>

| Feature                    | JavaScript (JS)                                           | TypeScript (TS)                                                                 |
| -------------------------- | --------------------------------------------------------- | ------------------------------------------------------------------------------- |
| **Type System**            | Dynamically typed (types are not enforced)                | Statically typed (types are enforced at compile time)                           |
| **Compilation**            | Interpreted directly by the browser or engine             | Compiled to JavaScript before running                                           |
| **Syntax**                 | Flexible, no type annotations                             | Requires type annotations for variables, functions, etc.                        |
| **Tooling Support**        | Limited type checking, less support in IDEs               | Advanced tooling, autocompletion, and error checking in IDEs                    |
| **Error Checking**         | Errors are only detected at runtime                       | Errors are detected at compile time, before execution                           |
| **Learning Curve**         | Easier to learn, as it’s just JavaScript                  | Requires understanding of types and compilation process                         |
| **Support for OOP**        | Basic object-oriented features                            | Full support for classes, interfaces, inheritance, etc.                         |
| **Code Readability**       | Code can be more prone to errors due to lack of types     | More readable and maintainable due to explicit types                            |
| **Backward Compatibility** | Fully compatible with all browsers and environments       | Needs to be compiled to JavaScript, but can be compatible with existing JS code |
| **Tooling/Frameworks**     | Popular for web development, with large community support | Growing adoption, especially in large projects or teams                         |
| **Development Speed**      | Faster development for small projects                     | Slower initial setup but can be more scalable in large projects                 |
| **Code Refactoring**       | More difficult due to lack of type enforcement            | Easier to refactor thanks to type checking and interfaces                       |

Ex,<br>

```JS
let mess = 'Hello'
mess = 123 // NO ERROR BUT MIGHT COUSE BUGS LATER
```

```TS
let mess : string = 'Hello'
mess = 123 // Error, Type numberis not assigible to type string
```

- TS is superset of the JS, in TS we should be declare the type of the variable <br>

Ex,<br>
```JS
let num = 10
num = 'Shubham' // NO error here
```

```TS
let num : number = 10
```

- Here the ``number`` is type of the `variable` <br>

- Avoid bugs in development, for that we use `TYPESCRIPT` <br>
- Increase development speed<br>

##### TS code can't run in production, we need to convert in JS format<br>

#### *Installation of TS -*<br>
- Go on terminal <br>
- Fire command <br>

```terminal
npm install -g typescript
```

#### *To check installed or not<br>*

```Terminal
tsc --help
```

#### How to declare type of variable<br>
- First declare the variable, then mark the colon ( : ), then type the main type<br>

Ex, <br>

```TS
let num : number = 20
```

Ex,<br>

```TS
function getTotal ( nums ){
	return nums.reduce ( (acc, item) => {
		return acc + item
	}, 0 ) 
}

console.log( getTotal ( [3,2,1] );
```

#### Build in types in TS<br>

  TS provides several builds-in types to safety and better code management<br>
Premitive Type<br>

| TYPE      | Example                               |
| --------- | ------------------------------------- |
| number    | `let age : number = 25`               |
| string    | `let name : string = 'Shubham'`       |
| boolean   | `let isActive : boolean = true`       |
| bigint    | `let largNumber : bigint = 45123698`  |
| undefined | `let uniquId : undefined = undefined` |
| null      | `let emptyValue : null = null`        |
| symbol    | `let uniqueId : symbol = symbol`      |

2. Object Type :<br>
	Used to define objects with properties<br>

```TS
let person : { name : string , age : number }
{
	name : 'John',
	age : 30
}
```

3. Array types<br>

```TS
let nums : number[] = [1,2,3,4,5]
let str : string[] = ['Shubham', 'Ram']
```

4. Tuple type<br>

```TS
let user : [ string, number ] = [ 'alice', 25 ]
```

5. Enum type <br>

```TS
enum Role {
	Admin,
	User,
	Guest
}

let userRole : Role = Role.Admin

console.log(userRolt) // O/P : 0
```

6. Any type <br>

```TS
let randomValue : any = 'Hello'
randomValue = 23
randomValue = true
```

7. void type <br>
	- Used to functions that do not return a value<br>

```TS
fucntion logMessage() : void {
	console.log("This function returns nothing")
}
```

8. Union type<br>

	Allow to holds multiple types<br>

```TS
let value : string | number
value = 'Hello'
value = 34
```

9. Custom types using type, interface and class<br>

Using type<br>

```TS
type User : { name : string , age : number}

let newUser : User = { name : 'Shubham' , age : 25}
```


Using interface<br>

```TS
interface Car {
	brand : string,
	model : string
}

let myCar : Car = { brand : 'Toyota', model : 'Corolla'}
```

Using class<br>

```TS
class Person {
	name : string;
	age : number;

	constructor(name : string , number : number) {
		this.name = name
		this.age = number
	}
	greet() : void {
		console.log(`Hello, My name is ${this.name}`)
	}
}

let user : Person = new Person('Alice', 25)
user.greet()
```

```
O/P : Hello, My name is Alice
```


#### NOTE : In TS, `console.log()` can be used for the print the any value or any statement<br>


##### **If we want to create the our custom type that time we can use 'type' keyword and also make first latter of custom type is Capital.<br>**
Ex,

```TS
type User = {
	name : string;
	age : number;
}

let user : User {
	name : 'Shubham',
	age : 21
}
```

**If we want to create the type with optional value simply we can add ? ( Question Mark ) before the colon { : }**<br>
Ex,

```TS
type User = {
	name ?: string;
	age ?: number;
}
```

<br>
When we add the ? ( Question Mark ) here then into that there are two possible types such as **provided type** or **undefined**
<br>
#### Function is TS<Br>
```TS
function fun_name ( parameters ) : funcion_type {
	.........................
	.........................    This is the body of the function
	.........................
}
```

Ex,
```TS
function login(){
	console.log('Hello')
}

login()
```

Ex,
Question : Create the function to perform the addition of the two numbers.

```TS
let n1 : number = 40;
let n2 : number = 20;

function add(n1,n2) : number {
	return n1 + n2;
}

console.log('The additon of the two numbers : ' + add(n1,n2))
```

```OUTPUT
This additon of the two numbers : 60
```
<br>
Ex, 
Create the function with the custom data type / aliases type<br>
```TS
type User = {
	name : string;
	age : number;
	address : string;
	gender : string;
}

function userData (user : User) : User {
	return user;
}

console.log(userData({ name : 'Shubham Randive' , age : 21, address : 'Chakreshwarawadi' , gender : 'male'}))
```

```OUTPUT
{
	name : 'Shubham Randive',
	age : 21,
	address : 'Chakreshwarawadi',
	gender : 'male'
}
```
<br><br>
| - This symbol is used for the provide two or more than two type s for the variable<br>Ex,
```TS
let str : string | number

str = 'Shubham'
str = 2334
```
<br>
#### Interfaces :

- Interface is like the shape of the any object.
- They support optional ( ? ) properties,  read-only properties, function signature and index signatures.
- Interfaces can extend other interface for reusability.
- Classes can implement interfaces to enforce structure.
- The time of the creation of the interface, the First letter of the name of the interface must be `Capital` because of the reason it is the rule for that.
- For creation of the interface we also use the `interface` keyword
- In TS, interfaces are used to define the structure of the object, ensuring type safety and consistency. They act as contracts that specify what properties and methods an object should have.
<br>
Ex,
```TS
interface interface_name {
	...................................
	................................... Block of the code
	...................................
}
```

```TS
interface Transaction {
	payerAccountNo : number;
	payeeAccountNo : number;
}
```

**We also use the interface as a type of the any other variable or method**
<br>
Ex,
```TS
interface Transaction {
	payerAccountNo : number;
	payeeAccountNo : number;
}

interface BankAccout {
	accoutNumber : number;
	accoutHolder : string;
	balence : number;
	isActive : boolern;
	transaction : Transaction;
}
```
<br>
Interface with functions<br>
```TS
interface MathOperation {
	(a : number , b : number) : number ;
}

const add : MathOpration = (x,y) => x + y;

console.log(add(5,10))
```


 Extending interfaces


```TS
  interface Person {
    name : string;
    age : number;
}

interface Employee extends Person{
    empId : number
}

const emp : Employee = {
    empId : 30,
    name : 'Shubham',
    age : 32
}

console.log(emp)
```

OUTPUT :

```
{ empId: 30, name: 'Shubham', age: 32 }
```

Interfaces with Classes

```TS
interface Animal {
	name : string;
	makeSound() : void
}

class Dog implements Animal {
	name : string;

	constructor(name : string){
		this.name = name;
	}
makeSound() {
	console.log("Woof! Woof!")
}
}

const dog = new Dog("Buddy");
dog.makeSound(); // O/P : Woof! Woof
```

Using read-only properties 

```TS
interface Car {
	readonly model : string;
	year : number
}

const myCar : Car = { 
	model : 'Tesla',
	year : 2024,
}

// myCar.model = 'BMW' // Error : Cannot assign to model because it is a read only property
```

Intersection Types vs Extending Interfaces

You can also combine multiple interfaces using intersection types ( & )

```TS
interface A {
	propA : string;
}

interface B {
	propB : number;
}

type Combine : A & B ;

const example : Combine = {
	propA : "Hellow",
	proB : 44,
}

console.log(example)
```

#### Extends interface

We also use the `extends` keyword for the use the feature of the previous interface and implements it into the next interface.

```TS
interface Book {
	name : string;
	price : number;
}

interface EBook extends Book {
	// name : string;
	// price : number;
	fileSize : number;
	format : string;
}

interface AudioBook extends EBook {
	// name : string;
	// price : number;
	// fileSize : number;
	// format : string;
	duration: number;
}

const book : AudioBook = {
	name : 'Atomic habits',
	price : 1200,
	fileSize : 300,
	format : 'pdf',
	duration : 4,
}
```


##### Merging interface :
- If you provide same name to different interface then TypeScript can relise it is same in merging both as a same or one.

```TS
interface Book {
	name : string;
	price : number;
}

interface Boook {
	size : number
}

const book : Book = {
	name : 'Yayati',
	price : 1200,
	size : 300
}

console.log(book)
```

##### NOTE : In between `type` and `interface`, the interface is also good for use because of resone, merging can support only the interface.  It doesn't support to type. 

#####  And if i want to create the primitive type then we should be use the `type` method because of interface can't able to make primitive data type.

Ex, 
```TS
	type SanitizedString = string;
```


