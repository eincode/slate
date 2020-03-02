# User

## POST /user/create-user

> Request Example

```json
{
  "email": "renoputraprawira1@gmail.com",
  "login": "Google"
}
```

> Response Example

```json
{
  "UserData": {
    "available_end_time": "-",
    "available_start_time": "-",
    "avatar": "-",
    "created_at": "Sun, 09 Feb 2020 12:17:18 GMT",
    "deleted_at": "-",
    "email": "user@something.com",
    "login": "Google",
    "role": "User",
    "token": "testToken",
    "id": "9216020923976048",
    "username": "renoputraprawira2",
    "name": "-"
  }
}
```

### Definition

Register new user

### Request Parameter

| Name  | Type   | Description                | Required | Example value                 |
| ----- | ------ | -------------------------- | -------- | ----------------------------- |
| email | String | User email.                | True     | user@something.com            |
| login | String | User method of registering | True     | `Google`, `Facebook`, `Email` |

## GET /user/search?name={name}

> Response Example

```json
[
  {
    "Token": "SomeToken",
    "UserID": "user:9170156123719684",
    "Created_at": "Fri Jan 24 2020 07:29:15 GMT+0000 (Coordinated Universal Time)",
    "Deleted_at": "-",
    "Role": "User",
    "Available_End_Time": "12:00",
    "Avatar": "https://scontent-cgk1-1.xx.fbcdn.net/v/t1.0-1/p320x320/43650827_2486289771381006_1904738105089327104_o.jpg?_nc_cat=110&_nc_oc=AQmyOKA7leU4SBp8OtZD17b5mN_tt7a2IqeSI5rIp3xN9WVy43Owlz9YoyJmUlIAT00&_nc_ht=scontent-cgk1-1.xx&_nc_tp=1002&oh=c88e5d63df9690beedeab51a821e4c68&oe=5EA92999",
    "Available_Start_Time": "17:00",
    "UserName": "renopp",
    "Login": "Google",
    "Email": "renoputraprawira@gmail.com"
  }
]
```

### Definition

Search User

## POST /user/update?accessToken={accessToken}

> Request Example

```json
{
  "available_start_time": "12:00",
  "available_end_time": "18:00",
  "avatar": "-",
  "name": "test bisa ya"
}
```

> Response Example

```json
{
  "avatar": "-",
  "login": "Google",
  "available_start_time": "12:00",
  "created_at": "Sun, 09 Feb 2020 11:49:38 GMT",
  "deleted_at": "-",
  "token": "testToken",
  "role": "User",
  "available_end_time": "18:00",
  "username": "renopp123",
  "id": "123123",
  "email": "renoputraprawira1@gmail.com",
  "name": "test bisa ya"
}
```

### Definition

Update user profile

### Request Parameter

| Name                 | Type   | Description               | Required | Example value       |
| -------------------- | ------ | ------------------------- | -------- | ------------------- |
| available_start_time | String | User available start time | True     | 12:00               |
| available_end_time   | String | User available end time   | True     | 17:00               |
| avatar               | String | User avatar image link    | True     | https://google.com/ |
| name                 | String | User name                 | True     | John                |

## GET /user/single?userID={userID}

> Response Example

```json
{
  "Token": "SomeToken",
  "UserID": "user:9170156123719684",
  "Created_at": "Fri Jan 24 2020 07:29:15 GMT+0000 (Coordinated Universal Time)",
  "Deleted_at": "-",
  "Role": "User",
  "Available_End_Time": "12:00",
  "Avatar": "https://scontent-cgk1-1.xx.fbcdn.net/v/t1.0-1/p320x320/43650827_2486289771381006_1904738105089327104_o.jpg?_nc_cat=110&_nc_oc=AQmyOKA7leU4SBp8OtZD17b5mN_tt7a2IqeSI5rIp3xN9WVy43Owlz9YoyJmUlIAT00&_nc_ht=scontent-cgk1-1.xx&_nc_tp=1002&oh=c88e5d63df9690beedeab51a821e4c68&oe=5EA92999",
  "Available_Start_Time": "17:00",
  "UserName": "renopp",
  "Login": "Google",
  "Email": "renoputraprawira@gmail.com"
}
```

### Definition

Get user profile
