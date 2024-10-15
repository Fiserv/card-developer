# Test Cases

<span style="color:#ff6600;">**Payments API Endpoints**</span>

Tests must use only requests given here.

## Payment Hold

### Payments Hold v1: Search payment hold information

This API retrieves payment hold information.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/payments/v1/payments/holds/search

```
{
    "accountNumber": "123456789"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
    "floatPayments": 1,
    "paymentHolds": [
        {
            "paymentEventIdentifier": "089060007812",
            "transactionCode": 271,
            "description": "Payment",
            "postingDate": "2023-12-26",
            "effectiveDate": "2023-12-26",
            "paymentAmount": "000000000065.00",
            "ageOffDate": "2024-01-21",
            "floatAmount": 35,
            "floatExpirationDate": "2024-01-15",
            "currentStatusText": "CH - Payment float amount and/or date changed",
            "availableCreditAmount": "0000000000097886"
        }
    ]
}
```

### Payments Hold v1: Update payment hold

This API makes updates to the existing payment hold.

#### Request

**HTTP Method:** PATCH

**Target URL:**  https://card-sandbox.api.fiservapps.com/cs/payments/v1/payments/hold

```
{

    "accountNumber": "123456789",
    "paymentEventIdentifier": "169030085708",
    "update": {
        "floatAmount": 18,
        "floatExpDate": "2023-12-26"
    }
}
```

#### Response

**HTTP Code:** 204 No Content

### Payments Hold v1: Release payment hold

This API releases the hold on the payment.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/payments/v1/payments/hold

```
{
    "accountNumber": "123456789",
    "paymentEventIdentifier": "169030085708",
    "release": {
        "floatAmount": 18
    }
}
```

#### Response

**HTTP Code:** 204 No Content
