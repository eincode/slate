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
  "available_start_time": "00:00",
  "available_end_time": "23:30",
  "login": "Email",
  "name": "corona penyakit",
  "available_days": ["Mon", "Tue", "Wed"]
}
```

> Response Example

```json
{
  "avatar": "-",
  "login": "Email",
  "user_id": "0afd8622-0494-40e2-bcfd-8a08a9a19c14",
  "available_start_time": "00:00",
  "created_at": 1585274478868,
  "available_end_time": "23:30",
  "role": "User",
  "available_days": ["Mon", "Tue", "Wed"],
  "username": "corona0606",
  "email": "corona@mail.com",
  "name": "corona penyakit"
}
```

### Definition

Update user profile

### Request Parameter

| Name                 | Type   | Description               | Required | Example value                                            |
| -------------------- | ------ | ------------------------- | -------- | -------------------------------------------------------- |
| available_start_time | String | User available start time | True     | 12:00                                                    |
| available_end_time   | String | User available end time   | True     | 17:00                                                    |
| name                 | String | User name                 | True     | John                                                     |
| login                | String | User login type           | True     | `Google`, `Facebook`, `Email`                            |
| available_days       | Array  | User available days       | True     | Array of `Sun`, `Mon`, `Tue`, `Wed`, `Thu`, `Fri`, `Sat` |

## GET /users/me

> Response Example

```json
{
  "avatar": "-",
  "login": "Email",
  "user_id": "0afd8622-0494-40e2-bcfd-8a08a9a19c14",
  "available_start_time": "00:00",
  "created_at": 1585274478868,
  "available_end_time": "23:30",
  "role": "User",
  "available_days": ["Mon", "Tue", "Wed"],
  "username": "corona0606",
  "email": "corona@mail.com",
  "name": "corona penyakit"
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

## POST /users/search

> Request Example

```json
{
  "username": "anjing1234"
}
```

> Response Example

```json
[
  {
    "avatar": "-",
    "login": "Google",
    "user_id": "1d0263e7-2015-458c-b29f-801fee73a393",
    "available_start_time": "09:00",
    "created_at": 1583731912113,
    "available_end_time": "21:00",
    "role": "User",
    "username": "anjing1234",
    "email": "anjing@gmail.com",
    "name": "Anjing"
  }
]
```

### Definition

Search user by exact username

### Request Parameter

| Name     | Type   | Description            | Required | Example value |
| -------- | ------ | ---------------------- | -------- | ------------- |
| username | String | Username to search for | True     | anjing        |

## POST /users/friend/search

> Request Example

```json
{
  "username": "anjing"
}
```

> Response Example

```json
[
  {
    "avatar": "-",
    "login": "Google",
    "user_id": "1d0263e7-2015-458c-b29f-801fee73a393",
    "available_start_time": "09:00",
    "created_at": 1583731912113,
    "available_end_time": "21:00",
    "role": "User",
    "username": "anjing1234",
    "email": "anjing@gmail.com",
    "name": "Anjing"
  }
]
```

### Definition

Search friend by username

### Request Parameter

| Name     | Type   | Description            | Required | Example value |
| -------- | ------ | ---------------------- | -------- | ------------- |
| username | String | Username to search for | True     | anjing        |

## GET /users/friends

> Response Example

```json
[
  {
    "avatar": "-",
    "login": "Google",
    "user_id": "1d0263e7-2015-458c-b29f-801fee73a393",
    "available_start_time": "09:00",
    "created_at": 1583731912113,
    "available_end_time": "21:00",
    "role": "User",
    "username": "anjing1234",
    "email": "anjing@gmail.com",
    "name": "Anjing"
  }
]
```

### Definition

Get users friends list

## POST /users/upload-ava

> Request Example

```json
{
  "image": "{{base64EncodedImage}}"
}
```

> Response Example

```json
{
  "avatar": "https://users-photo-dev.s3.ap-northeast-1.amazonaws.com/uploads/1d0263e7-2015-458c-b29f-801fee73a393.jpg",
  "login": "Google",
  "user_id": "1d0263e7-2015-458c-b29f-801fee73a393",
  "available_start_time": "09:00",
  "created_at": 1583731912113,
  "available_end_time": "21:00",
  "role": "User",
  "username": null,
  "email": "deras.hujan15@gmail.com",
  "name": "Hujan Deras"
}
```

### Definition

Upload user avatar

### Request Parameter

| Name  | Type   | Description          | Required | Example value              |
| ----- | ------ | -------------------- | -------- | -------------------------- |
| image | String | Base64 encoded image | True     | some-base-64-encoded-image |