# Person In Charge

## POST /api/pic/{companyId}

> Request Example

```json
{
  "name": "Boyce Avenue 4",
  "nationality": "Austria",
  "email": "boyce@me.com",
  "phone": "+88232637723",
  "img": "base64 image in JPG"
}
```

> Response Example

```json
{
  "id": "d2f0744f-a334-46da-8722-2ccc79876287",
  "name": "Boyce Avenue 4",
  "nationality": "Austria",
  "email": "boyce@me.com",
  "phone": "+88232637723",
  "img": "/static/images/product/d2f0744f-a334-46da-8722-2ccc79876287.jpg",
  "companyId": "d2f0744f-a334-46da-8722-2ccc79876287",
  "userId": "d2f0744f-a334-46da-8722-2ccc79876287"
}
```

### Definition

Create Person in Charge for the company

### Request Parameter

| Name        | Type   | Description                  | Required | Example Value        |
| ----------- | ------ | ---------------------------- | -------- | -------------------- |
| name        | String | Person in Charge Name        | True     | Boyce Avenue         |
| nationality | String | Person in Charge Nationality | True     | Indonesia            |
| email       | String | Person in Charge Email       | True     | boyce@btob.com       |
| phone       | String | Person in Charge Phone       | True     | +8843212312342       |
| img         | String | Image in base64 format       | Optional | base64 encoded image |

## GET /api/pic/{personInChargeId}

> Response Example

```json
[
  {
    "id": "d2f0744f-a334-46da-8722-2ccc79876287",
    "name": "Boyce Avenue 3",
    "nationality": "Austria",
    "email": "boyce@me.com",
    "phone": "+88232637723",
    "img": "/static/images/product/d2f0744f-a334-46da-8722-2ccc79876287.jpg",
    "companyId": "d2f0744f-a334-46da-8722-2ccc79876287",
    "userId": "d2f0744f-a334-46da-8722-2ccc79876287"
  }
]
```

### Definition

Get person in charge by company ID
