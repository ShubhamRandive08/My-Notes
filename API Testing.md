- [API](RESTFUL_API) stands for application programming interface
- It is a set of rules and protocols that defines how 2 software programs or systems can communicate with each other.
- API acts as intermediary between 2 systems allows them to exchange data and functionality.

![](/Image/api_test.png)

##### Why API testing is required ?
- API testing is crucial for ensuring the smooth functioning and overall quality of web applications that rely on Application Programming Interface ( APIs )
- It checks if the API delivers the correct data in the expected format when provided with valid inputs
- API Testing also involves invalid inputs to ensure the API handles errors gracefully and returns appropriate messages.

Rest API : 
- Most common API's are Rest API's
- Rest provide some rules and regulation to create API.
- Playwright can be used to get access to the REST API of your application.

##### BaseURL : 
- The base URL ( Uniform recourse locator ) is the starting point for the accessing the API's resources. The base URL typically includes the protocols. ( eg. HTTP or HTTPS ) domain name and optionally a version.

Ex,

```API
https://api.thecat.com/v1/

https://testful-booker.herokuapp.com/
```


##### Resources : 
- Resources refers to a specific endpoint collection of data within the REST API.
Ex,
```
https://api.thecatapi.cpm/v1/images/
https://api.thecatapi.cpm/v1/breeds/
https://restful-booker.herokuapp.com/booking/
```

##### Path parameters :
- path parameters are variables within the path of a URL that are used to identify specific resources or elements.
Ex,
```
https://api-thecatapi.com/v1/images/{ imageID } // Main syntax
https://api-thecatapi.com/v1/images/BkiEnN3pG // Example
```

In above example BkiEnN3pG is the value of the imageID.

Ex 2.
```
https://testful-booker.herokuapp.com/booking/{id} // main syntax
https://testful-booker.herokuaap.com/booking/2 // example
```

In above example 2 is the id of ther booking

##### Sub resource and its path parameters : 
- In RESTFU API design, resource can have hierarchical relationships, where one resouce may be considered a sub-resource of another. 
Ex,
In a blogging API, a blog post resource might have 
```
https://api.thecatapi.com/v1/images//images/{ image id }/breeds/{ breed id}

https://api.thecatapi.com/v1/images/search
```

##### Query parameter :
- Query parameter are additional parameters added to the end of a URL that provide supplementary information to a server when making a request. They are typically used to filter. sort, paginate, or customize the response data returned by the server.

```
https:api.thecatapi.com/v1//images/?kunur = 10
https:api.thecatapi.com/v1//images/?kunur = 10&page = 0&order = DESC.
``` 

##### End Point : 
- Endpoint are the URL's that represent specific resources or services in a web application or API.
Ex,

```
BaseURL + Resour + Query / Path Parameters
```

##### Header : 
- Headers are additional information sent along with an HTTP  request or response. Headers provide the metadata about the request  or response such as the content type , authentication credentials and more.

##### Body :
- In REST API design the `body` refers to the payload of an HTTP request or response. It contains the data being sent from the client to the server in a request ( i.e. Request body ) or from the server to the client in a response ( i.e Response body )

##### HTTP Methods : 
- HTTP methods are used to define the actions or operations that can be performed on resources. ( CRUD Operations )
- POST - Used to create new resources on the server. ( C )
- GET - Used to retrieve data from the server. ( R )
- PUT - Used to update existing resources on the server. ( U )
- DELETE - Used to remove the resources from the server ( D )

##### Status Code : 
- Status code are standardized numerical codes returned in the HTTP response header to include the outcome of a client's requests to the server.
- Here are a few command status code in RESTful API's
     - 200 ( OK ) : The request was successful
     - 201 ( Created ) : The request has been fulfilled. and a new resource has been created.
     - 400 ( Bad Request ) : The request could not be understood by the server due to malformed syntax or other client-side errors.
     - 401 ( Unauthorized ) : The request requires authentication and the client's credential's are missing or invalid.
     - 404 ( Not Found ) : The requested resource could not fount on the server
     - 500 ( Internal Server error ) : The server encountered and unexpected condition that prevented that prevented it from fulfilling the request.


#### My Personal JWT Authentication Notes :
- Firstly we should create the auth token and then create the method to verify that token 

Ex,

```TS
// This endpoint for the get create the access token 
app.post('/getToken', [], (req,res) => {
    const {key} = req.body
    const token = jwt.sign({key},'super-secret', {expiresIn : '24h'}) // Specificaly this method can create the JWT token
    res.send({token})
})

// This method for verify the given access token

async function auth(req,res,next) {
    try{
        const token = req.headers.authorization.replace('Bearer ', '')
        await jwt.verify(token, 'super-secret') // Specificly this method can verifyt the access token should be correct or valid 
        req.token = token
        next() // This method process the all next process in well condition
    }catch(err){
        res.status(401).send({error : 'Please authenticate'})
    }
}
```


#### Note : Firstly we also check the API with API testing tools like Postman, Bruno, ThunderClient extension.

##### Get Call : 
- A GET call in an API is a specific type of HTTP request method used to retrieve data from a server 
- When you make a GET call, you are essentially asking the server for information. The server responds by sending back the requested data in the response body.
- The data format can vary depending on the API, but common formats include JSON and XML ( Extensible Markup Language )

Components to use - 
- BaseURL - Resource + Query and / or Path Parameter
- Header ( if required ie. Content-Type, Authorization ) 

4 Ways to provide baseURL
- With HTTP method
- By using request context in Test block
- By using request context in with beforeAll
- In Playwright.config.file
- In .env file 

Ex,

```TS
import { test, request } from "@playwright/test";

test.describe("API testing", async () => {
  let reqContext2;
  test.beforeAll("Before All", async () => {
    reqContext2 = await request.newContext({
      baseURL: "http://localhost:3000",
    });
  });

  test("API request GET practice", async ({ request }) => {
    const res = await request.get("http://localhost:3000/studData"); // This is the 1st method the fire the api request with base URL
    console.log(await res.json());
  });

  test("API call", async () => {
    const reqContext = await request.newContext({
      // This is method 2nd to fire request with base URL separeted
      baseURL: "http://localhost:3000",
      extraHTTPHeaders : {
        'Content-Type' : 'application/json'
      }
    });
    
    const res1 = await reqContext.get("/studData");
    console.log(await res1.json());
  });
  
  test("API request GET practice 3", async () => {
    const res = await reqContext2.get("http://localhost:3000/studData"); // This is the 3rd method to call the api wiht the store the base URL into the beforeAll hooks
    console.log(await res.json());
  });
  test("API request GET practice 4", async ({ request }) => {
    const res = await request.get(`${process.env.API_BASE_URL}/studData`,{
      headers : {
      'Content-Type' : 'application/json' // This is optional
      }
    }); // This is the 4th method to call the api with store the base URL into the .env file
    console.log(await res.json());
  });
});
```

##### If we want the sent the query parameters values then we use params : { } syntax

Ex,

```TS
test('API', async ({request}) => {
	const rs = await request.get('http://localhost:3000/records', {
		params : { // This is the main step
			fname : "Shubh",
			lname : "Randive"
		}
	})
})
```


##### For assertion we can use the `expect()` method 
Ex,

```TS
test('Make get call with payload', async ({request}) =>{
        const rs = await request.get('http://localhost:3000/studDataOnId/43')
        await expect(rs.status()).toBe(200) // Checks the status
        await expect(rs.ok()).toBeTruthy() // Checks the status code
        const jsonRes = await rs.json();
        expect(jsonRes.studData[0].fname).toEqual('teststudent1') // Checks the specific field
        console.log(await rs.json())
    })
```
##### NOTE : Demo API Web - restful-booker.herokuapp.com/apidoc/index.html

  `The curl command also used for make the API call with the help of the cammand line interface ( CLI )`

```
curl -i https://restful-booker.herokuapp.com/booking
```


#### POST Call :
- A POST call in an API refers to a specific type of HTTP request method used to send data to a server.
- POST requests are primarily used to create or update data on the server.
- When you make a POST call, you send data along with the request body. This data is usually formatted in a structured way, such as JSON or XML ( Extensible Markup Language )

###### Components to use :
- BaseURL + Resource
- Header ( if required )
- Body ( data )

##### In playwright, making the POST call we need to pass the payload we use `data` key for passing the payload to the URL.

Ex,

```TS
test('API', async ({request}) => {
	await request.post('http://localhost:3000/insertStaff, {
		data : { // This is the main step for making the post call
			"tname" : "shubh",
			"email" : "shubh@gmail.com",
			"username" : "shubh1617",
			"password" : "abc@03"
		}
	})
})
```

Playwright example 
Ex,
```TS
// Write the test case for the make a post call
import {test, expect} from '@playwright/test'

import { request } from 'http'
test.describe('API testing', async () =>{

    test('POST method in Playwright', async ({request}) =>{
        const rs  = await request.post('http://localhost:3000/insertStaff', {
            data : {
                "tname": "test",
                "email": "test3@gmail.com",
                "username": "test",
                "password": "test"
            }
        })
        const jsonRes = await rs.json();
        console.log(jsonRes)
    })
})
```






---
ⓘ Metadata <br>
---
Title: My Note<br>
Tags:   #apiTesting #notes  #TypeScript<br>

Author : Shubham Randive<br>

---
