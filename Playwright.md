
* This file also present on [GitHub](GitHub_Git.md)  URL FOR NOTES - [URL](https://github.com/ShubhamRandive08/My-Notes.git) URL FOR CODE - [URL](https://github.com/ShubhamRandive08/Playwright_Tests.git)*
##### Get Started with Playwright 
1.1 What is Playwright and Advantages, Limitations <br>
1.2 Playwright Architecture<br>
1.3 Playwright VS Cypress<br>
1.4 Playwright VS Selenium WebDriver<br>
1.5 Software Requirement<br>
1.6 Install Nodejs And VS Code<br>
1.7 Install Playwright in VS Code<br>
1.8 Folder Structure<br>
1.9 Test Explorer<br>
1.10 Run Test<br>
1.11 Run Test on Google Chrome And Microsoft Edge Browsers<br>
1.12 Record Test in VS Code<br>
1.13 Generate HTML Test Report<br>
1.14 Record at Cursor<br>
1.15 Commonly used Terminologies<br>
1.16 First Playwright from Command Prompt<br>
1.17 Pick Locator in VS code<br>
1.18 Install Playwright from Command Prompt<br>
1.19 Run Test in Headless mode<br>
1.20 Run Test in UI mode<br>
1.21 Run Specific Spec file<br>
1.22 Run Test On Different Browser<br>
1.23 Codegen - Record and Play Test<br>

##### Locators, Assertion, Hooks and Annotations<br>
2.1 Locators <br>
2.2 Screenshots<br>
2.3 Hooks<br>
2.4 Add Screenshots to HTML Report when Test failed<br>
2.5 Dropdown List, IFrames and Date Picker <br>
2.6 Mouse Clicks, Keyboard Actions, Drag and Drop<br>
2.7 Assertions - Hard And Soft Assertions<br>
2.8 Watch mode<br>
2.9 Test Traces, Actions metadata, Console, Log, Network<br>


#### Getting Started with Playwright<br>
1.1 What is Playwright and advantages, Limitations<br>
     Playwright is an open-source automation testing tool which is used test end to end modern web mobile applications in headed or headless mode.<br>

###### Advantages :<br>
- Cross Browser Testing - Chrome, Edge, Chromium, Firefox and Webkit<br>
- Cross Platform Testing - Windows, Linux, And MacOS.<br>
- Cross Programming Language - JS, TS, Python, .NET and Java<br>
- Mobile/Web - Mobile emulation of Google Chrome for Android and Mobile, Safari<br>
- Auto wait<br>
- Tracing<br>
- Reporting<br>
- Dynamic wait assertions<br>
- Faster and Reliable<br>
- Powerful Tooling - Codegen, Playwright Inspector and Trace Viewer<br>
- No Flaky test<br>


###### Disadvantages
- Playwright does not have a big community compared to selenium webdriver.
- It does not work on lagacy browsers such IE11
- It is not possible to test with real device mobile apps.

##### 1.2 Playwright Architecture 
![](/Image/Playwright_Architecture.png)

- Client - In the client side our automation test code will be written in different language such as js, python, C# etc.

- Server - The server communicates between client and web browser engines such as chrome, firefox, edge etc. fire.

- Playwright uses COP to commucate with chromium or chrome browser, similarly Playwright has implemented CDP to communicate with other browser such as firefox and webkits etc.

- WebSocket Protocol - WebSocket connection is established to the server from client by using process called Web Socket Handsake, WebSocket sends respons e as soon as it gets requests in real time. Connection will be not terminated until unless connection is closed by either client or server.

- CDP (Chrome DevTools Protocol)


  ##### Playwright VS Cypress

![](/Image/DiffBetPlaywright_Cypress.png)




##### Playwright VS Selenium WebDriver
![](/Image/PlayVSCypress.png)


##### 1.5 Software Requiremen
	a. Node JS
	b. Visual Studio Code (VS code)
	c. JS 
	d.  Operating System ( Window / MAC / Linux )

##### 1.7 Install Playwright in VS code

Step 1 - We need to install "Playwright Test for VSCode" extension.
Step 2 - Press Ctrl + Shift + P enter " install playwright"
Step 3 - Select Playwright configuration and click on ' OK '
Then wait for some time to complete the installation.


###### How to run the Playwright test

###### Step 1
Simply go to the `Playwright test for VSCode` extension and click the `run or run and debug` button

###### Step 2
Go on terminal and fire command `npx playwright test`


#### How to record test in Visual Studio Code

Go On `Playwright test for VSCode` extension and click on the `Playwright` field and 
And then click on the `Record New` field.

Ex, `recordTest.spec.js`

```
import { test, expect } from '@playwright/test';

  

test('test', async ({ page }) => {

  await page.goto('https://github.com/BakkappaN');

  await page.getByRole('link', { name: 'Sign in' }).click();

  await page.getByRole('textbox', { name: 'Username or email address' }).click();

  await page.getByRole('textbox', { name: 'Username or email address' }).fill('Shubham');

  await page.getByRole('textbox', { name: 'Password' }).click();

  await page.getByRole('textbox', { name: 'Password' }).fill('SJSJSJJSJS');

  await page.getByRole('button', { name: 'Sign in', exact: true }).click();

  await expect(page.getByRole('alert')).toContainText('Incorrect username or password.');

});
```


1.15 Commonly used Terminologies in Playwright Test

- `require ?` - To include playwright module or to use playwright module in current JS file.
- `async & await ?` - async is a function, await is valid inside async function only.
		- Zero or more await expressions can be written inside async function
		- When each time async functions is called, it returns a new promise value. Which will be resolved with the value returned by the async function or rejected with an exception.
- `page ?` - It is a browser context object, using context we can open URL and interact with browser.
- `expect ?` It is a library for JS and TS intended for use with test runner such as Jest or playwright Test.
		- It lets you write better assertions for E-to-E testing or components testing


##### Selectors
Playwright supports various types of selectors to locate elements on a web page. Here are the main types :

- CSS selector - Users standard CSS rules select elements 
	ex,
```
button.submit
```

- XPath Selector - Uses XPath expressions to locate elements.
	ex,
```
//input[@type = "email"]
```

ID selector - Uses the elements unique ID.
```
await page.locator("#username").fill('testUser);
```

Class Selector - Selects elements based on class names
```
await page.locator('.error-message').isVisible();
```



##### Include the Playwright module 
```
const { test , expect } = require ('@playwright/test')
```

##### Playwright inbuild methods
1. page.locator ( selector ) - Finds elements matching the given CSS or XPath selector.
	Ex,
```
const element = page.locator('text=Submit');
```

1. locator.click() - Clicks on the located elements 
```
await page.locator('#submit-button').click();
```

1. locator.fill(value)  -  Fills an input field with the specified value.
```
await page.locator('#submit-button').click();
```

2. locator.press(key) - Simulates pressing a keyboard key ( e.g "Enter" )
```
await page.locator('#search-box').press('Enter');
```

3. locator.type(value) - Types text into an input field with a real typing effect
```
await page.locator('#username').type('testUser');
```

4. locator.hover() - Hovers over an elements
```
await page.locator('#menu-item').hover();
```

5. locator.sreenshot() - Captures a screenshot of the element
```
await page.locator('#logo').screenshot({ path: 'logo.png' });
```

6. locator.isVisible() - Checks if the elements is visible
```
const isVisible = await page.locator('#popup').isVisible();
console.log(isVisible);
```

7. locator.isEnbled() - Checks if the elements is enbled.
```
const isEnabled = await page.locator('#submit-button').isEnabled();
console.log(isEnabled);
```

8. locator.isChecked() - Checks if the checkbox or radio button is checked
```
const isChecked = await page.locator('#checkbox').isChecked();
console.log(isChecked);
```

9. page.goto(url) -  Navigates to the specified URL
```
await page.goto('https://example.com');
```

10. page.reload() - Reloads the page
```
await page.reload();
```

11. page.waitForSelector(selector) - Waits for the an elements to appear in the DOM.
```
await page.waitForSelector('#loader');
```

12. page.waitForLoadState(state) - Waits for a specific page load state (e.g "load", "domcontentloaded")
```
await page.waitForLoadState('networkidle');
```

13. page.waitForTimeout(ms) - Waits for a specified time (in milliseconds)
```
await page.waitForTimeout(3000); // Waits for 3 seconds
```

14. page.keyboard.press(key) - Simulates pressing a keyboard key
```
await page.keyboard.press('ArrowDown');
```

15. page.mouse.click(x, y) - Clicks at a specific coordinate
```
await page.mouse.click(100, 200);
```

16. page.evaluate(jsFunction) - Executes JS in the browser context.
```
const title = await page.evaluate(() => document.title);
console.log(title);
```

17. page.screenshot() - Captures the screenshot of thepage
```
await page.screenshot({ path: 'screenshot.png' });
```

1. browser.newContext() - Creates a new browser context for isolated sessions
```
const context = await browser.newContext();
const newPage = await context.newPage();
await newPage.goto('https://example.com');
```

##### How to install Playwright using Command prompt
- First time open the CMD.
Step 1 - Enter '`npm init playwright@latest`
Step 2 - Select Playwright configurations
	Then wait for some time to intall playwright

![](/Image/play_installation_in_CMD.png)


1.19 Run Test in Headless mode
- Playwright Test Report

In Terminal :

```
npx playwright test - For running the all test which is present in test folder

npx playwright show-report - For show the report into the HTML format
```

![](/Image/TestRunsInTerminal.png)

#### If we want to run the test cases in headless mode then simple change the value of `headless` key in `playwright.config.js` file make it `flase` .

In Command Prompt :

```
npx playwright test - For running the all test which is present in test folder

npx playwright show-report - For show the report into the HTML format
```


![](/Image/TestRunsInCMD.png)



1.20 Run the Test in Headed Mode : ( In terminal OR CMD )

```
npx playwright test --headed - For running the all test which is present in test folder

npx playwright show-report - For show the report into the HTML format
```


1.21 Run specific Playwright Spec File
- Firstly Go on Terminal - And run following command 
```
npx playwright test --headed demo.spec.js
```

1.22 Run Test on Different Browsers using the commands

***You Can Also Use the TERMINIL or CMD for run the playwright tests


```
// On Chromium
npx playwright test --project = chomium

// On Firefox
npx playwright test --project = firefox

// On webkit
npx playwright test --project = webkit

// On Microsoft Edge
npx playwright test --project = msedge

// On Googel Chrome
npx playwright test --project = chrome

```


1.23 Record Test using Codegen

***If you can get the test code with the help of the `codegen` , for that you can Simply type the `npm playwright codegen` And simply hit the `ENTER` key  

***Then you can navigate on the `One Chromium Or Any Browser` and `playwright inspector like as a VS Code` 

### ***`Whatever action can perform by you on the given playwright browser that is automatically track by the playwright inspector and this is store into the playwright inspector`


#### @2 Locators, Assertions, Hooks, Annotations and Actions

2.1 Locators - Identify web element<br>
i. By Role <br>
Role : ***alert / alertdialog / application / article / banner / blockquote / button / caption / cell / checkbox / code /  columnheadger / combobox / complementary /  link 
<br>
ex, 
```
await page.getByRole( 'role' , {object}).function();
await page.getByRole('link', { name : 'value'}).click();
```

ii . By Label<br>
ex,<br>
```
await page.getByLabel('value', {exact : true}).fill('value');
```

iii. By Alt Text<br> 
ex,<br>
```
await page.getByAltText('text').click();
```

iv. By Test Id<br>
ex,<br>
```
await page.getByTestid('value').fill('testers talk');
```

v. By Text<br>
- Complete text should be present<br>
ex,<br>
```
await page.getByText('any text', {exact : true}).click();
```

vi. By Title<br>
ex,<br>
```
await page.getByTitle('cypress by testers talk').click();
```

vii. XPath<br>
ex,<br>
```
await page.locator
("xpath = //*[@attr = 'value']").click();
```

viii. CSS selector<br>
ex,<br>
```
await page.locator("css = //*[@attr = 'value']").click();
```

ix. By Placeholder<br>
ex,<br>
```
await page.ByPlaceholder('value').click()
```



---
ⓘ Metadata <br>
--
Title: My Note<br>
Tags:  #playwright #automation<br>
Author : Shubham Randive<br>

---

