
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
2.6 Mouse Clicks, Keyboard Actions, Drag and Drop and Date Picker<br>
2.7 Assertions - Hard And Soft Assertions<br>
2.8 Watch mode<br>
2.9 Test Traces, Actions metadata, Console, Log, Network<br>

##### Retry, Repeat, Visual Testing and Parallelism
3.1 Annotations - Skip Test, Only
3.2 Grouping Tests
3.3 Tag Test
3.4 Repeat
3.5 Retry
3.6 Parallelism / Parallel Test Execution
3.7 Parametrize Tests
3.8 Visual Comparison - Visual Testing

##### Page Object Model, Video, Environments, Data Driven Testing
4.1 Env File
4.2 Data Driven Testing
4.3 Run Tests on Multiple Environments - QA, STAGE, PROD etc
4.4 Page Object Model
4.5 Video Recording
4.6 Full Screen Browser

#### Getting Started with Playwright<br>
1.1 What is Playwright and advantages, Limitations<br>
     Playwright is an open-source automation testing tool which is used test end to end modern web, mobile applications in headed or headless mode.<br>

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

- Server - The server communicates between client and web browser engines such as chrome, Firefox, edge etc. fire.

- Playwright uses COP to commutate with chromium or chrome browser, similarly Playwright has implemented CDP to communicate with other browser such as firefox and webkits etc.

- WebSocket Protocol - WebSocket connection is established to the server from client by using process called Web Socket Handsake, WebSocket sends respons e as soon as it gets requests in real time. Connection will be not terminated until unless connection is closed by either client or server.

- CDP (Chrome DevTools Protocol)


  ##### Playwright VS Cypress

![](/Image/DiffBetPlaywright_Cypress.png)




##### Playwright VS Selenium WebDriver
![](/Image/PlayVSCypress.png)


##### 1.5 Software Requirement
	a. Node JS
	b. Visual Studio Code (VS code)
	c. JS / TS
	d.  Operating System ( Window / MAC / Linux )

##### 1.7 Install Playwright in VS code

Step 1 - We need to install "Playwright Test for VSCode" extension.
Step 2 - Press Ctrl + Shift + P enter " install playwright"
Step 3 - Select Playwright configuration and click on ' OK '
Then wait for some time to complete the installation.


###### How to run the Playwright test

###### Step 1
Simply go to the `Playwright test for VSCode` extension and click the `run or run with debug` button

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
Step 1 - Enter `npm init playwright@latest`
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
i. By Role ( Used the locators )<br>
Role : ***alert / alertdialog / application / article / banner / blockquote / button / caption / cell / checkbox / code /  columnheadger / combobox / complementary /  link 
<br>
ex, 
```
await page.getByRole( 'role' , {object}).function();
await page.getByRole('link', { name : 'value'}).click();
```

ii . By Label ( Used the label )<br>
ex,<br>
```
await page.getByLabel('value', {exact : true}).fill('value');
```

iii. By Alt Text ( Used the alt text of image )<br> 
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

<br>
```
import { expect, test } from "@playwright/test"


test('Locator Test', async ({page}) =>{

    // Go to URL

    // await page.goto('https://playwright.dev/')

    // await page.waitForTimeout(3000); // Wait for 3 seconds between requests

    // // By role

    // // await page.getByRole('link',{name : 'Videos'}).click();

    // await page.getByRole('link', {name : 'Docs'}).click()


    // By Label

    // await page.goto('https://www.google.com/')


    // await page.getByLabel('Search', {exact : true}).fill('api testing by testers talk')

    // await page.waitForTimeout(4000)

    // await page.getByLabel('Search', {exact : true}).press('Enter')


    // await page.goto('https://github.com/BakkappaN')

    // await page.getByAltText("View BakkappaN's full-sized avatar").click()


    // By Test ID

    // await page.goto('https://github.com/login')

    // await page.getByTestId('username').fill('srandive245@gmail.com')

    // await page.getByTestId('current-password').fill('Kingsr@09')

    // await page.goto('https://www.youtube.com/')

    // await page.getByPlaceholder('Search').click()

    // await page.getByPlaceholder('Search').fill('@testerstalk')

    // await page.getByPlaceholder('Search').press('Enter')

    // await page.getByTitle("#4 Step by Step Integrating Playwright with CICD Tools(Jenkins+GitHub,Azure DevOps & GitHub Actions)").click()

    // await page.goto('https://www.youtube.com/')

    // await page.getByPlaceholder('Search').fill('@testerstalk')

    // await page.getByPlaceholder('Search').press('Enter')

    // await page.getByText("#4 Step by Step Integrating Playwright with CICD Tools(Jenkins+GitHub,Azure DevOps & GitHub Actions)").click()

    // await page.goto('https://www.youtube.com/')

    // await page.locator("//*[@name='search_query']").click()

    // await page.locator("//*[@name='search_query']").fill('Github with A to Z with Shubham')

    // await page.locator("//*[@name='search_query']").press('Enter')

    // await page.getByText('What Is GitHub? | GitHub Profile Creation | Use of GitHub | Part I').click();

    await page.goto('https://www.youtube.com')

    await page.locator("[name = 'search_query']").click()

    await page.locator("[aria-controls = 'i0']").fill('Github with A to Z with Shubham')

    await page.locator("[name = 'search_query']").press('Enter')

    await page.getByText('What Is GitHub? | GitHub Profile Creation | Use of GitHub | Part I').click();

    await page.waitForTimeout(5000)

})
```
<br>
2.2 Screenshots <br>
	i. Elements Screenshot
	ii. Page Screenshot
	iii. Full Page Screenshot <br>

i. Elements Screenshot : <br>
Capture the screenshot of the element of the page .
```
await page.locator("[class = 'demo-jam']").screenshot({path : './Screenshot/demo.png'})
```

ii. Page Screenshot<br>
Capture the screenshot of the present page of the browser screen
```
await page.screenshot({path : './Screenshots/demo.png});
```

iii. Full Page Screenshot<br>
Capture the screenshot of the entire page of the scrolling page
```
await page.screenshot({path : './Screenshot/demo.png', fullPage : true})
```
<br>
-  Add Screenshots to Playwright Test Report when Test failed<br>
***`For adding the screenshot if the test case getting failed that time we can perform simple action that is - Go to the playwright.config.js file and go inside the defineConfig property and then go inside of the use property and add that file 'screenshot : 'only-on-failure' ' value`

<br>
```
// Include playwright module

const { test, expect } = require('@playwright/test')  

test('Take a screenshot in playwright', async ({ page }) => {

    await page.goto('https://www.youtube.com/@Mr.Shubham_Randive')

    // Element Screenshot

    await page.locator("[class = 'yt-spec-avatar-shape__image-overlays yt-spec-avatar-shape__image']").screenshot({path : './Screenshots/element.png'})

    // Page Screenshot

    await page.screenshot({path : './Screenshots/page.png'})

    // Full page screenshot

    await page.screenshot({path : './Screenshots/Full_page.png', fullPage : true})
    
    await page.close();

})
```
<br>
2.3 Hooks : 
`Hooks is nothing but block of code  and that will be getting executed after the test cases or before the test cases. They are useful for setup, teardown, and handling test lifecycle events.` <br>

## **Types of Hooks in Playwright**<br>

Playwright provides the following hooks inside `test.describe()`: <br>

|Hook|Description|
|---|---|
|`beforeAll()`|Runs **once** before all tests in a test suite.|
|`beforeEach()`|Runs **before each** test inside a suite.|
|`afterEach()`|Runs **after each** test inside a suite.|
|`afterAll()`|Runs **once** after all tests in a test suite.|
<br>
## **When to Use Hooks in Playwright?**

 **`beforeAll()`** → Use for **global setup** like database connections, authentication, or API mocking.  
 **`beforeEach()`** → Use for **navigating to a page** or initializing test data before each test.  
 **`afterEach()`** → Use for **cleaning up test data, logging, or taking screenshots** on failure.  
 **`afterAll()`** → Use for **closing databases, clearing caches, or final cleanup**.<br>
- beforeAll() - It runs before all tests in test suite...... We can't use the page object inside the beforeAll() hook


```
test.beforAll('Runs before all test cases', async() => {
	await page.gotot('https://www.youtube.com')
	console.log('Runs before the all test cases')
})
```
<br>
- beforeEach() : It runs before the each test cases
```
test.describe('TestCases for the Playwright hooks', async () =>{
	test.beforeEach('Runs before each test cases', async ({ page }) => {
		console.log('Runs before each test cases');
		await page.goto('https://www.youtube.com')
	})
})
```

-  afterAll() - It runs after all tests in test suite...... We can't use the page object inside the beforeAll() hook


```
test.afterAll('Runs before all test cases', async() => {
	console.log('Runs after the all test cases')
})
```
<br>
- afterEach() : It runs after the each test cases
```
test.describe('TestCases for the Playwright hooks', async () =>{
	test.afterEach('Runs after each test cases', async ({ page }) => {
		console.log('Runs after each test cases');
	})
})
```

Code
<br>
```
import {test,expect} from '@playwright/test'

const logGreenMessage = async (message, delay = 1000) => {

    await new Promise(resolve => setTimeout(resolve, delay));

    console.log(`\x1b[32m✔ ${message}\x1b[0m`); // \x1b[32m makes text green

};

test.describe('Hooks in Playwright', () =>{

    test.beforeEach('Run before each test', async ({page}) => {

        await page.goto('https://www.youtube.com/')

        await page.getByRole('combobox', { name: 'Search' }).click();

    })

  

    test.beforeAll('Run before all test', async() => { // In that case we cant use 'page' object

        console.log('Runs before all tests..')

    })

  

    test.afterEach('Run after each test', async ({page}) => {

        console.log('Runs after the each test')

    })

  

    test.afterAll('Run after all test', async() => { // In that case we cant use 'page' object

        console.log('Runs after all tests..')

    })

    test('Test No. 01 - Hooks', async ({page}) =>{

        // Search with keywords

        await page.getByRole('combobox', { name: 'Search' }).fill('cypress by testers talk');

        await expect(page.getByRole('button', { name: 'Search', exact: true })).toBeEnabled();

        await page.getByRole('button', { name: 'Search', exact: true }).click();

        await page.waitForTimeout(5000);

        //Click on playlist

        await page.getByRole('link', { name: 'Cypress by Testers Talk☑️' }).click();

        // Validate title

        await expect(page).toHaveTitle('Cypress Tutorial Full Course | Cypress Automation | Learn Cypress in 5 Hrs - YouTube');

        await page.close();

        await logGreenMessage("Test 1 Passed", 1000); // D

    })

    test('Test No. 02 - Hooks', async ({page}) =>{

        // Search with keywords

        await page.getByRole('combobox', { name: 'Search' }).fill('GitHub with A to Z with Shubham');

        await expect(page.getByRole('button', { name: 'Search', exact: true })).toBeEnabled();

        await page.getByRole('button', { name: 'Search', exact: true }).click();

        await page.getByText('What Is GitHub? | GitHub Profile Creation | Use of GitHub | Part I').click();

        await page.close();

        await logGreenMessage("Test 2 Passed", 1000); // D

    })

})
```

<br>
2.5 Dropdown List, IFrames and Drag and Drop

Dropdown List : <br>
When you want to select the Dropdown items, for that we use `var_name.selectOption('value')` method <br>

There are use the following two methods,
<br>
	i. Value
	ii. Visible Text

i. Value : We use `value` attribute  as a getting the value from the dropdown

Ex,
```
const dropDownList = page.locator('#mount')

dropDownList.selectOption('5')
```
<br>
ii. Visible Text : We use `visible text` as for getting the value from the dropdown<br>
Ex, 
```
const dropDownList = page.locator('#main')

dropDownList.selectOption('Aug')
```


```
import {test,expect} from '@playwright/test'

test.describe('Script for the dropdown cheking', async () =>{

    test.beforeEach('Before each test cases', async ({page}) =>{

        await page.goto('https://www.facebook.com/')

    })

    test('Test No. 1 - DropDown List', async ({page}) => {

        await expect(page.locator("[class = '_42ft _4jy0 _6lti _4jy6 _4jy2 selected _51sy']")).toBeVisible();

        await page.locator("[class = '_42ft _4jy0 _6lti _4jy6 _4jy2 selected _51sy']").click();

        const dropDownList = page.locator('#month');

        await page.waitForTimeout(5000)

        dropDownList.selectOption('5') // By Value

        dropDownList.selectOption('Aug')

        await page.waitForTimeout(5000)

        await page.waitForTimeout(5000)

        await page.close()

    })

})
```


I Frames in Playwright and Drag and Drop<br>
- In that case firstly we can find out the `iFrame` elements then we can perform action which is in within the iframe <br>
- In that scenario we can perform following actions
		- Firstly find the `iframe` elements
		- Define the `src` and the `dest` elements
		- Then perform the action of the `drag` and `drop`


```
import { test, expect } from '@playwright/test'

test.describe('Test Cases for iframe in playwright the Drag and Drop Functionalites', async () => {

    let passedTests = [];

    let failedTests = [];

    test.beforeEach(async ({ page }) => {

        await page.goto('https://jqueryui.com/droppable/')

        console.log('\x1b[36mStarting a new test...\x1b[0m');

    test.afterEach(async ({ }, testInfo) => {

        if (testInfo.status === 'passed') {

            passedTests.push(testInfo.title);

            console.log(`\x1b[32m✔ Test Passed: ${testInfo.title}\x1b[0m`);

        } else {

            failedTests.push(testInfo.title);

            console.log(`\x1b[31m✖ Test Failed: ${testInfo.title}\x1b[0m`);

        }

    });

    test.afterAll(async () => {

        console.log('\nSummary:');

        if (failedTests.length === 0) {

            console.log('\x1b[32m✔ All tests passed successfully!\x1b[0m');

        } else {

            console.log('\x1b[31m✖ Some tests failed!\x1b[0m');

        }

    });

    test('Test No. 01 - Drag and Drop', async ({ page }) => {

        // Identify the iframe

        const iFrameElement = page.frameLocator('.demo-frame')

        // source and destionation

        const dragElement = iFrameElement.locator("[id = 'draggable']")

        const dropElement = iFrameElement.locator("[id = 'droppable']")

        // Drag and Drop elements

        await dragElement.dragTo(dropElement)

    })

})
```
<br>
2.6 A. Mouse Action in Playwright <br>
 There are several mouse click
	 - click() : This is used for the click on the particular element 
	 - dblclick() : This is used for the double click on the element
	 - rightclick : This is used for perform the right click on the element
	 - leftclick : This is used for perform the left click on the element
	 - middleclick : This is used for the perform the middle click on the element <br>

Ex, 
```
import {test,expect} from '@playwright/test'

test.describe('Mouse Action in playwright', async () => {

    test('Test No. 01 - Mouse Action', async ({page}) => {

        await page.goto('https://www.bing.com/search?q=A+to+Z+with+Shubham')

        // await page.locator('.gLFyf').click();

        // await page.locator('.gLFyf').type('https://www.youtube.com/@Shubham_Randive')

        //click

         await page.getByRole("link", {name : 'A to Z with Shubham - YouTube'}).first().click();

        // double click

         await page.getByRole('link', {name : `A to Z with Shubham - YouTube`}).first().dblclick()

        // mouse right click

         await page.getByRole('link', {name : `A to Z with Shubham - YouTube`}).first().dblclick({button : 'right'})

        // mouse middle click

         await page.getByRole('link', {name : `A to Z with Shubham - YouTube`}).first().dblclick({button : 'middle'})

        //left click

         await page.getByRole('link', {name : `A to Z with Shubham - YouTube`}).first().dblclick({button : 'left'})
        
        //mouse hover

        await page.locator("[aria-label = 'Search using voice']").hover()

    })

})
```

B. Keyboard Action in Playwright <br>
This is used for the perform the keyboard action.<br>
In that we press following keys,<br>
- Backquote, Minus, Equal, Backslash, Tab, Delete, Escape, ArrowDown, End, Enter, Home, Insert, PageDown, PageUp, ArrowRight, ArrowUp, F1 - F12, 0 - 9, A - Z, etc. <br>
```
import {test, exact, expect } from '@playwright/test'

import exp from 'constants'

test.describe('Playwright tests for keyboard action', async () =>{

    test('Test No.01 : Keybord Action', async ({page}) => {

        page.goto('https://www.youtube.com/')

        await expect(page.locator("//input[@name = 'search_query']")).toBeVisible();

        await page.locator("//input[@name = 'search_query']").click()

        // await page.locator("//input[@name = 'search_query']").type('Playwright by testers talk')

        // Press Enter

        //await page.locator("//input[@name = 'search_query']").press('Enter')

        // Press control + a and Delete

        // page.locator("//input[@name = 'search_query']").click()

        //await page.locator("//input[@name = 'search_query']").press('Control+a')

        //await page.locator("//input[@name = 'search_query']").press('Delete')

  

        // Press Tab

        await page.keyboard.press('Tab')

        await page.keyboard.press('Tab')

        await page.keyboard.press('Enter')

        await page.waitForTimeout(10000)

        await page.close()

    })
})
```
<br>
C. Date Picker
In that case we can select the any date from the particular date UI<br>
Which is help to us for select the date<br>
```
const {test,expect} = require('@playwright/test')

test.describe('Date Picker', async () =>{

    test('Peak the Date', async ({page}) => {

        await page.goto('https://jqueryui.com/datepicker/')

        const frameElement = page.frameLocator("//iframe[@class = 'demo-frame']")

        frameElement.locator('.hasDatepicker').click()

        // Today's date

        await frameElement.locator(".ui-datepicker-today").click();

        await page.waitForTimeout(10000)

        // Custom Date

         const defaultDate = frameElement.locator('.ui-datepicker-today > a')

         const currentDateValue = await defaultDate.getAttribute('data-date') // 28 as today

         let customDate = parseInt((currentDateValue) - 3)

         const element = `[date-date ='${customDate.toString()}']`

         await frameElement.locator(element).click()

         await page.waitForTimeout(5000)
    })
})
```
<br> Assertions - Hard Assertion and Soft Assertions<br>
- Soft Assertions - It is a type of the assertions, whenever assertion got a failed that time can't stop the test execution. In That we use `soft()` method for declare the soft assertion<br>
Ex,
```
const {test, expect}  = require('@playwright/test')

test.describe('Soft Assertions', async () => {
	test('Soft method', async ({ page }) => {
		await expect.soft(page).toHaveURL('https://www.google.com')
	})
})
```

- Hard Assertions - It is a type of the assertion, in that case if assertion got failed that time test execution automatically failed
1. URL - toHaveURL()
2. title - toHaveTitle()
3. text - toHaveText()
4. Editable - toBeEditable()
5. Visible - toBeVisible()
6. Enabled - toBeEnabled()
7. Disabled - toBeDisabled()
8. Empty - toBeEmpty()
9. Count - toHaveCount()<br>
```
const {test, expect} = require('@playwright/test')

const exp = require('constants')

test.describe('Assertions', async () => {

    test('Validate assertions', async ({page}) => {

        await page.goto('https://www.youtube.com/results?search_query=playwright+tutorial+full+course')

        //assert URL

        await expect(page).toHaveURL('https://www.youtube.com/results?search_query=playwright+tutorial+full+course')

        // assert Title

        await expect(page).toHaveTitle("playwright tutorial full course - YouTube")

        // assert Text

        await expect(page.locator("//input[@name = 'search_query']").first()).toHaveValue("playwright tutorial full course")

        // assert editable enabled visible

        await expect(page.locator("//input[@name = 'search_query']").first()).toBeEditable()

        await expect(page.locator("//input[@name = 'search_query']").first()).toBeVisible()


        await expect(page.locator("//input[@name = 'search_query']").first()).toBeEnabled();


        // assert disabled empty count

        // await expect(page.locator("//input[@name = 'search_query']").first()).toBeDisabled()

        // await expect(page.locator("//input[@name = 'search_query']").first()).toBeEmpty() // Should be empty

        await expect(page.locator("//input[@name = 'search_query']").first()).not.toBeEmpty() // Should not empty

        await expect(page.locator("//input[@name = 'search_query']")).toHaveCount(1)
        
        await page.waitForTimeout(60)

    })

})
```

2.8 Watch Mode in Playwright<br>
In Playwright, **watch mode** refers to a development mode that automatically reruns tests when it detects file changes. This is useful for rapid debugging and development.<br>

### **How to Use Watch Mode in Playwright**<br>

Playwright does not have a built-in `--watch` flag like Jest, but you can achieve similar functionality using `--ui` mode or external tools.<br>

#### **1. Using Playwright Test UI Mode (Recommended)<br>**

Playwright provides a **UI mode** that includes a watch feature:<br>
```
npx playwright test --ui
```

This opens an interactive UI where:<br>

- Tests rerun automatically when you edit test files.<br>
- You can click to rerun tests individually.<br>
- Debugging tools (e.g., time travel, trace viewer) are available.<br>

2.9 Test Traces, Actions, Metadata, Console, Log, Network<br>
Playwright provides powerful debugging and tracing tools, including **Test Traces, Actions, Metadata, Console Logs, and Network Logs**. These help developers analyze test execution, debug failures, and optimize automation.

---

## **1. Test Traces (Tracing)**<br>

Tracing in Playwright captures detailed execution steps, including network requests, console logs, and screenshots.<br>

### **Enable Tracing<br>**

Add tracing in your Playwright test configuration (`playwright.config.ts`):
```
import { defineConfig } from '@playwright/test';

export default defineConfig({
  use: {
    trace: 'on', // 'on', 'off', 'retain-on-failure', 'on-first-retry'
  },
});

```


Or, enable tracing dynamically in a test:
```
import { test } from '@playwright/test';

test.beforeEach(async ({ page }, testInfo) => {
  await testInfo.attach('trace', { path: 'trace.zip' });
  await page.context().tracing.start({ screenshots: true, snapshots: true });
});

test.afterEach(async ({ page }) => {
  await page.context().tracing.stop({ path: 'trace.zip' });
});

```
### **View Trace Files<br>**

1. Run tests:
```
npx playwright test
```

    
1. Open the trace file:<br>
```
npx playwright show-trace trace.zip
```
    
1. The UI will display steps, actions, console logs, network requests, and more.<br>

---

## **2. Actions (Step Recorder)<br>**

Playwright records actions performed during a test for debugging.<br>

### **Enable Action Recorder**<br>

Run the following command to open Playwright Inspector:<br>

`npx playwright codegen example.com`

It will:<br>

- Open a browser.<br>
- Record interactions (clicks, inputs, navigations).<br>
- Generate Playwright test code.<br>

---

## **3. Metadata**<br>

Metadata includes information like test duration, retries, and environment details.<br>

### **Adding Metadata**<br>

You can add custom metadata to tests:
```
import { test } from '@playwright/test';

test('example test', async ({ page }, testInfo) => {
  console.log(`Running test: ${testInfo.title}`);
  console.log(`Worker: ${testInfo.workerIndex}`);
  console.log(`Retries: ${testInfo.retry}`);
});

```


Metadata is included in Playwright reports:

`npx playwright test --reporter=json`

---

## **4. Console Logs**<br>

Playwright captures browser console logs.<br>

### **Enable Console Logging**
```
import { test } from '@playwright/test';

test('console log test', async ({ page }) => {
  page.on('console', (msg) => console.log(`Console Log: ${msg.text()}`));
  await page.goto('https://example.com');
});

```

This captures logs from the browser console.<br>

---

## **5. Network Logs**<br>

Playwright records network requests & responses.
```
test('track network requests', async ({ page }) => {
  page.on('request', (req) => console.log(`Request: ${req.url()}`));
  page.on('response', (res) => console.log(`Response: ${res.url()} - ${res.status()}`));
  
  await page.goto('https://example.com');
});

```
### **Capture Network Requests**


---

## **6. Log Files**<br>

You can store logs in a file using `fs` in Node.js.<br>

Example:
```
import fs from 'fs';

test('save logs to file', async ({ page }) => {
  let logData = '';

  page.on('console', (msg) => {
    logData += `Console Log: ${msg.text()}\n`;
  });

  page.on('response', (res) => {
    logData += `Response: ${res.url()} - ${res.status()}\n`;
  });

  await page.goto('https://example.com');

  fs.writeFileSync('playwright-logs.txt', logData);
});

```

This saves logs to `playwright-logs.txt`.

---

## **Summary Table**<br>

|Feature|Purpose|
|---|---|
|**Tracing**|Capture test steps, network, console, and metadata.|
|**Actions**|Record user interactions & generate test code.|
|**Metadata**|Get test details like retries, duration, and worker info.|
|**Console Logs**|Capture browser console logs.|
|**Network Logs**|Monitor HTTP requests and responses.|
|**Log Files**|Save logs to a file for later analysis.|

3.1 Annotations - Skip Test, Only<br>
only - used for run only a single test cases

|Annotation|Purpose|
|---|---|
|`test.skip()`|Skips the test (conditionally or unconditionally).|
|`test.fixme()`|Marks a test as broken (won't fail the suite).|
|`test.fail()`|Marks a test as expected to fail.|
|`test.slow()`|Increases timeout for slow tests.|
|`testInfo.annotations.push()`|Adds custom metadata to a test.|
Ex, 
```
const {test, expect} = require('@playwright/test')

const exp = require('constants')

test.describe('Annotations', async () => {

    test.skip('Validate assertions 1', async ({page}) => {

        await page.goto('https://www.youtube.com/results?search_query=playwright+tutorial+full+course')

        //assert URL

        await expect(page).toHaveURL('https://www.youtube.com/results?search_query=playwright+tutorial+full+course')

        // assert Title

        await expect(page).toHaveTitle("playwright tutorial full course - YouTube")

        // assert Text

        await expect(page.locator("//input[@name = 'search_query']").first()).toHaveValue("playwright tutorial full course")

        // assert editable enabled visible

        await expect(page.locator("//input[@name = 'search_query']").first()).toBeEditable()

        await expect(page.locator("//input[@name = 'search_query']").first()).toBeVisible()

        await expect(page.locator("//input[@name = 'search_query']").first()).toBeEnabled();

        // assert disabled empty count

        // await expect(page.locator("//input[@name = 'search_query']").first()).toBeDisabled()

        // await expect(page.locator("//input[@name = 'search_query']").first()).toBeEmpty() // Should be empty

        await expect(page.locator("//input[@name = 'search_query']").first()).not.toBeEmpty() // Should not empty

        await expect(page.locator("//input[@name = 'search_query']")).toHaveCount(1)

        await page.waitForTimeout(60)

    })

    test.only('Validate assertions 2', async ({page}) => {

        await page.goto('https://www.youtube.com/results?search_query=playwright+tutorial+full+course')

        //assert URL

        await expect(page).toHaveURL('https://www.youtube.com/results?search_query=playwright+tutorial+full+course')

        // assert Title

        await expect(page).toHaveTitle("playwright tutorial full course - YouTube")

        // assert Text

        await expect(page.locator("//input[@name = 'search_query']").first()).toHaveValue("playwright tutorial full course")

        // assert editable enabled visible

        await expect(page.locator("//input[@name = 'search_query']").first()).toBeEditable()

        await expect(page.locator("//input[@name = 'search_query']").first()).toBeVisible()

        await expect(page.locator("//input[@name = 'search_query']").first()).toBeEnabled();

        // assert disabled empty count

        // await expect(page.locator("//input[@name = 'search_query']").first()).toBeDisabled()

        // await expect(page.locator("//input[@name = 'search_query']").first()).toBeEmpty() // Should be empty

        await expect(page.locator("//input[@name = 'search_query']").first()).not.toBeEmpty() // Should not empty

        await expect(page.locator("//input[@name = 'search_query']")).toHaveCount(1)
        
        await page.waitForTimeout(60)

    })

    test('Validate assertions 3', async ({page}) => {

        await page.goto('https://www.youtube.com/results?search_query=playwright+tutorial+full+course')

        //assert URL

        await expect(page).toHaveURL('https://www.youtube.com/results?search_query=playwright+tutorial+full+course')

        // assert Title

        await expect(page).toHaveTitle("playwright tutorial full course - YouTube")

        // assert Text

        await expect(page.locator("//input[@name = 'search_query']").first()).toHaveValue("playwright tutorial full course")

        // assert editable enabled visible

        await expect(page.locator("//input[@name = 'search_query']").first()).toBeEditable()

        await expect(page.locator("//input[@name = 'search_query']").first()).toBeVisible()

        await expect(page.locator("//input[@name = 'search_query']").first()).toBeEnabled();

        // assert disabled empty count

        // await expect(page.locator("//input[@name = 'search_query']").first()).toBeDisabled()

        // await expect(page.locator("//input[@name = 'search_query']").first()).toBeEmpty() // Should be empty

        await expect(page.locator("//input[@name = 'search_query']").first()).not.toBeEmpty() // Should not empty

        await expect(page.locator("//input[@name = 'search_query']")).toHaveCount(1)

        await page.waitForTimeout(60)

    })

})
```

3.2 Group Tests <br>
For run the test in group we should be use the `describe()` method<br>
3.3 Tag Test<br>
In that case we add tag to test cases and execute that tests we using `--grep`  and then write the tag name

Syntax
```
npx playwright test --grep 'Tag1'
```

Ex, 
```
// Include playwright module

const { test, expect } = require('@playwright/test')  // test - It is used to create the test cases , expect - to validate or to assert the web dev. or any text.

// Write a test

// page - page is the object with the help of that we can interact with the browser.

test('Test 1 @Tag1', async ({ page }) => {

    await page.goto('https://www.youtube.com/')

    // Go to URL

    // Search with keywords

    await page.getByRole('combobox', { name: 'Search' }).click();

    await page.getByRole('combobox', { name: 'Search' }).fill('cypress by testers talk');

    await expect(page.getByRole('button', { name: 'Search', exact: true })).toBeEnabled();

    await page.getByRole('button', { name: 'Search', exact: true }).click();

    await page.waitForTimeout(5000);

    //Click on playlist

    await page.getByRole('link', { name: 'Cypress by Testers Talk☑️' }).click();

    // Validate title

    await expect(page).toHaveTitle('Cypress Tutorial Full Course | Cypress Automation | Learn Cypress in 5 Hrs - YouTube');
    
    await page.close();

})

test('Test 2 @Tag2', async ({ page }) => {

    await page.goto('https://www.youtube.com/')

    // Go to URL

    // Search with keywords

    await page.getByRole('combobox', { name: 'Search' }).click();

    await page.getByRole('combobox', { name: 'Search' }).fill('cypress by testers talk');

    await expect(page.getByRole('button', { name: 'Search', exact: true })).toBeEnabled();

    await page.getByRole('button', { name: 'Search', exact: true }).click();

    await page.waitForTimeout(5000);

    //Click on playlist

    await page.getByRole('link', { name: 'Cypress by Testers Talk☑️' }).click();  

    // Validate title

    await expect(page).toHaveTitle('Cypress Tutorial Full Course | Cypress Automation | Learn Cypress in 5 Hrs - YouTube');

    await page.close();

})

test('Test 3 @Tag1', async ({ page }) => {

    await page.goto('https://www.youtube.com/')

    // Go to URL

    // Search with keywords

    await page.getByRole('combobox', { name: 'Search' }).click();

    await page.getByRole('combobox', { name: 'Search' }).fill('cypress by testers talk');

    await expect(page.getByRole('button', { name: 'Search', exact: true })).toBeEnabled();

    await page.getByRole('button', { name: 'Search', exact: true }).click();

    await page.waitForTimeout(5000);

    //Click on playlist

    await page.getByRole('link', { name: 'Cypress by Testers Talk☑️' }).click();

    // Validate title

    await expect(page).toHaveTitle('Cypress Tutorial Full Course | Cypress Automation | Learn Cypress in 5 Hrs - YouTube');
    
    await page.close();

})
```

Run The Above test cases with tag name
```
npx playwright test --grep 'Tag1'
```

3.4 Repeat the test<br>
For running the test multiple time we use following commands, <br>
```
npx playwright test test_name --repeat-each = 2
```

Ex, 
```
 npx playwright test assertions.spec.js --repeat-each=2
```


3.5 How to `Retry` test<br>
Simply go in te `playwright.config.js` file and change the value of `retries: process.env.CI ? 2 : 0,

Ex, 
```
retries: process.env.CI ? 2 : 1, // This retry 1 time
retries: process.env.CI ? 2 : 2, // This retry 2 times
```


3.6 Parallelism / Parallel Test Execution<br>
Playwright supports **parallel test execution** to speed up test runs. You can run tests in parallel using **multiple workers** or within a single file using `test.describe.parallel()`.

Syntax
```
npx playwright test test_name --worker = no_of_worker
```

Ex,
```
npx playwright test group.spec.js --worker = 3 // This is runs 3 test cases at a same time
```


## **1. Run Tests in Parallel (Default Behavior)<br>**

Playwright runs tests in parallel by default using multiple **workers** (separate processes).<br>

### **Run Tests in Parallel<br>**

`npx playwright test`

This automatically runs tests in parallel, utilizing the available CPU cores.<br>

### **Control the Number of Parallel Workers**<br>

By default, Playwright detects the number of CPU cores and assigns workers accordingly. <br>You can manually set the number of workers:<br>

`npx playwright test --workers=4`

Or, set it in `playwright.config.js`:
```
import { defineConfig } from '@playwright/test';

export default defineConfig({
  workers: 4,  // Set the number of parallel workers
});

```

---

## **2. Parallel Execution in a Single File<br>**

By default, tests in a single file run **sequentially**. To make them run in parallel, use `test.describe.parallel()`:<br>

```
import { test, expect } from '@playwright/test';

test.describe.parallel('Parallel Test Suite', () => {

  test('Test A', async ({ page }) => {
    await page.goto('https://example.com');
    await expect(page).toHaveTitle('Example Domain');
  });

  test('Test B', async ({ page }) => {
    await page.goto('https://example.com/about');
    await expect(page).toHaveURL(/about/);
  });

});
```

###  Key Points:

- Tests in `test.describe.parallel()` run **concurrently**.<br>
- Each test gets a separate browser context.<br>

---

## **3. Disable Parallel Execution (Force Sequential)**

If you want to **run tests one after another**, use `--workers=1`:<br>

`npx playwright test --workers=1`

Or, use `test.describe.serial()`:<br>

```
test.describe.serial('Serial Test Suite', () => {
  test('Step 1', async ({ page }) => {
    await page.goto('https://example.com');
  });

  test('Step 2', async ({ page }) => {
    await page.goto('https://example.com/about');
  });
});
```

- **`test.describe.serial()`** ensures that tests **run sequentially in the same worker**.
- Useful for dependent tests.<br>

---

## **4. Parallelism in CI/CD<br>**

For **CI/CD pipelines**, you can distribute tests across multiple machines using **sharding**:<br>

`npx playwright test --shard=1/3`<br>

- This command runs **only 1/3rd of the tests** on a given machine.<br>
- Used when **splitting tests across multiple CI agents**.<br>

---

## **5. Run Specific Tests in Parallel<br>**

You can mark **only certain tests** to run in parallel using `test.parallel()`:
```
test.parallel('Test runs in parallel', async ({ page }) => {
  await page.goto('https://example.com');
});
```

---

## **6. Best Practices for Parallel Testing<br>**

 **Use `test.describe.parallel()`** for independent tests.  <br>
 **Use `test.describe.serial()`** for dependent tests.  <br>
 **Avoid using shared state between tests** (each test should be isolated).  <br>
 **Increase `workers` in CI/CD** for better performance.  <br>
 **Use `sharding`** when running tests on multiple machines.<br>


3.8 Parametrize Tests in Playwright <br>
In **Playwright Test**, you can use **parameterized tests** to run the same test with different data inputs. This helps avoid duplicate code and improves test coverage.<br>
```
// Include playwright module

const { test, expect } = require('@playwright/test')  // test - It is used to create the test cases , expect - to validate or to assert the web dev. or any text.

// Write a test

// page - page is the object with the help of that we can interact with the browser.

const testPara = ['Playwright by testers talk', 'Cypress by testers talk', 'Javascript by testers talk']

for (const searchKeyword of testPara) {

    test(`Parameterize test in playwright ${searchKeyword}`, async ({ page }) => {

        await page.goto('https://www.youtube.com/')

        // search with keyword

        await page.getByPlaceholder("Search").click()

        await page.getByPlaceholder("Search").fill(searchKeyword)

        await page.getByPlaceholder("Search").press("Enter")

        await page.waitForTimeout(5000)

    })
}
```

3.8 Visual Comparison - Visual Testing<br>
Visual comparison and visual testing in Playwright help ensure that web applications render correctly across different environments, browsers, and screen sizes. Here’s a breakdown of how visual testing works in Playwright:

### **1. Visual Testing in Playwright** <br>

Playwright supports screenshot-based testing to compare the UI against a baseline image. This helps catch unintended UI changes due to CSS updates, responsive issues, or browser inconsistencies.<br>

### **2. How Visual Comparison Works<br>**

- **Baseline Image:** The test captures a reference (baseline) screenshot.
- **Current Screenshot:** A new screenshot is taken during test execution.
- **Image Comparison:** Playwright compares the new screenshot with the baseline.
- **Threshold Configuration:** Small tolerances can be set to account for minor differences like anti-aliasing.<br>

### **3. Implementing Visual Testing in Playwright<br>**

Playwright provides built-in methods for visual comparisons:<br>

#### **Snapshot Testing<br>
```
import { test, expect } from '@playwright/test';

test('visual comparison test', async ({ page }) => {
    await page.goto('https://example.com');
    expect(await page.screenshot()).toMatchSnapshot('homepage.png');
});

```


- The first run generates a baseline screenshot.<br>
- On subsequent runs, Playwright compares new screenshots to the baseline.<br>

#### **Full Page Screenshot Comparison**

```
test('full-page visual regression test', async ({ page }) => {
    await page.goto('https://example.com');
    expect(await page.screenshot({ fullPage: true })).toMatchSnapshot('fullpage.png');
});

```
### **4. Handling Visual Differences<br>**

- **Set Tolerances:** Allow small pixel differences.<br>
- **Ignore Dynamic Elements:** Hide or mask elements like timestamps, ads, or animations.<br>
- **Update Baselines:** When intentional UI changes occur, update the snapshot using `--update-snapshots`.<br>

### **5. Tools for Enhanced Visual Testing<br>**

- **Playwright Test Built-in Features** – Basic screenshot comparison.<br>
- **Third-party Tools:** Integrate Playwright with tools like Applitools, Percy, or Loki for AI-powered visual testing. <br>


4.1 Env file in Playwright

In Playwright, you can use **`.env`** files to manage environment variables, such as API keys, base URLs, or authentication credentials. Here’s how you can use them effectively. <br>

---

### **1. Install dotenv Package**<br>

Playwright does not have built-in support for `.env` files, so you need to install the `dotenv` package to load environment variables.<br>

`npm install dotenv`

---

### **2. Create a `.env` File<br>**
```
BASE_URL=https://example.com
API_KEY=your_secret_api_key
USERNAME=testuser
PASSWORD=supersecret

```

Inside your project root, create a `.env` file and define your environment variables:<br>

---

### **3. Load `.env` Variables in Playwright Tests**

Modify your `playwright.config.ts` or `playwright.config.js` to load `.env` variables using `dotenv`:
```
import { defineConfig } from '@playwright/test';
import dotenv from 'dotenv';

// Load environment variables
dotenv.config();

export default defineConfig({
  use: {
    baseURL: process.env.BASE_URL, // Use env variable
    headless: true,
  },
});

```

---

### **4. Access Environment Variables in Tests**

In your test files, access the environment variables using `process.env`:

```
import { test, expect } from '@playwright/test';

test('Login test using environment variables', async ({ page }) => {
    await page.goto(process.env.BASE_URL!);
    await page.fill('#username', process.env.USERNAME!);
    await page.fill('#password', process.env.PASSWORD!);
    await page.click('#login');
    
    await expect(page).toHaveURL(process.env.BASE_URL + '/dashboard');
});

```
---

### **5. Using Different `.env` Files for Multiple Environments**

For different environments (e.g., development, staging, production), create multiple `.env` files:

- `.env.development`
- `.env.staging`
- `.env.production`

Then, load the specific file in `playwright.config.ts`:
```
import dotenv from 'dotenv';

// Load the correct .env file based on NODE_ENV
dotenv.config({ path: `.env.${process.env.NODE_ENV || 'development'}` });

console.log(`Running tests in ${process.env.NODE_ENV} mode`);

```

Run tests with different environments:


`NODE_ENV=staging npx playwright test`

---

### **6. Secure Your `.env` File**

- **Add `.env` to `.gitignore`** to prevent committing secrets to Git:

    `.env .env.*`
    
- **Use environment variables in CI/CD** instead of storing sensitive data in `.env` files.
    

---

### **7. Alternative: Use Playwright’s `test.use()`**

Instead of `.env` files, you can also pass environment-specific values using Playwright’s `test.use()`:

`test.use({ baseURL: process.env.BASE_URL });`



4.2 Data Driven Testing

 4.2.1 Data Driven Testing Using JSON File
 ### **Data-Driven Testing in Playwright using a JSON File**

Data-driven testing in Playwright allows you to run the same test with multiple sets of data stored in a JSON file. This approach helps validate different scenarios efficiently.

---

### **1. Create a JSON File for Test Data**

First, create a `data.json` file in your Playwright project:

```
[
  {
    "username": "user1",
    "password": "password123"
  },
  {
    "username": "user2",
    "password": "password456"
  }
]

```

---

### **2. Import and Use the JSON Data in Playwright Tests**

Modify your test file (e.g., `login.spec.ts`) to import and use the JSON data.

```
import { test, expect } from '@playwright/test';
import testData from './data.json'; // Import JSON data

testData.forEach(({ username, password }) => {
  test(`Login test with username: ${username}`, async ({ page }) => {
    await page.goto('https://example.com/login');

    await page.fill('#username', username);
    await page.fill('#password', password);
    await page.click('#login');

    // Check if login was successful
    await expect(page).toHaveURL('https://example.com/dashboard');
  });
});

```


---

### **3. Alternative: Using `test.describe()` for Multiple Data Sets**

If you have multiple test cases using the same data, you can use `test.describe()`:

```
test.describe('Login Tests', () => {
  for (const { username, password } of testData) {
    test(`Login test with username: ${username}`, async ({ page }) => {
      await page.goto('https://example.com/login');

      await page.fill('#username', username);
      await page.fill('#password', password);
      await page.click('#login');

      await expect(page).toHaveURL('https://example.com/dashboard');
    });
  }
});

```

---

### **4. Using `test.step()` for Better Debugging**

To improve test clarity, use `test.step()`:

```
testData.forEach(({ username, password }) => {
  test(`Login test for ${username}`, async ({ page }) => {
    await page.goto('https://example.com/login');

    await test.step('Enter credentials', async () => {
      await page.fill('#username', username);
      await page.fill('#password', password);
    });

    await test.step('Click login', async () => {
      await page.click('#login');
    });

    await test.step('Verify login success', async () => {
      await expect(page).toHaveURL('https://example.com/dashboard');
    });
  });
});

```

---

### **5. Running the Playwright Tests**

Run Playwright tests as usual:

`npx playwright test`

---

### **6. Using JSON Data in `test.use()` for Global Configurations**

If your JSON contains environment-specific configurations, you can use it in `playwright.config.ts`:

```
import { defineConfig } from '@playwright/test';
import configData from './config.json';

export default defineConfig({
  use: {
    baseURL: configData.baseURL
  },
});

```

---

### **7. Benefits of Using JSON for Data-Driven Testing**

✅ Easy to modify test data without changing test scripts  
✅ Allows running the same test for multiple data sets  
✅ Improves test maintainability






























---
ⓘ Metadata <br>
--
Title: My Note<br>
Tags:  #playwright #automation<br>
Author : Shubham Randive<br>

---

