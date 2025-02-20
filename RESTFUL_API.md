
##### What is RESTful API's ?
--- > A **RESTful API (Representational State Transfer API)** is an architectural style for designing networked applications. It uses the principles of HTTP to enable communication between a **client** (such as a web browser or mobile app) and a **server** (where data is stored). <br>
It is allow to communication between `Client` and `Server` with using standard HTTP methods like `GET, POST, PUT, DELETE, PATCH, HEAD, OPTION`
<br>
There have some key components like HTTP methods like GET, POST, PUT, DELETE, PATCH, HEAD, OPTION etc. Data format like JSON, XML, HTML, CVS etc. <br>

Importance of API's <br>
These are lot of importance of API's like Clear endpoint, HTTP methods, Data format, authentication, Light wight, Scalable, Error handling, etc.<br>

Disadvantages of API's<br>
These are some disadvantages like  security, integration issues , cost, Data overload <br>

HTTP methods used in API's <br>
These are some methods which are, <br>
1. `Get` - Retrieves the data from the server
2. `post` - Sends data to the server to create the new resource.
3. `put` - Update the an existing resource on the server
4. `delete` - Removes the resource from the server
5. `patch` - Partially updates an existing resource.
6. `option` - Describes the communication options for the target resource.
7. `head` - Retrieves the headers of a resource (without the body).<br>

What is difference between  `put` and `patch` methods<br>
### **PUT (Full Update)**

- **What it does**: The **PUT** method is used to update or replace the entire resource. If you send data using PUT, you typically need to send the **complete resource**, even if only part of it is being updated.
    
- **When to use**: Use PUT when you want to **replace** the resource entirely or update all the fields of a resource.
    
- **Example**:
    
    - You have a user with the following details:

        `{   "id": 1,   "name": "John",   "email": "john@example.com",   "age": 30 }`
        
    - You send a **PUT** request to update the user’s information, but you need to provide all the fields, even if you are only changing one field. For example:
 
        `{   "id": 1,   "name": "John Doe",   "email": "john.doe@example.com",   "age": 30 }`
        
- **Effect**: This will **replace the entire record**, even if only one field is changed.


### **PATCH (Partial Update)**

- **What it does**: The **PATCH** method is used to apply **partial updates** to a resource. With PATCH, you only need to send the **fields that are changing**, not the entire resource.
    
- **When to use**: Use PATCH when you want to update **only specific parts** of a resource.
    
- **Example**:
    
    - Using the same user data:
        
        `{   "id": 1,   "name": "John",   "email": "john@example.com",   "age": 30 }`
        
    - If you only want to update the **name**, you can send a **PATCH** request like this:
 
        `{   "name": "John Doe" }`
        
- **Effect**: This will **update only the specified field** (in this case, "name"), without changing the rest of the data.
    

### **Summary of the Difference:**

- **PUT**: Replaces the entire resource. You need to send all fields, even if only one needs to be updated.
- **PATCH**: Updates only the specific fields you want to change. You only send the data that’s being updated.

### Example Scenario:

- **PUT**: If you want to update all the details of a user's profile (e.g., name, email, and age), you would send a PUT request with all the details.
- **PATCH**: If you only want to update the user's **email**, you would use a PATCH request and only send the email field.<br>

#### **REST API Status Codes**

| Status Code | Meaning                                                                                           |     |
| ----------- | ------------------------------------------------------------------------------------------------- | --- |
| 100         | Continue - The server received the request headers and is waiting for the body                    |     |
| 101         | Switching Protocols – The server is switching protocols as requested by the client                |     |
| 102         | Processing – The request is being processed, but no response is available yet (WebDAV)            |     |
| 103         | - Early Hints – Used to preload resources before the final response.                              |     |
|             |                                                                                                   |     |
| 200         | OK – The request was successful                                                                   |     |
| 201         | Created – A new resource was successfully created.                                                |     |
| 202         | Accepted – The request has been accepted for processing but not completed                         |     |
| 203         | Non-Authoritative Information – Response metadata is from a different source.                     |     |
| 204         | No Content – The request was successful, but there is no content in the response.                 |     |
| 205         | Reset Content – The response instructs the client to reset the document view.                     |     |
| 206         | Partial Content – The server is delivering a portion of the resource (used for range requests).   |     |
| 207         | Multi-Status – Multiple status codes might be returned (WebDAV).                                  |     |
| 208         | Already Reported – The resource has already been reported in the current response.                |     |
| 226         | IM Used – The server has applied instance manipulations (Delta encoding).                         |     |
|             |                                                                                                   |     |
| 300         | Multiple Choices – There are multiple options for the resource.                                   |     |
| 301         | Moved Permanently – The resource has permanently moved to a new URL.                              |     |
| 302         | Found – The resource is temporarily located at a different URL.                                   |     |
| 303         | See Other – The client should fetch the resource from another URL (e.g., after a `POST` request). |     |
| 304         | Not Modified – The resource has not changed since the last request.                               |     |
| 305         | Use Proxy – The resource is available only through a proxy (deprecated).                          |     |
| 307         | Temporary Redirect – The request should be repeated with another URL (method remains unchanged).  |     |
| 308         | Permanent Redirect – The resource has moved permanently (like 301 but method remains unchanged).  |     |
|             |                                                                                                   |     |
| 400         | Bad Request – The request is invalid or malformed.                                                |     |
| 401         | Unauthorized – Authentication is required.                                                        |     |
| 402         | Payment Required – Reserved for future use.                                                       |     |
| 403         | - Forbidden – The client does not have permission to access the resource.                         |     |
| 404         | Not Found – The resource was not found.                                                           |     |
| 405         | Method Not Allowed – The HTTP method is not allowed for this resource                             |     |
| 406         | Not Acceptable – The requested format is not supported.                                           |     |
| 407         | Proxy Authentication Required – The client must authenticate with a proxy.                        |     |
|             |                                                                                                   |     |
| 500         | Internal Server Error – A generic error when something goes wrong on the server.                  |     |
| 501         | Not Implemented – The server does not support the request method.                                 |     |
| 502         | Bad Gateway – The server received an invalid response from an upstream server.                    |     |
| 503         | Service Unavailable – The server is temporarily unavailable.                                      |     |


---
ⓘ Metadata <br>
---
Title: My Note<br>
Tags:   #restfulApi #api<br>
Author : Shubham Randive<br>

---
