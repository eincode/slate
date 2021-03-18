# User

## User Registration Flow

### Registration

User needs to be registered first before they can use the app

### Auth Requirements

After login, the client needs to include token in `Authorization` field in the header with value of `Bearer {TOKEN}` to be able to verify the user authenticity

## POST /api/auth/login

> Request Example

```json
{
  "email": "test+2@example.com",
  "password": "somePassword"
}
```

> Response Example

```json
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJfaWQiOjIsImVtYWlsIjoidGVzdCsyQGV4YW1wbGUuY29tIiwiaWF0IjoxNjE2MDM4ODg0fQ._QwfGpTiStsmrXxg-_bwDEQeTmXWoCgev2k4RDVrINk"
}
```

### Definition

Login using email and password

### Request Parameter

| Name     | Type   | Description   | Required | Example Value    |
| -------- | ------ | ------------- | -------- | ---------------- |
| email    | String | User email    | True     | test@example.com |
| password | String | User password | True     | somePassword     |

## POST /api/auth/register

> Request Example

```json
{
  "email": "test+3@example.com",
  "password": "somePassword",
  "confirmationPassword": "somePassword"
}
```

> Response Example

```json
{
  "email": "test+4@example.com",
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJfaWQiOjE5LCJlbWFpbCI6InRlc3QrNEBleGFtcGxlLmNvbSIsImlhdCI6MTYxNjAzNDQ4NH0.aZ04bGvygTM36WVd9s_skPedV0nxEadp7M6C2mvE5Ck"
}
```

### Definition

Register new user

### Request Parameter

| Name                 | Type   | Description           | Required | Example value      |
| -------------------- | ------ | --------------------- | -------- | ------------------ |
| email                | String | User email            | True     | test+4@example.com |
| password             | String | User password         | True     | somePassword       |
| confirmationPassword | String | Confirmation Password | True     | somePassword       |

## POST /api/users/update-role

> Request Example

```json
{
  "role": "SELLER"
}
```

> Response Example

```json
{
  "id": 2,
  "email": "test+2@example.com",
  "role": "SELLER"
}
```

### Definition

After register, user must update their role using above endpoint

### Request Parameter

| Name | Type   | Description | Required | Example Value       |
| ---- | ------ | ----------- | -------- | ------------------- |
| role | String | User role   | True     | `SELLER` or `BUYER` |

## GET /api/users/me

> Response Example

```json
{
  "user": {
    "_id": "07514458-b24a-41aa-b924-262eb2486f74",
    "email": "test+2@example.com",
    "iat": 1615791586
  }
}
```

### Definition

Get my profile