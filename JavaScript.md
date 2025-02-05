What is JavaScript?
1. JavaScript is the high level interpreted programming language which is used for the create the interactive and dynamic websites. 
2. It enables to create responsive web applications by adding functionalities like from validations, animations and many more.

What is datatype?
1. Datatype refers to the kind of which is holds by the variable.
2. Type of data in JS : 
	1. Primitive Data Type :
			String 
			Number 
			BigInt
			Boolean
			Undefind
			Null
			Symbol

What is variable?
1. Variable is nothing but container which is used for the store the value. And it also acts as a symbolic name of the values.
2. Variable of var type can also declare as a copy but let and const type can't be declare as a copy.

3. Variable Naming Rules
	- Must begin with a letter, underscore (`_`), or dollar sign (`$`).
	- Cannot start with a number.
	- Can contain letters, numbers, underscores, and dollar signs.
	- Cannot use reserved keywords like `if`, `else`, `var`, etc.

		let name = "John"; // String
		const age = 25;    // Number
		var isStudent = true; // Boolean
		console.log(name, age, isStudent); // Output: John 25 true

	Keywords for variable declaration :

		const : It is block scope variable declaration type which is used for the declare the variable but Which variable declare using the 'const' keyword that can't be change its initial value but we are change it with the help of Object.

		let : It is block scope variable declaration type which is used for the declare the variable.

		var : It a older way for the declare the variable and it has function scope variable.


Note : If we have get the output into the table format then we use the table method

		console.table([accId, accName, bankName])

		let a = 20
		let b = 10
		let c = 30

		PS C:\Users\srand\OneDrive\Desktop\JS> node variable
       ┌─────────┬───────────┐
       │ (index) │ Values    │
       ├─────────┼───────────┤
       │ 0       │ 20        │
       │ 1       │ 10        │
       │ 2       │ 30        │
       └─────────┴───────────┘

Note : If any variable can't be initialized with the any value then JS should be initialize with 'undefined' value

Note :  """  - triple cote, DocString

"use strict" - This treat all JS code as newer version


Datatype in JS
	Datatype can also refers to what type of value holds by the variable

Why cant run alert() method on console?
	Because of this is the method of the window object, which is always available in the browser.

Datatype in JS :

1. Number   Stores the all the type of number range : 2 power 53
2. BigInt    
3. null     This is object type initialize as a empty
4. string
5. boolean
6. undefined
7. object
8. symbol   It is mostly used for uniqueness

```Copy
console.log(typeof null)

O/P :
	object
```

What is constructer in JS?
	Constructor is a special method used to initialize the object created by a class. It is automatically called when  instance is created.

Ex,

```Copy
class Person{
	construcor(name,age){
		this.name = name
		this.age = age
	}

	greet(){
		console.log(`Hello, My nameis ${this.name} and I am ${this.age} years old`)
	}
}

O/P :
   Hello, My name is Shubham and I am 21 years old

```

Constructor overloading :
	
``` Copy
class Person{
constructor(name = "Unknown",age = 0)
	tihs.name = name
	this.age = age
}

const person1 = new Person('Shubh',21)
const person2 = new Person()

console.log(person1)
console.log(person2)

O/P  :
	Person{name : 'Unknow', age : 0}
	Person(name : 'Shubham', age = 21)

```