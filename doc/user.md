# USER API Spec

## Register User

Endpoint: POST /api/users

Request Body:

```json
{
  "username": "resna",
  "password": "rahasia",
  "name": "pangestu"
}
```

Response Body (Success) :

```json
{
  "data": {
    "username": "resna",
    "name": "pangestu"
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

Request Body:

```json
{
  "username": "resna",
  "password": "rahasia"
}
```

Response Body (Success) :

```json
{
  "data": {
    "username": "resna",
    "name": "pangestu",
    "token": "session_id_generated"
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

- authorization: token

Response Body (Success) :

```json
{
  "data": {
    "username": "resna",
    "name": "pangestu"
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

Headers:

- Authorization: token

Request Body:

```json
{
  "password": "rahasia",
  "name": "pangestu"
}
```

Response Body (Success) :

```json
{
  "data": {
    "username": "resna",
    "name": "pangestu"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Username already registered"
}
```

## Logout User

Endpoint: DELETE /api/users/current

Headers:

- Authorization: token

Response Body (Success) :

```json
{
  "data": true
}
```
