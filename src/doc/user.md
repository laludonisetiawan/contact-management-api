# User API Spec

## Register User

Endpoint: POST /api/users

Request Body :

```json
{
  "username": "laludonisetiawan",
  "password": "rahasia123"
}
```

Response Body (Sucess) :

```json
{
  "data": {
    "username": "laludonisetiawan",
    "name": "Lalu Doni Setiawan"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Username already registered"
}
```

## Login User

Endpoint: POST /api/users/login

Request Body :

```json
{
  "username": "laludonisetiawan",
  "password": "rahasia123"
}
```

Response Body (Sucess) :

```json
{
  "data" : {
    "username": "laludonisetiawan",
    "name"    : "Lalu Doni Setiawan"
    "token"   : "session_id_generated"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Username or password is wrong"
}
```

## Get User

Endpoint: GET /api/users/current

Headers :

- Authorization: token

Response Body (Sucess) :

```json
{
  "data": {
    "username": "laludonisetiawan",
    "name": "Lalu Doni Setiawan"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Unauthorized"
}
```

## Update User

Endpoint: PATCH /api/users/current

Headers :

- Authorization: token

Request Body :

```json
{
  "password": "rahasia123", // optional
  "name": "Lalu Doni Setiawan" // optional
}
```

Response Body (Sucess) :

```json
{
  "data": {
    "username": "laludonisetiawan",
    "name": "Lalu Doni Setiawan"
  }
}
```

## Logout User

Endpoint: DELETE /api/users/current

Headers :

- Authorization: token

Response Body (Sucess) :

```json
{
  "data": true
}
```
