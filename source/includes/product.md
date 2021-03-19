# Product

## POST /api/product/{companyID}

> Request Example

```json
[
  {
    "category": "Fashion",
    "name": "Midi Dress 3",
    "description": "Some custom Midi Dress",
    "isHalal": true,
    "minimumOrderQuantity": "20 packs",
    "img": "base64 image in JPG"
  },
  {
    "category": "Fashion",
    "name": "Full Dress 3",
    "description": "Some custom Full Dress",
    "isHalal": true,
    "minimumOrderQuantity": "20 kgs",
    "img": "base64 image in JPG"
  }
]
```

> Response Example

```json
{
  "count": 2
}
```

### Definition

Create product by company ID

### Request Parameter

| Name                 | Type    | Description                    | Required | Example Value          |
| -------------------- | ------- | ------------------------------ | -------- | ---------------------- |
| category             | String  | Product Category               | Required | Fashion                |
| name                 | String  | Product Name                   | Required | Midi Dress             |
| description          | String  | Product Description            | Required | Some Custom Midi Dress |
| isHalal              | Boolean | Product is Halal or not        | Required | true                   |
| minimumOrderQuantity | String  | Product minimum order quantity | Required | true                   |
| img                  | String  | Image in base64 format         | Optional | base64 encoded image   |

## GET /api/product/{companyID}

> Response Example

```json
[
  {
    "id": "07514458-b24a-41aa-b924-262eb2486f74",
    "category": "Fashion",
    "name": "Midi Dress 3",
    "description": "Some custom Midi Dress",
    "isHalal": true,
    "minimumOrderQuantity": "20 packs",
    "companyId": "d2f0744f-a334-46da-8722-2ccc79876287",
    "img": "/static/images/product/d2f0744f-a334-46da-8722-2ccc79876287.jpg"
  },
  {
    "id": "07514458-b24a-41aa-b924-262eb2486f74",
    "category": "Fashion",
    "name": "Full Dress 3",
    "description": "Some custom Full Dress",
    "isHalal": true,
    "minimumOrderQuantity": "20 kgs",
    "companyId": "d2f0744f-a334-46da-8722-2ccc79876287",
    "img": "/static/images/product/d2f0744f-a334-46da-8722-2ccc79876287.jpg"
  }
]
```

### Definition

Get product list by company ID
