		
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

- What is linting ?
Linting issues refer to problems detected by **a linter**, a tool that analyzes your code for potential errors, formatting inconsistencies, or bad practices. These issues usually arise when using Git alongside code quality tools like **ESLint, Prettier, Pylint, or other linters**.

### **`path` in JavaScript (Node.js)** <br>

In **Node.js**, the `path` module provides utilities for working with file and directory paths. It helps handle file system paths in a way that is compatible across different operating systems (Windows, macOS, Linux).
<br>
#### **Importing the `path` Module**

Since `path` is a built-in module in Node.js, you don't need to install anything. Just import it like this:<br>
```
const path = require('path');
```

<br>
### **`path.join()`**

The `path.join()` method joins multiple path segments into a single path, handling directory separators automatically.<br>

```
path.join(...paths)
```

<br>
Ex,
```
const filePath = path.join('users', 'john', 'docs', 'file.txt');
console.log(filePath);
// Output on Windows: 'users\john\docs\file.txt'
// Output on macOS/Linux: 'users/john/docs/file.txt'
```

<br>
### **Other Useful `path` Methods**

|Method|Description|
|---|---|
|`path.basename(filePath)`|Returns the filename.|
|`path.dirname(filePath)`|Returns the directory of the file.|
|`path.extname(filePath)`|Returns the file extension.|
|`path.resolve(...paths)`|Converts a relative path to an absolute path.|

<br>
### **When to Use `path.join()`**

 When constructing file paths dynamically.  
 When ensuring cross-platform compatibility.  
 When normalizing inconsistent paths.
<br><br>
- What is fs module?
The `fs` module in **Node.js** allows you to interact with the **file system**. You can **read, write, delete, update, and manipulate files and directories**.

#### **1. Importing the `fs` Module**

Since `fs` is built into Node.js, you can import it without installing anything:
```
const fs = require('fs');
```

## **Basic File Operations**

### **1️ Reading a File**

You can read a file **synchronously** (`fs.readFileSync()`) or **asynchronously** (`fs.readFile()`).

####  **Asynchronous (Non-blocking) - Recommended**

```
fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) {
    console.error('Error reading file:', err);
    return;
  }
  console.log('File content:', data);
});
```


 Writing to a File
```
fs.writeFile('output.txt', 'Hello, World!', (err) => {
  if (err) throw err;
  console.log('File written successfully!');
});
```


### **Appending to a File**


`fs.appendFile('output.txt', '\nNew content added!', (err) => {   if (err) throw err;   console.log('Content appended!'); });`

---

###  Deleting a File**



`fs.unlink('output.txt', (err) => {   if (err) throw err;   console.log('File deleted!'); });`

---

### ** Checking if a File Exists**



`if (fs.existsSync('example.txt')) {   console.log('File exists!'); } else {   console.log('File does not exist.'); }`

---

## **3. Working with Directories**

### ** 1 Creating a Directory**

`fs.mkdir('newDir', (err) => {   if (err) throw err;   console.log('Directory created!'); });`

🔹 Use `fs.mkdirSync()` for synchronous execution.

---

### ** 2 Reading Directory Contents**



`fs.readdir('.', (err, files) => {   if (err) throw err;   console.log('Files in directory:', files); });`

---

### **3️ Removing a Directory**


`fs.rmdir('newDir', (err) => {   if (err) throw err;   console.log('Directory removed!'); });`

---

## **4. Using `fs.promises` (Modern Async/Await)**

For cleaner **async/await** code, use `fs.promises`:

`const fsPromises = require('fs').promises;  async function readFileAsync() {   try {     const data = await fsPromises.readFile('example.txt', 'utf8');     console.log(data);   } catch (err) {     console.error('Error:', err);   } }  readFileAsync();`

---

## **5. Summary of Key `fs` Methods**

|Method|Description|
|---|---|
|`fs.readFile()`|Reads a file asynchronously.|
|`fs.writeFile()`|Writes to a file asynchronously.|
|`fs.appendFile()`|Appends content to a file.|
|`fs.unlink()`|Deletes a file.|
|`fs.mkdir()`|Creates a directory.|
|`fs.readdir()`|Reads the contents of a directory.|
|`fs.rmdir()`|Deletes a directory.|
|`fs.existsSync()`|Checks if a file exists.|

---

### **When to Use `fs`?**

 Reading/Writing files  
 Creating and managing directories  
 Handling logs, configurations, or storing data



- What is process.cwd() ?
### **`process.cwd()` in Node.js**

The `process.cwd()` method in **Node.js** returns the **current working directory** of the Node.js process.

SYNTAX,
```
process.cwd()
```
- Returns a **string** representing the absolute path of the directory where the Node.js process was started.
- `cwd` stands for **"Current Working Directory"**.


## **When to Use `process.cwd()`?**

 When constructing file paths relative to the root of the project  
 When handling configurations that depend on the working directory  
 When dealing with CLI tools that might be run from different locations



- What is promise.race() and promise.all() ?
Both `Promise.race()` and `Promise.all()` are methods used to handle multiple promises in **JavaScript**, but they behave differently.

## **`Promise.all()`**

###  **Waits for all promises to resolve (or rejects if one fails)**

- Takes an array of promises and returns a single promise.
- Resolves when **all** promises resolve, returning an array of their values.
- **Rejects immediately** if any promise fails (rejects).
Syntax,
```
Promise.all([promise1, promise2, promise3])
  .then(results => console.log(results))
  .catch(error => console.error(error));
```


Ex,
```
const p1 = new Promise(resolve => setTimeout(() => resolve('P1 done'), 1000));
const p2 = new Promise(resolve => setTimeout(() => resolve('P2 done'), 2000));
const p3 = new Promise(resolve => setTimeout(() => resolve('P3 done'), 3000));

Promise.all([p1, p2, p3])
  .then(results => console.log(results)) //  ["P1 done", "P2 done", "P3 done"]
  .catch(error => console.error(error));
```

Handling Rejections 
```
const p1 = Promise.resolve('Success 1');
const p2 = Promise.reject('Error in P2'); //  One promise fails
const p3 = Promise.resolve('Success 3');

Promise.all([p1, p2, p3])
  .then(results => console.log(results)) //  Won't execute
  .catch(error => console.error(error)); //  Logs: "Error in P2"
```


## **`Promise.race()`**

###  **Returns the result of the first promise to settle (resolve or reject)**

- Takes an array of promises and returns a single promise.
- Resolves or rejects **as soon as the first promise settles** (not waiting for all).

Syntax,

```
Promise.race([promise1, promise2, promise3])
  .then(result => console.log(result))
  .catch(error => console.error(error));
```


Ex,
```
const p1 = new Promise(resolve => setTimeout(() => resolve('P1 won!'), 1000));
const p2 = new Promise(resolve => setTimeout(() => resolve('P2 won!'), 2000));
const p3 = new Promise(resolve => setTimeout(() => resolve('P3 won!'), 3000));

Promise.race([p1, p2, p3])
  .then(result => console.log(result)) //  "P1 won!" (Fastest)
  .catch(error => console.error(error));
```

Handling Rejections
```
const p1 = new Promise((_, reject) => setTimeout(() => reject('P1 failed'), 500));
const p2 = new Promise(resolve => setTimeout(() => resolve('P2 won!'), 1000));

Promise.race([p1, p2])
  .then(result => console.log(result)) //  Won't execute
  .catch(error => console.error(error)); //  Logs: "P1 failed"
```


##  `Promise.all()` vs `Promise.race()`**

|Feature|`Promise.all()`|`Promise.race()`|
|---|---|---|
|Resolves When|**All** promises resolve|**First** promise settles|
|Rejects When|**Any** promise rejects|**First** promise rejects|
|Returns|Array of all results|First settled result|
|Use Case|Waiting for multiple tasks to complete|Picking the fastest result|

---

### **When to Use Which?**

 **Use `Promise.all()` when:**

- You need **all tasks** to complete before proceeding.
- Example: Fetching data from multiple APIs at once.

 **Use `Promise.race()` when:**

- You care only about the **first** resolved/rejected promise.
- Example: Implementing a **timeout** mechanism:




- How page action framework use ?

### **Page Action Framework in Test Automation** 

 A Page Action Framework is a **design pattern** used in **test automation** (especially with tools like Selenium, Playwright, and Cypress). It is an **enhanced version** of the **Page Object Model (POM)**, focusing on **actions** instead of just page elements.

## **What is a Page Action Framework?**

- In **POM**, each web page has a corresponding class that stores **locators** and **methods**.
- In **Page Action Framework**, **actions** (like clicking buttons, entering text, etc.) are abstracted into separate **Page Actions** classes.
- This improves **code reusability, readability, and maintainability**.

## **Structure of a Page Action Framework**

###  **Components:**

1. **Page Objects (PO)**
    
    - Stores **locators** (elements of a page).
    - Example: `LoginPage.js`
2. **Page Actions**
    
    - Defines actions (**methods**) that interact with page elements.
    - Example: `LoginActions.js`
3. **Test Cases**
    
    - Uses Page Actions to perform user workflows.
    - Example: `LoginTest.js`

## **Example Using Playwright (JavaScript)**

###  **Step 1: Create the Page Object**

**📁 `pages/LoginPage.js`**

```
class LoginPage {
  constructor(page) {
    this.page = page;
    this.usernameInput = page.locator('#username');
    this.passwordInput = page.locator('#password');
    this.loginButton = page.locator('#login');
  }
}

module.exports = LoginPage;
```

#### Create the Page Action

```
const LoginPage = require('../pages/LoginPage');

class LoginActions {
  constructor(page) {
    this.loginPage = new LoginPage(page);
  }

  async login(username, password) {
    await this.loginPage.usernameInput.fill(username);
    await this.loginPage.passwordInput.fill(password);
    await this.loginPage.loginButton.click();
  }
}

module.exports = LoginActions;
```


#### Use Page Actions in Tests
```
const { test, expect } = require('@playwright/test');
const LoginActions = require('../actions/LoginActions');

test('User can log in successfully', async ({ page }) => {
  const loginActions = new LoginActions(page);
  await page.goto('https://example.com/login');

  await loginActions.login('testuser', 'password123');

  // Validate login success
  await expect(page.locator('.welcome-message')).toHaveText('Welcome, testuser!');
});
```


## **Benefits of Using a Page Action Framework**

 **Separation of Concerns** – UI elements and actions are kept separate.  
 **Code Reusability** – Actions can be used across multiple tests.  
 **Better Readability** – Test cases focus on user workflows rather than low-level UI interactions.  
 **Easy Maintenance** – Changing an element's locator affects only the Page Object, not test scripts.

---

## **5️ When to Use a Page Action Framework?**

🔹 When writing large-scale test automation projects.  
🔹 When needing to **reuse** common actions across different tests.  
🔹 When following **clean code** principles to improve test structure.



---
ⓘ Metadata <br>
---
Title: My Note<br>
Tags:   #markdown #mdfile #othrnotes<br>
Author : Shubham Randive<br>

---

