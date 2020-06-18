# Events

## POST /event/create

> Request Example

```json
{
  "group_id": "3b01e0a9-6873-4aea-b361-6ee07b27feb4",
  "title": "Belajar yuks",
  "description": "Weekly study",
  "event_start": 1584525282422,
  "event_end": 1584525382422,
  "location": "San Francisco"
}
```

> Response Example

```json
{
  "event_id": "eb782268-ce50-4399-8aaa-5a17b8b4bc99",
  "group_id": "33521b88-8129-430f-a223-11c1d7b8609b",
  "title": "Belajar yuks 7",
  "description": "Weekly study 7",
  "event_start": 1584525282422,
  "event_end": 1584525382422,
  "location": "San Francisco",
  "created_at": 1592467831545,
  "updated_at": 0,
  "deleted_at": 0,
  "created_by": "1f35081e-afb3-4bd8-b132-4a9ecf36736f",
  "deleted_by": "-",
  "status": "joined",
  "user_event_id": "ce6d55fe-fe82-4dc7-b9e2-073f39b8315a",
  "members_count": 7,
  "members_list": []
}
```

### Description

Create new event

### Request Parameter

| Name        | Type   | Description                         | Required | Example value                        |
| ----------- | ------ | ----------------------------------- | -------- | ------------------------------------ |
| group_id    | String | Group ID which the event belongs to | True     | 3b01e0a9-6873-4aea-b361-6ee07b27feb4 |
| title       | String | Event title                         | True     | Belajar yuks                         |
| description | String | Event description                   | True     | Weekly study                         |
| event_start | Number | Event start time                    | True     | 1584525282422                        |
| event_end   | Number | Event end time                      | True     | 1584525382422                        |
| location    | String | Event location                      | True     | San Francisco                        |

## GET /event/:groupId

> Response Example

```json
[
  {
    "updated_at": 0,
    "created_at": 1589782085370,
    "deleted_at": 0,
    "deleted_by": "-",
    "created_by": "0afd8622-0494-40e2-bcfd-8a08a9a19c14",
    "event_end": 1584525382422,
    "event_id": "bb1e4a52-7f01-40be-91c4-bd371676df85",
    "description": "Weekly study 3",
    "event_start": 1584525282422,
    "group_id": "10e15565-7b50-4f18-9b55-7977c617bb9b",
    "title": "Belajar yuks 3",
    "status": "joined",
    "user_event_id": "11b26be6-d5c2-48b0-9882-c06a829daea7"
  },
  {
    "updated_at": 0,
    "created_at": 1589777415066,
    "deleted_at": 0,
    "deleted_by": "-",
    "created_by": "0afd8622-0494-40e2-bcfd-8a08a9a19c14",
    "event_end": 1584525382422,
    "event_id": "e57de692-3881-4325-94ef-e25fab64714e",
    "description": "Weekly study",
    "event_start": 1584525282422,
    "group_id": "10e15565-7b50-4f18-9b55-7977c617bb9b",
    "title": "Belajar yuks",
    "status": "joined",
    "user_event_id": "623998f3-8d3c-4d9f-9a5c-6766d8d3fc55"
  }
]
```

### Description

Get events list by group

## GET /event/detail/:eventId

> Response Example

```json
{
  "updated_at": 0,
  "created_at": 1589782085370,
  "deleted_at": 0,
  "deleted_by": "-",
  "created_by": "0afd8622-0494-40e2-bcfd-8a08a9a19c14",
  "event_end": 1584525382422,
  "event_id": "bb1e4a52-7f01-40be-91c4-bd371676df85",
  "description": "Weekly study 3",
  "event_start": 1584525282422,
  "group_id": "10e15565-7b50-4f18-9b55-7977c617bb9b",
  "title": "Belajar yuks 3",
  "members_count": 2,
  "members_list": [
    {
      "avatar": "https://users-photo-dev.s3.ap-northeast-1.amazonaws.com/uploads/1f35081e-afb3-4bd8-b132-4a9ecf36736f-1589002551709.jpg",
      "login": "Email",
      "user_id": "1f35081e-afb3-4bd8-b132-4a9ecf36736f",
      "available_start_time": "04:00",
      "created_at": 1585094292456,
      "available_end_time": "21:00",
      "role": "User",
      "available_days": ["Sun", "Mon", "Tue", "Wed", "Thu"],
      "username": "diare2029",
      "email": "diare@mail.com",
      "name": "Diarrhea",
      "status": "invited"
    },
    {
      "avatar": "-",
      "login": "Email",
      "user_id": "0afd8622-0494-40e2-bcfd-8a08a9a19c14",
      "available_start_time": "00:00",
      "created_at": 1585274478868,
      "available_end_time": "23:30",
      "role": "User",
      "available_days": ["Sun"],
      "username": "corona0606",
      "email": "corona@mail.com",
      "name": "corona penyakit 2",
      "status": "joined"
    }
  ]
}
```

### Description

Get event detail by event id

## GET /event/me

> Response Example

```json
[
  {
    "updated_at": 0,
    "created_at": 1589782085370,
    "deleted_at": 0,
    "deleted_by": "-",
    "created_by": "0afd8622-0494-40e2-bcfd-8a08a9a19c14",
    "event_end": 1584525382422,
    "event_id": "bb1e4a52-7f01-40be-91c4-bd371676df85",
    "description": "Weekly study 3",
    "event_start": 1584525282422,
    "group_id": "10e15565-7b50-4f18-9b55-7977c617bb9b",
    "title": "Belajar yuks 3",
    "status": "joined"
  },
  {
    "updated_at": 0,
    "created_at": 1589777415066,
    "deleted_at": 0,
    "deleted_by": "-",
    "created_by": "0afd8622-0494-40e2-bcfd-8a08a9a19c14",
    "event_end": 1584525382422,
    "event_id": "e57de692-3881-4325-94ef-e25fab64714e",
    "description": "Weekly study",
    "event_start": 1584525282422,
    "group_id": "10e15565-7b50-4f18-9b55-7977c617bb9b",
    "title": "Belajar yuks",
    "status": "invited"
  }
]
```

### Description

Get my events

## POST /event/delete

> Request Example

```json
{
  "event_id": "fe8a5876-0c42-4ddd-9e31-f4251715ce41"
}
```

> Response Example

```json
{
  "event_id": "fe8a5876-0c42-4ddd-9e31-f4251715ce41",
  "group_id": "3b01e0a9-6873-4aea-b361-6ee07b27feb4",
  "title": "Belajar yuks",
  "description": "Weekly study",
  "event_start": 1584525282422,
  "event_end": 1584525382422,
  "location": "San Francisco",
  "created_at": 1584525282422,
  "created_by": "1d0263e7-2015-458c-b29f-801fee73a393",
  "updated_at": 0,
  "updated_by": "-",
  "deleted_at": 1584525282422,
  "deleted_by": "1d0263e7-2015-458c-b29f-801fee73a393"
}
```

### Description

Delete an event

### Request Parameter

| Name     | Type   | Description        | Required | Example value                        |
| -------- | ------ | ------------------ | -------- | ------------------------------------ |
| event_id | String | Event ID to delete | True     | fe8a5876-0c42-4ddd-9e31-f4251715ce41 |

## POST /event/sync

> Request Example

```json
{
  "events": [
    {
      "event_id": "1b2a637c-73cf-49f4-9079-b35aad0f5ef1",
      "title": "My personal event 2",
      "description": "Test personal event 2",
      "event_start": 1587970800000,
      "event_end": 1587974400000
    },
    {
      "event_id": "6d1c2464-a9fb-4189-889a-96f96e0d8fa9",
      "title": "My personal event 3",
      "description": "Test personal event 3",
      "event_start": 1587970800000,
      "event_end": 1587974400000
    }
  ]
}
```

> Response Example

```json
{
  "success": "true"
}
```

### Description

Sync user personal calendar to Floo app. Note that these events will just be used to calculate user's free time and will not be shown in the app

### Request Parameters

Request contains 1 field called `events` containing array with the following fields:

| Name        | Type   | Description                   | Required | Example value                        |
| ----------- | ------ | ----------------------------- | -------- | ------------------------------------ |
| event_id    | String | Event ID from user's calendar | True     | 1b2a637c-73cf-49f4-9079-b35aad0f5ef1 |
| title       | String | Event title                   | True     | My personal event 2                  |
| description | String | Event description             | True     | Test personal event 2                |
| event_start | Number | Event start time              | True     | 1584525282422                        |
| event_end   | Number | Event end time                | True     | 1584525382422                        |
