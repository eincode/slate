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
    "minimumOrderQuantity": "20 packs"
  },
  {
    "category": "Fashion",
    "name": "Full Dress 3",
    "description": "Some custom Full Dress",
    "isHalal": true,
    "minimumOrderQuantity": "20 kgs"
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

## GET /api/product/{companyID}

> Response Example

```json
[
  {
    "id": 9,
    "category": "Fashion",
    "name": "Midi Dress 3",
    "description": "Some custom Midi Dress",
    "img": null,
    "isHalal": true,
    "minimumOrderQuantity": "20 packs",
    "companyId": 6
  },
  {
    "id": 10,
    "category": "Fashion",
    "name": "Full Dress 3",
    "description": "Some custom Full Dress",
    "img": null,
    "isHalal": true,
    "minimumOrderQuantity": "20 kgs",
    "companyId": 6
  }
]
```

### Definition
Get product list by company ID