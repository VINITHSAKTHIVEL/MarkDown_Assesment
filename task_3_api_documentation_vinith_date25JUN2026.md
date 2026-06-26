# User Management REST API Documentation

---

# Table of Contents

1. Login API.
    
2. Register API.
    
3. Get User API.
    

---

# Login API

## Endpoint Details

|Property|Value|
|---|---|
|Method|POST|
|Endpoint|`/api/login`|
|Description|Authenticates a user and returns an access token.|

## Request Headers

|Header|Value|
|---|---|
|Content-Type|application/json|

## Request Body

```json
{
  "email": "vinith7017@gmail.com.com",
  "password": "Vinith@123"
}
```

### Request Parameters

- **email**
    
    - Type: String
        
    - Required: Yes
        
    - Description: Registered email address
        
- **password**
    
    - Type: String
        
    - Required: Yes
        
    - Description: User password
        

## Success Response

**Status Code:** `200 OK`

```json
{
  "status": "success",
  "message": "Login successful",
  "token": "eyJhbGciOiJIUzI1NiIsInR5..."
}
```

## Error Responses

|Status Code|Description|
|---|---|
|400|Invalid request|
|401|Invalid email or password|
|500|Internal server error|

---

# Register API

## Endpoint Details

|Property|Value|
|---|---|
|Method|POST|
|Endpoint|`/api/register`|
|Description|Registers a new user.|

## Request Headers

|Header|Value|
|---|---|
|Content-Type|application/json|

## Request Body

```json
{
  "name": "Vinith",
  "email": "vinith7017@gmail.com",
  "password": "Vinith@123",
  "phone": "9751678054"
}
```

### Request Parameters

- **name**
    
    - Type: String
        
    - Required: Yes
        
- **email**
    
    - Type: String
        
    - Required: Yes
        
- **password**
    
    - Type: String
        
    - Required: Yes
        
- **phone**
    
    - Type: String
        
    - Required: Yes
        

## Success Response

**Status Code:** `201 Created`

```json
{
  "status": "success",
  "message": "User registered successfully"
}
```

## Error Responses

|Status Code|Description|
|---|---|
|400|Missing required fields|
|409|User already exists|
|500|Internal server error|

---

# Get User API

## Endpoint Details

|Property|Value|
|---|---|
|Method|GET|
|Endpoint|`/api/users/{id}`|
|Description|Retrieves user details by ID.|

## Request Headers

|Header|Value|
|---|---|
|Authorization|Bearer Token|
|Content-Type|application/json|

## Path Parameter

- **id**
    
    - Type: Integer
        
    - Required: Yes
        
    - Description: Unique user ID
        

## Success Response

**Status Code:** `200 OK`

```json
{
  "id": 101,
  "name": "Vinith",
  "email": "vinith7017@gmail.com",
  "phone": "9751678054"
}
```

## Error Responses

|Status Code|Description|
|---|---|
|401|Unauthorized access|
|404|User not found|
|500|Internal server error|

---

# HTTP Status Codes Used

|Code|Meaning|
|---|---|
|200|OK|
|201|Created|
|400|Bad Request|
|401|Unauthorized|
|404|Not Found|
|409|Conflict|
|500|Internal Server Error|
