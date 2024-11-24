# API-Testing-Authentication
This document explains the **three types of API authentication** and demonstrates how to test **REST API requests** (`GET`, `POST`, `PUT`, and `DELETE`) using **Postman**. 

---

## Types of API Authentication

### 1. **Basic Authentication**
Basic Authentication sends a username and password in each request, typically encoded in Base64. It’s easy to implement but less secure unless used with HTTPS.
* [Postman API](https://api.postman.com/collections/27777291-57f9c0cc-33a6-47b8-9bf5-ad2070d0297a?access_key=PMAT-01JDF9R3YR588YHFXHZRJVYRX0)
### 2. **Token-Based Authentication**
In Token-Based Authentication, a client authenticates once and receives a token (e.g., JWT). This token is included in subsequent requests for authorization.
### 3. **OAuth 2.0**
OAuth 2.0 allows third-party applications to access resources without exposing user credentials. It involves obtaining and using an access token.

#### Steps:
- Request an authorization code.
- Exchange the code for an access token.
- Use the token to access the API.
