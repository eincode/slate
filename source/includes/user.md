# User

## User Registration Flow

### Cognito registration

User needs to be registered first through cognito in order to get that user's ID to be used in the request header. After user registration, user will be asked for their data needed in order to use Floo app. After the data is obtained, client will update the user details through the update endpoint below.

### After Cognito registration

After user is registered in Cognito, a Post Registration trigger will invoke the auto-user-registration function which will add said user to DynamoDb with values:

- User ID: User's ID provided by Cognito
- Email: User's cognito registered email
- Username: User's email before the `@` character appended with 4 digit random number

## POST /users/update

> Request Example

```json
{
  "available_start_time": "09:00",
  "available_end_time": "21:00",
  "avatar": "-",
  "name": "Hujan Deras",
  "login": "Email"
}
```

> Response Example

```json
{
  "avatar": "-",
  "login": "Google",
  "user_id": "1d0263e7-2015-458c-b29f-801fee73a393",
  "available_start_time": "09:00",
  "created_at": 1583731912113,
  "available_end_time": "21:00",
  "role": "User",
  "username": "deras.hujan154432",
  "email": "deras.hujan15@gmail.com",
  "name": "Hujan Deras"
}
```

### Definition

Update user profile

### Request Parameter

| Name                 | Type   | Description               | Required | Example value                 |
| -------------------- | ------ | ------------------------- | -------- | ----------------------------- |
| available_start_time | String | User available start time | True     | 12:00                         |
| available_end_time   | String | User available end time   | True     | 17:00                         |
| avatar               | String | User avatar image link    | True     | https://google.com/           |
| name                 | String | User name                 | True     | John                          |
| login                | String | User login type           | True     | `Google`, `Facebook`, `Email` |

## GET /users/me

> Response Example

```json
{
  "avatar": "-",
  "login": "Google",
  "user_id": "1d0263e7-2015-458c-b29f-801fee73a393",
  "available_start_time": "09:00",
  "created_at": 1583731912113,
  "available_end_time": "21:00",
  "role": "User",
  "username": "deras.hujan154432",
  "email": "deras.hujan15@gmail.com",
  "name": "Hujan Deras"
}
```

### Definition

Get my profile

## GET /users/:userId

> Response Example

```json
{
  "avatar": "-",
  "login": "Google",
  "user_id": "1d0263e7-2015-458c-b29f-801fee73a393",
  "available_start_time": "09:00",
  "created_at": 1583731912113,
  "available_end_time": "21:00",
  "role": "User",
  "username": "deras.hujan154432",
  "email": "deras.hujan15@gmail.com",
  "name": "Hujan Deras"
}
```

### Definition

Get user profile based on user ID
