- API stands for application programming interface
- It is a set of rules and protocols that defines how 2 software programs or systems can communicate with each other.
- API acts as intermediary between 2 systems allows them to exchange data and functionality.

![](/Image/api_test.png)

Rest API : 
- Most common API's are Rest API's
- Rest provide some rules and regulation to create API.
- Playwright can be used to get access to the REST API of your application.

##### BaseURL : The base URL ( Uniform recourse locator ) is the starting point for the accessing the API's resources. The base URL typically includes the protocols. ( eg. HTTP or HTTPS ) domain name and optionally a version.

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

