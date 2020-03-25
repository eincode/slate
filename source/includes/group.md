# Group

## GET /group/:groupId

> Response Example

```json
{
  "createdAt": 1584525282422,
  "description": "Belajar kuy",
  "createdBy": "1d0263e7-2015-458c-b29f-801fee73a393",
  "name": "Grup Belajar",
  "group_id": "3b01e0a9-6873-4aea-b361-6ee07b27feb4",
  "deletedBy": null
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
  "createdAt": 1584525282422,
  "description": "Belajar kuy",
  "createdBy": "1d0263e7-2015-458c-b29f-801fee73a393",
  "name": "Grup Belajar",
  "group_id": "3b01e0a9-6873-4aea-b361-6ee07b27feb4",
  "deletedBy": null
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
  "createdAt": 1584533027596,
  "createdBy": "1d0263e7-2015-458c-b29f-801fee73a393",
  "deletedBy": null
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
    "kicked_at": null,
    "user_id": "46406186-f4e5-4a52-8bba-3668d1fc338f",
    "group_member_id": "d0c45242-6b87-450d-9b66-f5070461dc6a",
    "role": "member",
    "status": "invited",
    "invited_by": "1d0263e7-2015-458c-b29f-801fee73a393",
    "kicked_by": null,
    "invited_at": 1584534383348,
    "group_id": "ccf60309-2f0a-40e6-b348-9021b1b57fa6"
  },
  {
    "kicked_at": null,
    "user_id": "1d0263e7-2015-458c-b29f-801fee73a393",
    "group_member_id": "154cd569-9cdd-48c2-a224-59ec389757b0",
    "role": "admin",
    "status": "joined",
    "kicked_by": null,
    "invited_at": 1584533027596,
    "group_id": "ccf60309-2f0a-40e6-b348-9021b1b57fa6"
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
    "createdAt": 1584533027596,
    "description": "Yuk belajar bareng",
    "name": "Grup belajar bareng",
    "createdBy": "1d0263e7-2015-458c-b29f-801fee73a393",
    "group_id": "ccf60309-2f0a-40e6-b348-9021b1b57fa6",
    "deletedBy": null,
    "group_member_id": "d0c45242-6b87-450d-9b66-f5070461dc6a"
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
  "kicked_at": null,
  "group_member_id": "d0c45242-6b87-450d-9b66-f5070461dc6a",
  "user_id": "46406186-f4e5-4a52-8bba-3668d1fc338f",
  "role": "member",
  "status": "joined",
  "invited_by": "1d0263e7-2015-458c-b29f-801fee73a393",
  "kicked_by": null,
  "invited_at": 1584534383348,
  "group_id": "ccf60309-2f0a-40e6-b348-9021b1b57fa6"
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
    "createdAt": 1584533027596,
    "description": "Yuk belajar bareng",
    "name": "Grup belajar bareng",
    "createdBy": "1d0263e7-2015-458c-b29f-801fee73a393",
    "group_id": "ccf60309-2f0a-40e6-b348-9021b1b57fa6",
    "deletedBy": null,
    "group_member_id": "154cd569-9cdd-48c2-a224-59ec389757b0"
  }
]
```

### Description

Get list of joined groups
