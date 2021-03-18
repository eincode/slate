# Company

## POST /api/company

> Request Example

```json
{
  "country": "Indonesia",
  "name": "BTOB 3",
  "type": "Fashion",
  "address": "Boyce Avenue, No. 5",
  "website": "https://google.com",
  "email": "btob@boyce.com",
  "phone": "+62812345679",
  "request": "From Tokyo only",
  "img": "base64 image in JPG"
}
```

> Response Example

```json
{
  "id": "d2f0744f-a334-46da-8722-2ccc79876287",
  "country": "Indonesia",
  "name": "BTOB 4",
  "type": "Fashion",
  "address": "Boyce Avenue, No. 5",
  "website": "https://google.com",
  "email": "btob@boyce.com",
  "phone": "+62812345679",
  "request": "From Tokyo only",
  "img": "/static/images/product/d2f0744f-a334-46da-8722-2ccc79876287.jpg",
  "userId": "d2f0744f-a334-46da-8722-2ccc79876287",
  "createdAt": "2021-03-18T04:25:31.034Z"
}
```

### Definitian

Create a new company

### Request Parameter

| Name    | Type   | Description                  | Required | Example Value        |
| ------- | ------ | ---------------------------- | -------- | -------------------- |
| country | String | Country for company          | True     | Indonesia            |
| name    | String | Company Name                 | True     | BTOB                 |
| type    | String | Company type of industry     | True     | Fashion              |
| address | String | Company address              | True     | Boyce Avenue No. 5   |
| website | String | Company website              | True     | https://google.com   |
| email   | String | Company email                | True     | btob@boyce.com       |
| phone   | String | Company phone                | True     | +8823643234          |
| request | String | Special request from company | True     | From Tokyo only      |
| img     | String | Image in base64 format       | Optional | base64 encoded image |

## GET /api/company/me

> Response Example

```json
{
  "id": "d2f0744f-a334-46da-8722-2ccc79876287",
  "country": "Indonesia",
  "name": "BTOB 4",
  "type": "Fashion",
  "address": "Boyce Avenue, No. 5",
  "website": "https://google.com",
  "email": "btob@boyce.com",
  "phone": "+62812345679",
  "request": "From Tokyo only",
  "img": "/static/images/product/d2f0744f-a334-46da-8722-2ccc79876287.jpg",
  "userId": "d2f0744f-a334-46da-8722-2ccc79876287",
  "createdAt": "2021-03-18T04:25:31.034Z"
}
```

### Definition

Get my company

## GET /api/company?id={companyId}

> Response Example

```json
{
  "id": "d2f0744f-a334-46da-8722-2ccc79876287",
  "country": "Indonesia",
  "name": "BTOB 3",
  "type": "Fashion",
  "address": "Boyce Avenue, No. 5",
  "website": "https://google.com",
  "email": "btob@boyce.com",
  "phone": "+62812345679",
  "request": "From Tokyo only",
  "img": "/static/images/product/d2f0744f-a334-46da-8722-2ccc79876287.jpg",
  "userId": "d2f0744f-a334-46da-8722-2ccc79876287",
  "createdAt": "2021-03-15T07:13:31.163Z"
}
```

### Definition

Get company by ID

## POST /api/company/save

> Request Example

```json
{
  "companyId": "d2f0744f-a334-46da-8722-2ccc79876287"
}
```

> Response Example

```json
{
  "id": "d2f0744f-a334-46da-8722-2ccc79876287",
  "personInChargeId": "d2f0744f-a334-46da-8722-2ccc79876287"
}
```

### Definition

Save company by company ID

### Request parameter

| Name      | Type   | Description        | Required | Example Value                          |
| --------- | ------ | ------------------ | -------- | -------------------------------------- |
| companyId | String | Company ID to save | True     | `d2f0744f-a334-46da-8722-2ccc79876287` |

## GET /api/company/saved

> Response Example

```json
{
  "id": "d2f0744f-a334-46da-8722-2ccc79876287",
  "personInChargeId": "d2f0744f-a334-46da-8722-2ccc79876287",
  "companies": [
    {
      "id": "d2f0744f-a334-46da-8722-2ccc79876287",
      "country": "Indonesia",
      "name": "BTOB 3",
      "type": "Fashion",
      "address": "Boyce Avenue, No. 5",
      "website": "https://google.com",
      "email": "btob@boyce.com",
      "phone": "+62812345679",
      "request": "From Tokyo only",
      "img": "/static/images/product/d2f0744f-a334-46da-8722-2ccc79876287.jpg",
      "userId": "d2f0744f-a334-46da-8722-2ccc79876287",
      "createdAt": "2021-03-15T07:13:31.163Z"
    }
  ]
}
```

### Definition

Get my saved companies
