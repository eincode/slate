# Group

## POST /group/create-group?accessToken={accessToken}

> Request Example

```json
{
  "name": "group-test",
  "description": "desc test"
}
```

> Response Example

```json
{
  "id": "9181158038276432",
  "name": "group-test",
  "description": "desc test",
  "created_at": "Tue Jan 28 2020 04:45:07 GMT+0000 (Coordinated Universal Time)",
  "updated_at": "-",
  "deleted_at": "-",
  "created_by": "user:9170315640735828",
  "deleted_by": "-"
}
```

### Description

Create new event group

### Request Parameter

| Name        | Type   | Description             | Required | Example value          |
| ----------- | ------ | ----------------------- | -------- | ---------------------- |
| name        | String | Group event name        | True     | group-test             |
| description | String | Group event description | True     | group description test |

## POST /group/invitation/invite?accessToken={accessToken}

> Request Example

```json
{
  "user_id": "user:9177652795967584",
  "group_id": "9193517173606516"
}
```

> Response Example

```json
{
  "id": "9193526318926006",
  "group_id": "9193517173606516",
  "role": "MEMBER",
  "status": "INVITED",
  "user_id": "user:9177652795967584",
  "created_at": "Sat, 01 Feb 2020 13:35:57 GMT",
  "invited_by": "test"
}
```

### Description

Invite other member to an event

### Request Parameter

| Name     | Type   | Description                       | Required | Example value         |
| -------- | ------ | --------------------------------- | -------- | --------------------- |
| user_id  | String | User ID to invite                 | True     | user:9177652795967584 |
| group_id | String | Group ID to invite the invitee to | True     | 9193517173606516      |

## POST /group/invitation/accept?accessToken={accessToken}

> Request Example

```json
{
  "user_id": "user:9177652795967584",
  "group_id": "9193517173606516"
}
```

> Response Example

```json
{
  "user_id": "123123",
  "accepted_at": "Sun, 09 Feb 2020 10:15:37 GMT",
  "created_at": "Sat, 01 Feb 2020 12:57:30 GMT",
  "role": "MEMBER",
  "status": "ACCEPTED",
  "invited_by": "123123",
  "id": "9193450719021134",
  "group_id": "9178381983451212"
}
```

### Description

Accept an invitation

### Request Parameter

| Name     | Type   | Description                       | Required | Example value         |
| -------- | ------ | --------------------------------- | -------- | --------------------- |
| user_id  | String | User ID to invite                 | True     | user:9177652795967584 |
| group_id | String | Group ID to invite the invitee to | True     | 9193517173606516      |

## POST /group/invitation/decline?accessToken={accessToken}

> Request Example

```json
{
  "user_id": "user:9177652795967584",
  "group_id": "9193517173606516"
}
```

> Response Example

```json
{
  "user_id": "123123",
  "accepted_at": "Sun, 09 Feb 2020 10:15:37 GMT",
  "created_at": "Sat, 01 Feb 2020 12:57:30 GMT",
  "role": "MEMBER",
  "status": "DECLINED",
  "invited_by": "123123",
  "id": "9193450719021134",
  "group_id": "9178381983451212"
}
```

### Description

Accept an invitation

### Request Parameter

| Name     | Type   | Description                       | Required | Example value         |
| -------- | ------ | --------------------------------- | -------- | --------------------- |
| user_id  | String | User ID to invite                 | True     | user:9177652795967584 |
| group_id | String | Group ID to invite the invitee to | True     | 9193517173606516      |

## GET /group/invitation/my-invitation?accessToken={accessToken}

> Response Example

```json
{
  "groups": [
    {
      "updated_at": "-",
      "created_at": "Sat Feb 01 2020 12:46:03 GMT+0000 (Coordinated Universal Time)",
      "deleted_at": "-",
      "deleted_by": "-",
      "created_by": "123",
      "description": "value2",
      "id": "9193428193904732",
      "name": "group test"
    }
  ]
}
```

### Description

Get list of invitation

## GET /group/my-group?accessToken={accessToken}

> Response Example

```json
{
  "groups": [
    {
      "updated_at": "-",
      "created_at": "Sat Feb 01 2020 13:31:18 GMT+0000 (Coordinated Universal Time)",
      "deleted_at": "-",
      "deleted_by": "-",
      "created_by": "123",
      "description": "value2",
      "id": "9193517173606516",
      "name": "group test"
    }
  ]
}
```

### Description

Get list of joined groups
