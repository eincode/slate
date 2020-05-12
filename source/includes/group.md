# Group

## GET /group/:groupId

> Response Example

```json
{
  "avatar": "https://groups-photo-dev.s3.ap-northeast-1.amazonaws.com/uploads/10e15565-7b50-4f18-9b55-7977c617bb9b.jpg",
  "created_at": 1585289894877,
  "deleted_at": 0,
  "created_by": "1f35081e-afb3-4bd8-b132-4a9ecf36736f",
  "deleted_by": "-",
  "description": "-",
  "name": "Aku invite coronacok",
  "group_id": "10e15565-7b50-4f18-9b55-7977c617bb9b",
  "member_count": 1,
  "member_list": [
    {
      "avatar": "https://users-photo-dev.s3.ap-northeast-1.amazonaws.com/uploads/1f35081e-afb3-4bd8-b132-4a9ecf36736f-1589002551709.jpg",
      "login": "Email",
      "user_id": "1f35081e-afb3-4bd8-b132-4a9ecf36736f",
      "available_start_time": "04:00",
      "created_at": 1585094292456,
      "available_end_time": "21:00",
      "role": "admin",
      "available_days": [],
      "username": "diare2029",
      "email": "diare@mail.com",
      "name": "Diarrhea",
      "kicked_at": 0,
      "group_member_id": "0efce601-5c23-46af-a01a-8e4120e04bdb",
      "status": "joined",
      "invited_by": "1f35081e-afb3-4bd8-b132-4a9ecf36736f",
      "kicked_by": "-",
      "invited_at": 1585289894877,
      "group_id": "10e15565-7b50-4f18-9b55-7977c617bb9b"
    }
  ],
  "event_count": 1,
  "event_list": [
    {
      "updated_at": 0,
      "created_at": 1589257709345,
      "deleted_at": 0,
      "deleted_by": "-",
      "created_by": "0afd8622-0494-40e2-bcfd-8a08a9a19c14",
      "event_end": 1584525382422,
      "event_id": "44eedd79-06c8-4e83-944d-8e8881f5078b",
      "description": "Weekly study",
      "event_start": 1584525282422,
      "group_id": "10e15565-7b50-4f18-9b55-7977c617bb9b",
      "title": "Belajar yuks"
    }
  ]
}
```

### Description

Get Group by ID

## POST /group/update

> Request Example

```json
{
  "group_id": "3b01e0a9-6873-4aea-b361-6ee07b27feb4",
  "name": "Grup Belajar",
  "description": "Belajar kuy"
}
```

> Response Example

```json
{
  "created_at": 1584525282422,
  "description": "Belajar kuy",
  "created_by": "1d0263e7-2015-458c-b29f-801fee73a393",
  "name": "Grup Belajar",
  "group_id": "3b01e0a9-6873-4aea-b361-6ee07b27feb4",
  "deleted_by": "-",
  "deleted_at": 0,
  "avatar": "-"
}
```

### Description

Update group detail

### Request Parameter

| Name        | Type   | Description           | Required | Example value                        |
| ----------- | ------ | --------------------- | -------- | ------------------------------------ |
| group_id    | String | Group ID to update    | True     | 3b01e0a9-6873-4aea-b361-6ee07b27feb4 |
| name        | String | New group name        | True     | Grup Belajar                         |
| description | String | New group description | True     | Belajar kuy                          |

## POST /group/create

> Request Example

```json
{
  "name": "Grup belajar bareng",
  "description": "Yuk belajar bareng"
}
```

> Response Example

```json
{
  "group_id": "ccf60309-2f0a-40e6-b348-9021b1b57fa6",
  "name": "Grup belajar bareng",
  "description": "Yuk belajar bareng",
  "created_at": 1584533027596,
  "created_by": "1d0263e7-2015-458c-b29f-801fee73a393",
  "deleted_by": "-",
  "deleted_at": 0,
  "avatar": "-"
}
```

### Description

Create new Group

### Request Parameter

| Name        | Type   | Description           | Required | Example value       |
| ----------- | ------ | --------------------- | -------- | ------------------- |
| name        | String | New group name        | True     | Grup belajar bareng |
| description | String | New group description | True     | Yuk belajar bareng  |

## POST /group/invite

> Request Example

```json
{
  "group_id": "ccf60309-2f0a-40e6-b348-9021b1b57fa6",
  "users": [
    "46406186-f4e5-4a52-8bba-3668d1fc338f",
    "658384cb-a67a-470e-a4ba-5a16098d7589"
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

Invite other user to Group

### Request Parameter

| Name     | Type   | Description                     | Required | Example value                                                                     |
| -------- | ------ | ------------------------------- | -------- | --------------------------------------------------------------------------------- |
| group_id | String | Group ID to invite the users to | True     | ccf60309-2f0a-40e6-b348-9021b1b57fa6                                              |
| users    | Array  | List of user ID to invite       | True     | `["46406186-f4e5-4a52-8bba-3668d1fc338f","658384cb-a67a-470e-a4ba-5a16098d7589"]` |

## POST /group/remove-user

> Request Example

```json
{
  "group_member_id": "0c713b9e-88ba-437f-864a-9e2462dbf5a0"
}
```

> Response Example

```json
{
  "kicked_at": 1584534457426,
  "group_member_id": "0c713b9e-88ba-437f-864a-9e2462dbf5a0",
  "user_id": "658384cb-a67a-470e-a4ba-5a16098d7589",
  "role": "member",
  "status": "kicked",
  "invited_by": "1d0263e7-2015-458c-b29f-801fee73a393",
  "kicked_by": "1d0263e7-2015-458c-b29f-801fee73a393",
  "invited_at": 1584534383350,
  "group_id": "ccf60309-2f0a-40e6-b348-9021b1b57fa6"
}
```

### Description

Remove user from the Group

### Request Parameter

| Name            | Type   | Description               | Required | Example value                        |
| --------------- | ------ | ------------------------- | -------- | ------------------------------------ |
| group_member_id | String | Group member ID to remove | True     | 0c713b9e-88ba-437f-864a-9e2462dbf5a0 |

## GET /group/member/:groupID

> Response Example

```json
[
  {
    "avatar": "https://users-photo-dev.s3.ap-northeast-1.amazonaws.com/uploads/1f35081e-afb3-4bd8-b132-4a9ecf36736f.jpg",
    "login": "Email",
    "user_id": "1f35081e-afb3-4bd8-b132-4a9ecf36736f",
    "available_start_time": "04:00",
    "created_at": 1585094292456,
    "available_end_time": "21:00",
    "role": "admin",
    "available_days": ["Mon"],
    "username": "diare2029",
    "email": "diare@mail.com",
    "name": "Diare Ngentot",
    "kicked_at": 0,
    "group_member_id": "0efce601-5c23-46af-a01a-8e4120e04bdb",
    "status": "joined",
    "invited_by": "1f35081e-afb3-4bd8-b132-4a9ecf36736f",
    "kicked_by": "-",
    "invited_at": 1585289894877,
    "group_id": "10e15565-7b50-4f18-9b55-7977c617bb9b"
  }
]
```

### Description

Get list of member in a group

## GET /group/my-invitation

> Response Example

```json
[
  {
    "created_at": 1584533027596,
    "description": "Yuk belajar bareng",
    "name": "Grup belajar bareng",
    "created_by": "1d0263e7-2015-458c-b29f-801fee73a393",
    "group_id": "ccf60309-2f0a-40e6-b348-9021b1b57fa6",
    "deleted_by": "-",
    "deleted_at": 0,
    "group_member_id": "d0c45242-6b87-450d-9b66-f5070461dc6a",
    "avatar": "-"
  }
]
```

### Description

Get list of my invitations

## POST /group/respond

> Request Example

```json
{
  "group_member_id": "d0c45242-6b87-450d-9b66-f5070461dc6a",
  "status": "joined"
}
```

> Response Example

```json
{
  "success": "true"
}
```

### Description

Respond to group invitation. When user accepts the invitation, that user will automagically be friends with all of the group member

### Request Parameter

| Name            | Type   | Description                         | Required | Example value                        |
| --------------- | ------ | ----------------------------------- | -------- | ------------------------------------ |
| group_member_id | String | User's group member ID in the group | True     | d0c45242-6b87-450d-9b66-f5070461dc6a |
| status          | String | New user status in the group        | True     | `joined` or `declined`               |

## GET /group/me

> Response Example

```json
[
  {
    "created_at": 1584533027596,
    "description": "Yuk belajar bareng",
    "name": "Grup belajar bareng",
    "created_by": "1d0263e7-2015-458c-b29f-801fee73a393",
    "group_id": "ccf60309-2f0a-40e6-b348-9021b1b57fa6",
    "deleted_by": "-",
    "group_member_id": "154cd569-9cdd-48c2-a224-59ec389757b0",
    "deleted_at": 0,
    "avatar": "-"
  }
]
```

### Description

Get list of joined groups

## POST /group/remove

> Request example

```json
{
  "group_id": "ccf60309-2f0a-40e6-b348-9021b1b57fa6"
}
```

> Response Example

```json
{
  "created_at": 1584533027596,
  "description": "Yuk belajar bareng",
  "name": "Grup belajar bareng",
  "created_by": "1d0263e7-2015-458c-b29f-801fee73a393",
  "group_id": "ccf60309-2f0a-40e6-b348-9021b1b57fa6",
  "deleted_by": "-",
  "group_member_id": "154cd569-9cdd-48c2-a224-59ec389757b0",
  "deleted_at": 1584533027596,
  "avatar": "-"
}
```

### Description

Delete a group

### Request Parameter

| Name     | Type   | Description        | Required | Example value                        |
| -------- | ------ | ------------------ | -------- | ------------------------------------ |
| group_id | String | group_id to delete | True     | ccf60309-2f0a-40e6-b348-9021b1b57fa6 |

## POST /group/upload-ava

> Request Example

```json
{
  "group_id": "ccf60309-2f0a-40e6-b348-9021b1b57fa6",
  "image": "{{base64EncodedImage}}"
}
```

> Response Example

```json
{
  "avatar": "https://groups-photo-dev.s3.ap-northeast-1.amazonaws.com/uploads/10e15565-7b50-4f18-9b55-7977c617bb9b.jpg",
  "created_at": 1585289894877,
  "deleted_at": 0,
  "created_by": "1f35081e-afb3-4bd8-b132-4a9ecf36736f",
  "deleted_by": "-",
  "description": "-",
  "name": "Aku invite corona",
  "group_id": "10e15565-7b50-4f18-9b55-7977c617bb9b"
}
```

### Definition

Upload group avatar

### Request Parameter

| Name     | Type   | Description          | Required | Example value                          |
| -------- | ------ | -------------------- | -------- | -------------------------------------- |
| image    | String | Base64 encoded image | True     | some-base-64-encoded-image             |
| group_id | String | Group ID to update   | True     | `ccf60309-2f0a-40e6-b348-9021b1b57fa6` |
