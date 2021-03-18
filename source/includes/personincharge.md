# Person In Charge

## POST /api/pic/{companyId}

> Request Example

```json
{
  "name": "Boyce Avenue 4",
  "nationality": "Austria",
  "email": "boyce@me.com",
  "phone": "+88232637723"
}
```

> Response Example

```json
{
  "id": 5,
  "name": "Boyce Avenue 4",
  "nationality": "Austria",
  "email": "boyce@me.com",
  "phone": "+88232637723",
  "img": null,
  "companyId": 6,
  "userId": 20
}
```

### Definition

Create Person in Charge for the company

### Request Parameter

| Name        | Type   | Description                  | Required | Example Value  |
| ----------- | ------ | ---------------------------- | -------- | -------------- |
| name        | String | Person in Charge Name        | True     | Boyce Avenue   |
| nationality | String | Person in Charge Nationality | True     | Indonesia      |
| email       | String | Person in Charge Email       | True     | boyce@btob.com |
| phone       | String | Person in Charge Phone       | True     | +8843212312342 |

## GET /api/pic/{personInChargeId}

> Response Example

```json
[
  {
    "id": 3,
    "name": "Boyce Avenue 3",
    "nationality": "Austria",
    "email": "boyce@me.com",
    "phone": "+88232637723",
    "img": null,
    "companyId": 3,
    "userId": 3
  }
]
```

### Definition

Get person in charge by company ID
