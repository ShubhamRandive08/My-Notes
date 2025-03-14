
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
