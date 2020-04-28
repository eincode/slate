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
  "deleted_at": 0,
  "deleted_by": "-"
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
    "deleted_at": 0,
    "deleted_by": "-"
  }
]
```

### Description

Get events list by group

## GET /event/me

> Response Example

```json
[
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
    "deleted_at": 0,
    "deleted_by": "-"
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
