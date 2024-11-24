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

---

