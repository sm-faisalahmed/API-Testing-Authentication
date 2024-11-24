# API-Testing-Authentication
This document explains the **three types of API authentication** and demonstrates how to test **REST API requests** (`GET`, `POST`, `PUT`, and `DELETE`) using **Postman**. 

---

## Types of API Authentication

### 1. **Basic Authentication**
Basic Authentication sends a username and password in each request, typically encoded in Base64. It’s easy to implement but less secure unless used with HTTPS.
#### Steps to Use Basic Authentication in Postman:
* Open Postman and select your API request (e.g., GET, POST).
* Go to the Authorization tab.
* Select Basic Auth from the dropdown.
* Enter your Username and Password.
* Postman will automatically generate the Authorization header with the value.
* Send the request.
#### Example: [Postman API - Basic Auth](https://api.postman.com/collections/27777291-57f9c0cc-33a6-47b8-9bf5-ad2070d0297a?access_key=PMAT-01JDF9R3YR588YHFXHZRJVYRX0)
#### Example of postman basic auth:
![Postman basic auth](image%20forder/Basic-Auth.png)
### 2. **Token-Based Authentication**
In Token-Based Authentication, a client authenticates once and receives a token (e.g., JWT). This token is included in subsequent requests for authorization.
#### Steps to Use Token-Based Authentication in Postman:
* Perform a login request to the API if required (e.g., a POST request to /login) and retrieve the token from the response.
* Go to the Authorization tab.
* Select Bearer Token from the dropdown.
* Enter the token in the Token field.
* Postman will automatically include the token in the Authorization header.
* Send the request.
#### Example: [Postman API - API Key Auth](https://api.postman.com/collections/27777291-ab639b66-318f-4009-9548-32c44b705d75?access_key=PMAT-01JDFB5ACBDK6V1XDQETFGEZD)
#### Example of Nasa API Key:
![Postman basic auth](image%20forder/API-key.png)
### 3. **OAuth 2.0**
OAuth 2.0 allows third-party applications to access resources without exposing user credentials. It involves obtaining and using an access token.

#### Steps to Use OAuth 2.0 in Postman:
* Go to the Authorization tab.
* Select OAuth 2.0 from the dropdown.
* Click Get New Access Token and fill in the details:
* Token Name: A descriptive name for the token.
* Grant Type: Choose the OAuth grant type (e.g., Authorization Code, Client Credentials, etc.).
* Access Token URL: URL to get the access token (provided by the API documentation).
* Client ID: Your client ID (provided by the API provider).
* Client Secret: Your client secret (provided by the API provider).
* Scope: The permissions you’re requesting.
* State: (Optional) A unique string for identifying the session.
* Client Authentication: Choose whether to send the client credentials in the body or header.
* Click Request Token. Postman will handle the token exchange.
* Once retrieved, select the token and click Use Token.
* Postman will add the Authorization header automatically:
* Send the request.
#### Example of Spotify Auth 2.0:
![Spotify API](image%20forder/Auth2.0.png)

---

# Testing REST API Requests with Postman
Postman is a powerful tool for testing and interacting with REST APIs. Here’s how you can use it to test common requests:

#### [API Documentation](http://dummy.restapiexample.com/)
### 1. GET Request
Used to retrieve data, such as fetching a list of users or specific resource details.

Example Endpoint:
GET: https://dummy.restapiexample.com/api/v1/employees/1

#### Result Body: 
```json
 {
"status": "success",
"data": {
"id": "1",
"employee_name": "Tiger Nixon",
"employee_salary": "320800",
"employee_age": "61",
"profile_image": ""
}
}
```

#### Steps in Postman:

* Select GET as the request method.
* Enter the API URL.
*Add headers if required (e.g., Authorization).

### 2. POST Request
Used to create new resources.

Example Endpoint:
POST: /users](https://dummy.restapiexample.com/api/v1/create)

#### Body:
```json
{"name":"test","salary":"123","age":"23"}
```
#### Result Body:
```json
{
    "status": "success",
    "data": {
        "name": "test",
        "salary": "123",
        "age": "23",
        "id": 25
    }
}
```

#### Steps in Postman:
* Select POST as the request method.
* Enter the API URL.
* Add the JSON body in the Body tab.
* Add headers like Content-Type: application/json.
* 
### 3. PUT Request
Used to update existing resources.

Example Endpoint:
PUT: https://dummy.restapiexample.com/api/v1/update/21

#### Body: 
```json
	{"name":"test","salary":"123","age":"23"}
```
#### Result Body:
```json
{
    "status": "success",
    "data": {
        "name": "test",
        "salary": "123",
        "age": "23",
        "id": 25
    }
}
```
#### Steps in Postman:

* Select PUT as the request method.
* Enter the API URL (replace {id} with the resource ID).
* Add the JSON body with updated data.
### 4. DELETE Request
Used to delete resources.

Example Endpoint:

DELETE: https://dummy.restapiexample.com/api/v1/delete/2

#### Result Body:
```json
{
    "status": "success",
    "message": "successfully! deleted Records"
}
```
#### Steps in Postman:

* Select DELETE as the request method.
* Enter the API URL (replace {id} with the resource ID).
