		
What is markdown files in GitHub?
    "A markdown" file (.md) is either created or editing using the MacDown editor for MacOS.

	Markdown files (.md) are used for to write formatted text using plain text syntax, and they are commenly used for the documentation.

What is Huskey?
	Huskey is the tool that refers to the managing Git hooks.

What is locators?
	Locators is the identifiers used to find and interact with element on a web page.
### **Types of Locators**

1. **By ID**
    
    - Uses the `id` attribute of an element.
    - Fast and reliable if the `id` is unique on the page.
    - Example:
        
        html
        
        CopyEdit
        
        `<input id="username" type="text">`
        
        Locator: `#username` or `document.getElementById("username")`
2. **By Class Name**
    
    - Uses the `class` attribute of an element.
    - May return multiple elements if the class is not unique.
    - Example:
        
        html
        
        CopyEdit
        
        `<div class="error-message">Invalid username</div>`
        
        Locator: `.error-message` or `document.getElementsByClassName("error-message")`
3. **By Name**
    
    - Uses the `name` attribute of an element.
    - Often used in form fields.
    - Example:
        
        html
        
        CopyEdit
        
        `<input name="email" type="email">`
        
        Locator: `[name="email"]`
4. **By Tag Name**
    
    - Matches elements by their HTML tag.
    - Example:
        
        html
        
        CopyEdit
        
        `<button>Click Me</button>`
        
        Locator: `button` or `document.getElementsByTagName("button")`
5. **By Link Text (Anchor Elements)**
    
    - Finds links by their visible text.
    - Example:
        
        html
        
        CopyEdit
        
        `<a href="/about">Learn More</a>`
        
        Locator: Link text: `"Learn More"`
6. **By Partial Link Text**
    
    - Finds links that contain specific text.
    - Example:
        
        html
        
        CopyEdit
        
        `<a href="/contact">Contact Us</a>`
        
        Locator: Partial link text: `"Contact"`
7. **By XPath**
    
    - Uses the XML Path Language (XPath) to locate elements.
    - Flexible but can be verbose and fragile.
    - Example:
        
        html
        
        CopyEdit
        
        `<div><span class="info">Details</span></div>`
        
        Locator: `//div/span[@class='info']`
8. **By CSS Selector**
    
    - Uses CSS selectors to match elements.
    - Powerful and widely used.
    - Example:
        
        html
        
        CopyEdit
        
        `<input type="text" class="input-field" id="user-email">`
        
        Locator: `input#user-email` or `.input-field`

What is package.json file and what is dependencies and DevDependencies? 

Package.json File : 
		It also contain the metadata about the project such as name, version, script and its dependencies.

Relative path VS Absolute path
	Main difference between a relative path and an absolute path lies in their reference point and how they locate files or directories.

Relative path : 
1. Which defines from current working directories.
2. It don't start with the root directory
3. It is shorter and flexible from absolute path 

Absolute path :
1. An absolute path specifies the full locations of a file or directories starting from the root directory.
2. It is fixed and point to the same location

Ex, 
	Linux / Unix  : /home/user/project/images/logo.png
	Windows : \User\user\project\image\logo.pnh

What is constructor?
1. Constructor is a special method used to initialize objects created by a class. It is automatically called when instance is created


``` C
	class Person{
		constructor(name,age){
			this.name = name
			this.age = age
		}
		
		greed(){
			console.log(`My name is ${this.name} and I am ${this.age} years old`)
		}
	}
	const p1 = new Person("Shubham",21);
	p1.greed();
```

Ex2, Pass by default value to a constructor

```C
	class Person{
		constructor(name = 'Unknown',age = 0){
			this.name = name
			this.age = age
		}
	}
	
	const p1 = new Person();
	const p1 = new Person('Shubham',21)
	
	console.log(p1)
	console.log(p2)
```

	Note : If we can't pass any value to the constructor then JS compiler can automatically define the 'undefined' value for construnctor parameter

What is helper.ts file?
1. This is a TypeScript file used in software project to organize and centralize utility function.
2. These reusable helper function are block of code designed to perform specific, often repetitive tasks that do not belong to the core logic of the application.
3. - Use of the helper.ts file ---> 
	1. Data formatting : Function to format dates, strings and numbers etc.

		```
``` C
export function formatDate(date : Date) :
				string{
					return date.toISOString().split('T')[0]; // Forms date as YYYY-MM-DD
				}
```
		1. Validations
		2. API requests
		3. Maths calculations

What is dry run?
1. A dry run is a process of testing or simulating an operations without actually executing it or making real changes to the system. It is commonly used in programming, debugging and other field to verify the correctness of logic, identify potential issues

map(), reduce() and filter(), foreach() methods in JS.
1. In JS map(), reduce(), filter() and foreach() are array methods used for iterating over arrays in fundamental and declaration way.

- map() :
		- Creates a new array by applying a function to each element of original array.
		- Used to transform data
	
	- Syntax : 
		- array.map(callback(currentValues, index, array))

		```C
			const nums = [1,2,3,4,5]
			
			const square = nums.map(num => num ** 2)
			
			console.log(square)
		```
	  
- reduce() :
		- Reduce the array to a single value by applying a function that accumulate a result
	- Key Points :
		- Takes an accumulator and the current values as arguments.
		- Often used for summing, averaging, or combining elements.
	- Syntax,
		- array.reduce ( callback ( accumulator, currentValue, index, array ), initial Value )
	
	```c
		const nums = [1,2,3,4,5]
		const sum = nums.reduce((acc, num)=> acc + num),0)
		
		console.log(sum)
	```

What is linting ?
Linting issues refer to problems detected by **a linter**, a tool that analyzes your code for potential errors, formatting inconsistencies, or bad practices. These issues usually arise when using Git alongside code quality tools like **ESLint, Prettier, Pylint, or other linters**.



---
ⓘ Metadata <br>
---
Title: My Note<br>
Tags:   #markdown #mdfile<br>
Author : Shubham Randive<br>

---

