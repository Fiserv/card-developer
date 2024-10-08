# Test Cases

<span style="color:#ff6600;">**Card API Endpoints**</span>

When testing these endpoints, please use the test cases and test data from the Sandbox.

## Order

### Credit Order v2: Search using card number

Retrieves the orders for the selected cardholder record.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/order/search

```
{
       "cardNumber": "4000200030004001"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
    "orders": [
        {
            "cardNumber": "400020XXXXXX4001",
            "nonTransToken": "pSAZIXCAXrAo4001",
            "transactionCode": "194",
            "cardPlasticsCount": "001",
            "specialHandling": "NONE",
            "cardholderOrderInfo": {
                "cardholderName": "Doe, John H",
                "personalizedEmbossingText": "Home Team"
            }
        }
    ]
}
```

### Credit Order v2: Cancel using card number

Cancel the selected order.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/order

```
{
      "cardNumber": "4000100020004001",
      "action": "CANCEL"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
    "card": {
        "cardNumber": "400020XXXXXX4001",
        "nonTransToken": "pSAZIXCAXrAo4001",
        "action": "CANCEL"
    }
}
```

### Debit Order v2: Search using card number

Retrieves the orders for the selected cardholder record.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/order/search

```
{
    "cardNumber": "4000200030004000",
    "memberNumber": "0"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
    "orders": [
        {
            "cardNumber": "400010XXXXXX3000",
            "orderStatus": "ACTIVE",
            "orderType": "CARD",
            "rushType": "REGULAR",
            "processedDate": "2022-08-03",
            "orderId": "4974",
            "orderDate": "2022-09-09",
            "orderReason": "NEW",
            "orderedBy": "Jesse Doe",
            "memberNumber": "0",
            "logo": "APIP",
            "lastMaintenanceBy": "Jesse Doe",
            "lastMaintainanceDate": "1990-08-24",
            "lastMaintainanceTime": "12:00",
            "cardholderOrderInfo": {
                "nameSequenceNumber": "1",
                "cardholderName": "Jesse Doe",
                "personalizedEmbossingText": "Home Team",
                "photoId": "EFGH",
                "plasticId": "PM001",
                "nameSuffix": "MD"
            },
            "orderAddress": {
                "addressLine1": "123 Any Street",
                "addressLine2": "Apt 100",
                "city": "Newark",
                "country": "USA",
                "state": "NewJersey",
                "zipCode": "12345",
                "addressType": "PRIMARY"
            },
            "cardMiscellaneous": {
                "cardClass": "AAA00",
                "emv": "CONTACT",
                "pinVendor": "1234",
                "vendor": "Home Supply"
            }
        }
    ]
}
```

### Debit Order v2: Search using NTT

Retrieves the orders for the selected cardholder record.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/order/search

```
{
          "nonTransToken": "WUPIL5DQTZGM3000",
          "memberNumber": "0"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
    "orders": [
        {
            "nonTransToken": "WUPIL5DQTZGM3000",
            "orderStatus": "ACTIVE",
            "orderType": "CARD",
            "rushType": "REGULAR",
            "processedDate": "2022-08-03",
            "orderId": "4974",
            "orderDate": "2022-09-09",
            "orderReason": "NEW",
            "orderedBy": "Jesse Doe",
            "memberNumber": "0",
            "logo": "APIP",
            "lastMaintenanceBy": "Jesse Doe",
            "lastMaintainanceDate": "1990-08-24",
            "lastMaintainanceTime": "12:00",
            "cardholderOrderInfo": {
                "nameSequenceNumber": "1",
                "cardholderName": "Jesse Doe",
                "personalizedEmbossingText": "Home Team",
                "photoId": "EFGH",
                "plasticId": "PM001",
                "nameSuffix": "MD"
            },
            "orderAddress": {
                "addressLine1": "123 Any Street",
                "addressLine2": "Apt 100",
                "city": "Newark",
                "country": "USA",
                "state": "NewJersey",
                "zipCode": "12345",
                "addressType": "PRIMARY"
            },
            "cardMiscellaneous": {
                "cardClass": "AAA00",
                "emv": "CONTACT",
                "pinVendor": "1234",
                "vendor": "Home Supply"
            }
        }
    ]
}
```

### Debit Order v2: Cancel using card number

Cancel the selected order.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/order

```
{
      "cardNumber": "4000200030004000",
      "orderId": "436",
      "memberNumber": "0",
      "action": "CANCEL",
      "rushType": "NONE",
      "orderType": "CARD"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
      "card": {
          "cardNumber": "400020XXXXXX4000",
          "action": "CANCEL",
          "orderId": "436"
      }
}
```

### Debit Order v2: Cancel using NTT

Cancel the selected order.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/order

```
{
      "nonTransToken": "WUPIL5DQTZGM3000",
      "orderId": "436",
      "action": " CANCEL",
      "rushType": "NONE",
      "orderType": "CARD"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
      "card": {
          "nonTransToken": "WUPIL5DQTZGM3000",
          "action": "CANCEL",
          "orderId": "436"
      }
}
```

### Debit Order v2: Update using card number

Update rush type of the selected order.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/order

```
{
      "cardNumber": "4000200030004000",
      "orderId": "436",
      "memberNumber": "0",
      "action": "UPDATE",
      "rushType": "NONE",
      "orderType": "CARD"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
      "card": {
          "cardNumber": "400020XXXXXX4000",
          "action": "UPDATE",
          "orderId": "436"
      }
  }
```
