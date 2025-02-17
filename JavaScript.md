* This all code is on My GitHub Profile [GITHUB](https://github.com/ShubhamRandive08)  URL FOR NOTES REPOS - [URL](https://github.com/ShubhamRandive08/My-Notes.git)*

What is JavaScript?
1. JavaScript is the high level interpreted programming language which is used for the create the interactive and dynamic websites. 
2. It enables to create responsive web applications by adding functionalities like from validations, animations and many more.
3. It is extended version like TS ( TypeScript ) is also used for the Automation Test with using [Playwright](Playwright.md)  automation tool

What is datatype?
4. Datatype refers to the kind of which is holds by the variable.
5. Type of data in JS : 
	1. Primitive Data Type :
			String 
			Number 
			BigInt
			Boolean
			Undefind
			Null
			Symbol

What is variable?
6. Variable is nothing but container which is used for the store the value. And it also acts as a symbolic name of the values.
7. Variable of var type can also declare as a copy but let and const type can't be declare as a copy.

8. Variable Naming Rules
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

9. Number   Stores the all the type of number range : 2 power 53
10. BigInt    
11. null     This is object type initialize as a empty
12. string
13. boolean
14. undefined
15. object
16. symbol   It is mostly used for uniqueness

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

##### Class And Objects :
- For interview point of view classes and object is must important topic.

##### Objects And Prototypes :
- A JavaScript object is an entity having state and behavior ( Properties [Variable] and method [Function] )
- JS objects have a special property called prototype. We can set prototype using --proto--
- An **object** is a collection of key-value pairs, where the keys are strings (or Symbols) and the values can be any data type, including functions.

- Object is the blueprint of the class

#### **Creating Objects**

Objects can be created in multiple ways:
     ` let person = { name : "Alice", age : 25, greet : function (){ console.log("Hello, " + this.name); } };`

Using the `new Object()` Constructor : 
    `let obj = new Object();obj.name = "Bob";`

Using a Constructor Function :
     `function Person(name, age) {
          `this.name = name;`
         `this.age = age;`
        `}`

        `let p1 = new Person("Charlie", 30);`
        `console.log(p1.name); // Output: Charlie

Using class (ES6) :
`class Person {`
  `constructor(name, age) {`
    `this.name = name;`
    `this.age = age;`
  `}`
`}`

`let p2 = new Person("David", 40);`
`console.log(p2.name); // Output: David`

##### Prototype :
- Every JavaScript object has an internal property called `[[Prototype]]`, which refers to another object from which it can inherit properties.

```function Animal(name) {
  this.name = name;
}

// Adding method to prototype
Animal.prototype.speak = function () {
  console.log(this.name + " makes a sound");
};

let dog = new Animal("Dog");
dog.speak(); // Output: Dog makes a sound

console.log(dog.__proto__ === Animal.prototype); // true

```

- Objects in JavaScript store data as key-value pairs.
- Prototypes allow objects to inherit properties and methods from other objects.
- The prototype chain is used to look up properties and methods when they are not found directly on an object.
- The `__proto__` property references an object's prototype, while functions have a `prototype` property used for inheritance.

```Copy
	const student = {
		fullName : "Shubham Balavant Randive",
		marks : 91.80,
		printMarks : function () {
			 console.log("Marks : ", this.marks);
		},
	}
```


- Object can also ends with the qama. ( , )

![](/Image/01.png)


Prototype is always a `Object` which holds various values like,

In JS, the type of can be object.
Ex,
     ![](/Image/02.png)

##### Methods of declare the function in an objects
```Copy
// Method No. 1
	const employee = {
		calcTax1() {
			console.log("Tax Rate is 5%")
		},

// Methd No. 2
		calcTax2 : function() {
			console.log("Tax Rate is 10%");
		}
	}
```

Note : We can also define the protype of object manually,
Ex, 

``` Copy
const emp = {
    calcTax(a) {

        console.log(a * 18 / 100)

    },

    calcTax2 : function (a) {

        console.log(a * 20 / 100)

    }

}

const Shubham = {

    salary1 : 20000,

    salary2 : 50000,

}
Shubham.__proto__ = emp
```

![](/Image/03.png)


#### Classes : 
- Class is a program-code template for creating objects.

- Those objects will have some state (variables) and some behavior (functions) inside it.

- In JS, classes are a way to create reusable blueprints for objects. They were introduced in ES (ECMAScript 2015) as a more structured way to implements object-oriented programming ( OOP ) compared to constructor functions and prototypes

- Classes can be provide the template for the create the object..

- Class is the Hard Copy of the objects.

Syntax ,
```Copy
	class Class_Name {
		construcotr() {............}
		myMethod() {.............}

		let obj_name = new Class_Name();
	}
```

Ex ,

```
class Shubham {

    constructor(name, age){

        this.name = name;

        this.age = age

    }
    dispaly(){

        console.log('The name of the student : ' + this.name);

        console.log('The age of the student : '  + this.age)

    }
}

let obj = new Shubham('Shubham', 30);

  

obj.dispaly();
```


#### Constructor :
- If we can't create any constructor, it is automatically invoked by `new` 
- Its also defined with the `constructor` keyword in JS.
- It is automatically called when the object of class can be created.
- Specifically it is used for the initialize the object.
- A **constructor** in JavaScript is a special function used to create and initialize objects. It is primarily used inside **classes** or as a standalone function to set up new instances.

Syntax for Constructor Creation,
	constructor ( ){
		variables
        methods 
	}


###### Before ES6 introduced classes, JavaScript used **constructor functions** to create objects.

```Copy
function Person(name, age) {
  this.name = name;
  this.age = age;
}

let person1 = new Person("Alice", 25);
console.log(person1.name); // Output: Alice
console.log(person1.age); // Output: 25

```

![](/Image/04.png)


Constructor creating in JS,
   Ex , 
```Copy
class Demo{

    constructor(){

        console.log('Initialize the objects.')

    }

}

let o1 = new Demo();

let o2 = new Demo();
```

Output : 

![](/Image/05.png)

##### Constructor with arguments
```Copy
class Demo{

    constructor(name){
        console.log('The name of student : ' + name)
    }

}

let o1 = new Demo('Shubham');

let o2 = new Demo('Rohan');
```

![](/Image/06.png)


#### Inheritance in JS 
- Inheritance in JS is passing down properties and methods from parent class to child class.

- It is also used for the code reusability.

- If child and parent have same method, child method will the used ( Method overriding )

- In JS for inheritance used the `extends` keyword.

- Inheritance is a fundamental concept in object-oriented programming (OOP) that allows one object to acquire the properties and methods of another. JavaScript implements inheritance primarily through **prototypes** and **ES6 classes**.


- Syntax ,

```Copy
class Parent {

}

class Child extends Parent {

}
```

Prototype based Inheritance :

```
function Animal(name) {
  this.name = name;
}

Animal.prototype.speak = function() {
  console.log(`${this.name} makes a noise.`);
};

const dog = new Animal("Buddy");
dog.speak(); // Output: Buddy makes a noise.

```

Example of the class inheritance

```
class Animal {
	eat(){
		console.log("Its animal is eating.")
	}
}

class Dog extends Animal{
	bark(){
		console.log("The Dog is barking.")
	}
}

let obj = new Dog();
obj.eat();
```

Ex ,

```
class Person {
	eat() {
		console.log("Eat")
	}

	sleep() {
		console.log("Sleep")
	}

	work() {
		console.log("Do nothing")
	}
}

class Doctor extends Person {
	work(){
		console.log("Treat Patints");
	}
}

class Engineer extends Person {
	work(){
		console.log("Solve Problems and Building something")
	}
}

```

#### Super Keyword :
- The super keyword is used to call the constructor of its parent class to access the parents properties and methods.

- With using the `super()` method we can access the parent constructor.

- With using `super` keyword we can access the parent class method inside the child class method


Ex , 
```
class Demo{

    constructor(){

        console.log("Parent Constucotr")

    }

    fun1(){

        console.log("Information of Demo")

    }

}

class Child extends Demo{

    constructor(){

        super()

        console.log("Child constructor")

    }

  

    funChild(){

        super.fun1();

        console.log("Inofrmation of child")

    }

}

let obj = new Child()

obj.funChild()
```


Output : 

![](/Image/07.png)

##### Practice Questions : 
Let's Practice ,
	1. Qs. You are creating website for your collage. Create a class User with 2 properties, name and email. It also has a method called viewData() that allows user to view website data.

```
class User{

    constructor(name,email){

        this.name = name

        this.email = email

    }

    viewData(){

        console.log("The name of the student : " + this.name)

        console.log("The email of student : " + this.email)

    }

}

let obj = new User("Shubham", 'srandive245@gmail.com')

obj.viewData()
```

Output :

![](/Image/07.png)

2.Create a new class called Admin which inherits from User. Add a new method called editData to Admin that allows it to website data.


```
class User {

    constructor(name, email) {

      this.name = name;

      this.email = email;

    }

    displayInfo() {

      console.log(`User: ${this.name}, Email: ${this.email}`);

    }

  }

  class Admin extends User {

    constructor(name, email) {

      super(name, email);

    }

    editData(data) {

      console.log(`Editing website data: ${data}`);

    }

  }

  // Example usage:

  const admin = new Admin("Alice", "alice@example.com");

  admin.displayInfo();

  admin.editData("Updated site content");
```

![](/Image/09.png)

##### Exception Handling in JS : 
- You can also use the `try - catch` block for handling the error or exception in JS.
- You can also use the `finally` and `throw` to handle the error

Ex, 
```
try {
  let result = 10 / 0;  // No error, but may be unintended behavior
  console.log(result);

  let a = undefinedVariable; // This will throw an error
} catch (error) {
  console.error("An error occurred:", error.message);
} finally {
  console.log("This will always run, regardless of errors.");
}

```

![](/Image/10.png)



---
ⓘ Metadata <br>
---
Title: My Note<br>
Tags:   #JS #JavaScript<br>
Author : Shubham Randive<br>

---

