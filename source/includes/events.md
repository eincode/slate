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
    "location": "San Fransisco",
    "created_at": 1592465557048,
    "deleted_at": 0,
    "deleted_by": "-",
    "created_by": "1f35081e-afb3-4bd8-b132-4a9ecf36736f",
    "event_end": 1584525382422,
    "event_id": "a9be0d81-3aab-48f9-8e54-7f70adb595f2",
    "description": "Weekly study 5",
    "event_start": 1584525282422,
    "group_id": "33521b88-8129-430f-a223-11c1d7b8609b",
    "title": "Belajar yuks 5",
    "status": "joined",
    "user_event_id": "3d594840-fad5-4d00-91bf-ac696f595e48",
    "member_count": 7,
    "member_list": []
  },
  {
    "updated_at": 0,
    "location": "San Francisco",
    "created_at": 1592467831545,
    "deleted_at": 0,
    "deleted_by": "-",
    "created_by": "1f35081e-afb3-4bd8-b132-4a9ecf36736f",
    "event_end": 1584525382422,
    "event_id": "eb782268-ce50-4399-8aaa-5a17b8b4bc99",
    "description": "Weekly study 7",
    "event_start": 1584525282422,
    "group_id": "33521b88-8129-430f-a223-11c1d7b8609b",
    "title": "Belajar yuks 7",
    "status": "joined",
    "user_event_id": "ce6d55fe-fe82-4dc7-b9e2-073f39b8315a",
    "member_count": 7,
    "member_list": []
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
  "location": "San Fransisco",
  "created_at": 1592465557048,
  "deleted_at": 0,
  "deleted_by": "-",
  "created_by": "1f35081e-afb3-4bd8-b132-4a9ecf36736f",
  "event_end": 1584525382422,
  "event_id": "a9be0d81-3aab-48f9-8e54-7f70adb595f2",
  "description": "Weekly study 5",
  "event_start": 1584525282422,
  "group_id": "33521b88-8129-430f-a223-11c1d7b8609b",
  "title": "Belajar yuks 5",
  "status": "joined",
  "user_event_id": "3d594840-fad5-4d00-91bf-ac696f595e48",
  "members_count": 7,
  "members_list": [
    {
      "avatar": "-",
      "login": "Email",
      "user_id": "5db31fba-1d1d-4b88-98eb-153532675656",
      "available_start_time": "01:00",
      "created_at": 1585274325214,
      "available_end_time": "23:00",
      "role": "User",
      "available_days": ["Mon"],
      "username": "sars1216",
      "email": "sars@mail.com",
      "name": "sars virus",
      "status": "invited"
    },
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
    "location": "San Fransisco",
    "created_at": 1592465557048,
    "deleted_at": 0,
    "deleted_by": "-",
    "created_by": "1f35081e-afb3-4bd8-b132-4a9ecf36736f",
    "event_end": 1584525382422,
    "event_id": "a9be0d81-3aab-48f9-8e54-7f70adb595f2",
    "description": "Weekly study 5",
    "event_start": 1584525282422,
    "group_id": "33521b88-8129-430f-a223-11c1d7b8609b",
    "title": "Belajar yuks 5",
    "status": "joined",
    "user_event_id": "3d594840-fad5-4d00-91bf-ac696f595e48",
    "member_list": [],
    "member_count": 7
  },
  {
    "updated_at": 0,
    "location": "San Fransisco",
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
    "status": "invited",
    "user_event_id": "b9552f75-de1c-4975-9aee-1a7544ab9e7e",
    "member_list": [],
    "member_count": 1
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

## GET /event/suggest-revamp

> Response Example

```json
[
  {
    "startTime": 1593403200000,
    "startTimeHumanized": "Monday 29 June 2020 04:00",
    "endTime": 1593464400000,
    "endTimeHumanized": "Monday 29 June 2020 21:00",
    "ableUsers": {
      "availableUserCount": 2,
      "ableUserIds": [
        "1f35081e-afb3-4bd8-b132-4a9ecf36736f",
        "b0751348-8b39-41bc-a26a-c5bcf28195de"
      ]
    }
  },
  {
    "startTime": 1593489600000,
    "startTimeHumanized": "Tuesday 30 June 2020 04:00",
    "endTime": 1593492305383,
    "endTimeHumanized": "Tuesday 30 June 2020 04:45",
    "ableUsers": {
      "availableUserCount": 2,
      "ableUserIds": [
        "1f35081e-afb3-4bd8-b132-4a9ecf36736f",
        "b0751348-8b39-41bc-a26a-c5bcf28195de"
      ]
    }
  }
]
```

### Request queries

| Name      | Type   | Description                                          | Required | Example value                        |
| --------- | ------ | ---------------------------------------------------- | -------- | ------------------------------------ |
| startTime | Number | Start time range to sugggest                         | True     | 1590944400000                        |
| endTime   | Number | End time range to suggest                            | True     | 1591030800000                        |
| groupId   | String | Group ID to create event                             | True     | 2d303746-cd62-44fb-9e6c-624785a8d0a8 |

### Example full link request

https://iacr9wz5kh.execute-api.ap-northeast-1.amazonaws.com/staging/event/suggest-revamp?startTime=1593450000000&endTime=1593622800000&groupId=2d303746-cd62-44fb-9e6c-624785a8d0a8

## GET /event/suggest (deprecated, see GET /event/suggest-revamp)

> Response Example

```json
[
  {
    "startTime": 1591009200000,
    "endTime": 1591030800000,
    "ableUserCount": 2,
    "ableUserIds": [
      "1f35081e-afb3-4bd8-b132-4a9ecf36736f",
      "b0751348-8b39-41bc-a26a-c5bcf28195de"
    ]
  },
  {
    "startTime": 1591003800000,
    "endTime": 1591025400000,
    "ableUserCount": 2,
    "ableUserIds": [
      "1f35081e-afb3-4bd8-b132-4a9ecf36736f",
      "b0751348-8b39-41bc-a26a-c5bcf28195de"
    ]
  },
  {
    "startTime": 1590998400000,
    "endTime": 1591020000000,
    "ableUserCount": 2,
    "ableUserIds": [
      "1f35081e-afb3-4bd8-b132-4a9ecf36736f",
      "b0751348-8b39-41bc-a26a-c5bcf28195de"
    ]
  }
]
```

### Request queries

| Name      | Type   | Description                                          | Required | Example value                        |
| --------- | ------ | ---------------------------------------------------- | -------- | ------------------------------------ |
| startTime | Number | Start time range to sugggest                         | True     | 1590944400000                        |
| endTime   | Number | End time range to suggest                            | True     | 1591030800000                        |
| groupId   | String | Group ID to create event                             | True     | 2d303746-cd62-44fb-9e6c-624785a8d0a8 |
| duration  | String | Event duration (in minutes) must have `minutes` word | True     | 60 minutes                           |

### Example full link request

https://iacr9wz5kh.execute-api.ap-northeast-1.amazonaws.com/staging/event/suggest?startTime=1590944400000&endTime=1591030800000&groupId=2d303746-cd62-44fb-9e6c-624785a8d0a8&duration=60%20minutes

## POST /event/respond

> Request Example

```json
{
  "user_event_id": "623998f3-8d3c-4d9f-9a5c-6766d8d3fc55",
  "status": "joined"
}
```

> Response Example

```json
{
  "event_id": "e57de692-3881-4325-94ef-e25fab64714e",
  "user_id": "0afd8622-0494-40e2-bcfd-8a08a9a19c14",
  "status": "joined",
  "user_event_id": "623998f3-8d3c-4d9f-9a5c-6766d8d3fc55"
}
```

### Description

Respond to event invitation

### Request Parameter

| Name          | Type   | Description                 | Required | Example value                        |
| ------------- | ------ | --------------------------- | -------- | ------------------------------------ |
| user_event_id | String | User Event ID to respond to | True     | 623998f3-8d3c-4d9f-9a5c-6766d8d3fc55 |
| status        | String | Respond                     | True     | `joined` or `declined`               |
