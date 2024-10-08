# Test Cases

<span style="color:#ff6600;">**Card API Endpoints**</span>

When testing these endpoints, please use the test cases and test data from the Sandbox.

## Limits

### Debit Limits v2: Search limits using card number

Retrieves the limits for the selected cardholder record.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/search

```
{
  "cardNumber": "4000200030004000"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "400020XXXXXX4000",
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "dailyLimits": {
    "nonExpiring": false,
    "limitExpirationDate": "2024-12-31",
    "limitType": "OVERRIDE",
    "aggregateOfflineAmount": "500",
    "aggregateTotalAmount": "2500",
    "atmOfflineAmount": "300",
    "atmTotalAmount": "600",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "2",
    "cashEquivTotalAmount": "10",
    "customerNPOfflineAmount": "500",
    "customerNPTotalAmount": "1500",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "500",
    "posTotalAmount": "2500",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  },
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "0",
    "accountOpenToBuyTotalAmount": "0",
    "cardOpenToBuyOfflineAmount": "0",
    "cardOpenToBuyTotalAmount": "0"
  },
  "velocityLimits": {
    "aggMaxCardUsage": "0",
    "aggTimeInterval": "00:00",
    "atmMaxCardUsage": "0",
    "atmTimeInterval": "00:00",
    "cashEquivMaxCardUsage": "0",
    "cashEquivTimeInterval": "00:00",
    "posMaxCardUsage": "0",
    "posTimeInterval": "00:00"
  }
}
```

### Debit Limits v2: Search limits using NTT

Retrieves the limits for the selected cardholder record.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/search

```
{
  "nonTransToken": "piUVBJKZGfks4000"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "400020XXXXXX4000",
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "dailyLimits": {
    "nonExpiring": false,
    "limitExpirationDate": "2024-12-31",
    "limitType": "OVERRIDE",
    "aggregateOfflineAmount": "500",
    "aggregateTotalAmount": "2500",
    "atmOfflineAmount": "300",
    "atmTotalAmount": "600",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "2",
    "cashEquivTotalAmount": "10",
    "customerNPOfflineAmount": "500",
    "customerNPTotalAmount": "1500",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "500",
    "posTotalAmount": "2500",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  },
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "0",
    "accountOpenToBuyTotalAmount": "0",
    "cardOpenToBuyOfflineAmount": "0",
    "cardOpenToBuyTotalAmount": "0"
  },
  "velocityLimits": {
    "aggMaxCardUsage": "0",
    "aggTimeInterval": "00:00",
    "atmMaxCardUsage": "0",
    "atmTimeInterval": "00:00",
    "cashEquivMaxCardUsage": "0",
    "cashEquivTimeInterval": "00:00",
    "posMaxCardUsage": "0",
    "posTimeInterval": "00:00"
  }
}
```

### Debit Limits v2: Search limits using card number, token only response format

Retrieves the limits for the selected cardholder record.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/search

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "TOKEN_ONLY",
  "memberNumber": "0"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "dailyLimits": {
    "nonExpiring": false,
    "limitExpirationDate": "2024-12-31",
    "limitType": "OVERRIDE",
    "aggregateOfflineAmount": "500",
    "aggregateTotalAmount": "2500",
    "atmOfflineAmount": "300",
    "atmTotalAmount": "600",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "2",
    "cashEquivTotalAmount": "10",
    "customerNPOfflineAmount": "500",
    "customerNPTotalAmount": "1500",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "500",
    "posTotalAmount": "2500",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  },
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "0",
    "accountOpenToBuyTotalAmount": "0",
    "cardOpenToBuyOfflineAmount": "0",
    "cardOpenToBuyTotalAmount": "0"
  },
  "velocityLimits": {
    "aggMaxCardUsage": "0",
    "aggTimeInterval": "00:00",
    "atmMaxCardUsage": "0",
    "atmTimeInterval": "00:00",
    "cashEquivMaxCardUsage": "0",
    "cashEquivTimeInterval": "00:00",
    "posMaxCardUsage": "0",
    "posTimeInterval": "00:00"
  }
}
```

### Debit Limits v2: Search limits using card number, full card and token only response format.

Retrieves the limits for the selected cardholder record

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/search

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "FULL_CARD_AND_TOKEN",
  "memberNumber": "0"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "4000200030004000",
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "dailyLimits": {
    "nonExpiring": false,
    "limitExpirationDate": "2024-12-31",
    "limitType": "OVERRIDE",
    "aggregateOfflineAmount": "500",
    "aggregateTotalAmount": "2500",
    "atmOfflineAmount": "300",
    "atmTotalAmount": "600",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "2",
    "cashEquivTotalAmount": "10",
    "customerNPOfflineAmount": "500",
    "customerNPTotalAmount": "1500",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "500",
    "posTotalAmount": "2500",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  },
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "0",
    "accountOpenToBuyTotalAmount": "0",
    "cardOpenToBuyOfflineAmount": "0",
    "cardOpenToBuyTotalAmount": "0"
  },
  "velocityLimits": {
    "aggMaxCardUsage": "0",
    "aggTimeInterval": "00:00",
    "atmMaxCardUsage": "0",
    "atmTimeInterval": "00:00",
    "cashEquivMaxCardUsage": "0",
    "cashEquivTimeInterval": "00:00",
    "posMaxCardUsage": "0",
    "posTimeInterval": "00:00"
  }
}
```

### Debit Limits v2: Search limits using card number, masked card only response format

Retrieves the limits for the selected cardholder record

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/search

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "MASKED_CARD_ONLY",
  "memberNumber": "0"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "400020XXXXXX4000",
  "memberNumber": "0",
  "dailyLimits": {
    "nonExpiring": false,
    "limitExpirationDate": "2024-12-31",
    "limitType": "OVERRIDE",
    "aggregateOfflineAmount": "500",
    "aggregateTotalAmount": "2500",
    "atmOfflineAmount": "300",
    "atmTotalAmount": "600",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "2",
    "cashEquivTotalAmount": "10",
    "customerNPOfflineAmount": "500",
    "customerNPTotalAmount": "1500",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "500",
    "posTotalAmount": "2500",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  },
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "0",
    "accountOpenToBuyTotalAmount": "0",
    "cardOpenToBuyOfflineAmount": "0",
    "cardOpenToBuyTotalAmount": "0"
  },
  "velocityLimits": {
    "aggMaxCardUsage": "0",
    "aggTimeInterval": "00:00",
    "atmMaxCardUsage": "0",
    "atmTimeInterval": "00:00",
    "cashEquivMaxCardUsage": "0",
    "cashEquivTimeInterval": "00:00",
    "posMaxCardUsage": "0",
    "posTimeInterval": "00:00"
  }
}
```

### Debit Limits v2: Search limits using card number, masked card and token response format

Retrieves the limits for the selected cardholder record.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/search

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "MASKED_CARD_AND_TOKEN",
  "memberNumber": "0"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "400020XXXXXX4000",
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "dailyLimits": {
    "nonExpiring": false,
    "limitExpirationDate": "2024-12-31",
    "limitType": "OVERRIDE",
    "aggregateOfflineAmount": "500",
    "aggregateTotalAmount": "2500",
    "atmOfflineAmount": "300",
    "atmTotalAmount": "600",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "2",
    "cashEquivTotalAmount": "10",
    "customerNPOfflineAmount": "500",
    "customerNPTotalAmount": "1500",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "500",
    "posTotalAmount": "2500",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  },
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "0",
    "accountOpenToBuyTotalAmount": "0",
    "cardOpenToBuyOfflineAmount": "0",
    "cardOpenToBuyTotalAmount": "0"
  },
  "velocityLimits": {
    "aggMaxCardUsage": "0",
    "aggTimeInterval": "00:00",
    "atmMaxCardUsage": "0",
    "atmTimeInterval": "00:00",
    "cashEquivMaxCardUsage": "0",
    "cashEquivTimeInterval": "00:00",
    "posMaxCardUsage": "0",
    "posTimeInterval": "00:00"
  }
}
```

### Debit Limits v2: Update daily limits using card number

Override the daily limits for the selected cardholder record.

#### Request

**HTTP Method**: PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/daily

```
{
  "cardNumber": "4000200030004000",
  "dailyLimits": {
    "nonExpiring": false,
    "limitExpirationDate": "2024-12-31",
    "aggregateOfflineAmount": "0",
    "aggregateTotalAmount": "0",
    "atmOfflineAmount": "200",
    "atmTotalAmount": "2000",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "100",
    "cashEquivTotalAmount": "500",
    "customerNPOfflineAmount": "0",
    "customerNPTotalAmount": "0",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "400",
    "posTotalAmount": "3000",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "400020XXXXXX4000",
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "dailyLimits": {
    "nonExpiring": false,
    "limitExpirationDate": "2024-12-31",
    "limitType": "OVERRIDE",
    "aggregateOfflineAmount": "0",
    "aggregateTotalAmount": "0",
    "atmOfflineAmount": "200",
    "atmTotalAmount": "2000",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "100",
    "cashEquivTotalAmount": "500",
    "customerNPOfflineAmount": "0",
    "customerNPTotalAmount": "0",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "400",
    "posTotalAmount": "3000",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  }
```

### Debit Limits v2: Update daily limits using NTT

Override the daily limits for the selected cardholder record.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/daily

```
{
      {
  "nonTransToken": "piUVBJKZGfks4000",
  "dailyLimits": {
    "nonExpiring": false,
    "limitExpirationDate": "2024-12-31",
    "aggregateOfflineAmount": "0",
    "aggregateTotalAmount": "0",
    "atmOfflineAmount": "200",
    "atmTotalAmount": "2000",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "100",
    "cashEquivTotalAmount": "500",
    "customerNPOfflineAmount": "0",
    "customerNPTotalAmount": "0",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "400",
    "posTotalAmount": "3000",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "400020XXXXXX4000",
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "dailyLimits": {
    "nonExpiring": false,
    "limitExpirationDate": "2024-12-31",
    "limitType": "OVERRIDE",
    "aggregateOfflineAmount": "0",
    "aggregateTotalAmount": "0",
    "atmOfflineAmount": "200",
    "atmTotalAmount": "2000",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "100",
    "cashEquivTotalAmount": "500",
    "customerNPOfflineAmount": "0",
    "customerNPTotalAmount": "0",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "400",
    "posTotalAmount": "3000",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  }
}
```

### Debit Limits v2: Update daily limits using card number, full card only response format

Override the daily limits for the selected cardholder record.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/daily

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "FULL_CARD_ONLY",
  "memberNumber": "0",
  "dailyLimits": {
    "nonExpiring": false,
    "limitExpirationDate": "2024-12-31",
    "aggregateOfflineAmount": "0",
    "aggregateTotalAmount": "0",
    "atmOfflineAmount": "200",
    "atmTotalAmount": "2000",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "100",
    "cashEquivTotalAmount": "500",
    "customerNPOfflineAmount": "0",
    "customerNPTotalAmount": "0",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "400",
    "posTotalAmount": "3000",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  }
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "4000200030004000",
  "memberNumber": "0",
  "dailyLimits": {
    "nonExpiring": false,
    "limitExpirationDate": "2024-12-31",
    "limitType": "OVERRIDE",
    "aggregateOfflineAmount": "0",
    "aggregateTotalAmount": "0",
    "atmOfflineAmount": "200",
    "atmTotalAmount": "2000",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "100",
    "cashEquivTotalAmount": "500",
    "customerNPOfflineAmount": "0",
    "customerNPTotalAmount": "0",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "400",
    "posTotalAmount": "3000",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  }
}
```

### Debit Limits v2: Update daily limits using card number, full card and token response format

Override the daily limits for the selected cardholder record.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/daily

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "FULL_CARD_AND_TOKEN",
  "memberNumber": "0",
  "dailyLimits": {
    "nonExpiring": false,
    "limitExpirationDate": "2024-12-31",
    "aggregateOfflineAmount": "0",
    "aggregateTotalAmount": "0",
    "atmOfflineAmount": "200",
    "atmTotalAmount": "2000",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "100",
    "cashEquivTotalAmount": "500",
    "customerNPOfflineAmount": "0",
    "customerNPTotalAmount": "0",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "400",
    "posTotalAmount": "3000",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  }
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "4000200030004000",
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "dailyLimits": {
    "nonExpiring": false,
    "limitExpirationDate": "2024-12-31",
    "limitType": "OVERRIDE",
    "aggregateOfflineAmount": "0",
    "aggregateTotalAmount": "0",
    "atmOfflineAmount": "200",
    "atmTotalAmount": "2000",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "100",
    "cashEquivTotalAmount": "500",
    "customerNPOfflineAmount": "0",
    "customerNPTotalAmount": "0",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "400",
    "posTotalAmount": "3000",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  }
}
```

### Debit Limits v2: Update daily limits using card number, masked card only response format

Override the daily limits for the selected cardholder record.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/daily

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "MASKED_CARD_ONLY",
  "memberNumber": "0",
  "dailyLimits": {
    "nonExpiring": false,
    "limitExpirationDate": "2024-12-31",
    "aggregateOfflineAmount": "0",
    "aggregateTotalAmount": "0",
    "atmOfflineAmount": "200",
    "atmTotalAmount": "2000",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "100",
    "cashEquivTotalAmount": "500",
    "customerNPOfflineAmount": "0",
    "customerNPTotalAmount": "0",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "400",
    "posTotalAmount": "3000",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  }
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "400020XXXXXX4000",
  "memberNumber": "0",
  "dailyLimits": {
    "nonExpiring": false,
    "limitExpirationDate": "2024-12-31",
    "limitType": "OVERRIDE",
    "aggregateOfflineAmount": "0",
    "aggregateTotalAmount": "0",
    "atmOfflineAmount": "200",
    "atmTotalAmount": "2000",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "100",
    "cashEquivTotalAmount": "500",
    "customerNPOfflineAmount": "0",
    "customerNPTotalAmount": "0",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "400",
    "posTotalAmount": "3000",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  }
}
```

### Debit Limits v2: Update daily limits using card number, masked card and token response format

Override the daily limits for the selected cardholder record.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/daily

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "MASKED_CARD_AND_TOKEN",
  "memberNumber": "0",
  "dailyLimits": {
    "nonExpiring": false,
    "limitExpirationDate": "2024-12-31",
    "aggregateOfflineAmount": "0",
    "aggregateTotalAmount": "0",
    "atmOfflineAmount": "200",
    "atmTotalAmount": "2000",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "100",
    "cashEquivTotalAmount": "500",
    "customerNPOfflineAmount": "0",
    "customerNPTotalAmount": "0",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "400",
    "posTotalAmount": "3000",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  }
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "400020XXXXXX4000",
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "dailyLimits": {
    "nonExpiring": false,
    "limitExpirationDate": "2024-12-31",
    "limitType": "OVERRIDE",
    "aggregateOfflineAmount": "0",
    "aggregateTotalAmount": "0",
    "atmOfflineAmount": "200",
    "atmTotalAmount": "2000",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "100",
    "cashEquivTotalAmount": "500",
    "customerNPOfflineAmount": "0",
    "customerNPTotalAmount": "0",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "400",
    "posTotalAmount": "3000",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  }
}
```

### Debit Limits v2: Update daily limits using card number, token only response format

Override the daily limits for the selected cardholder record.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/daily

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "TOKEN_ONLY",
  "memberNumber": "0",
  "dailyLimits": {
    "nonExpiring": false,
    "limitExpirationDate": "2024-12-31",
    "aggregateOfflineAmount": "0",
    "aggregateTotalAmount": "0",
    "atmOfflineAmount": "200",
    "atmTotalAmount": "2000",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "100",
    "cashEquivTotalAmount": "500",
    "customerNPOfflineAmount": "0",
    "customerNPTotalAmount": "0",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "400",
    "posTotalAmount": "3000",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  }
}
```

#### Response

**HTTP Code:** **HTTP Code:** 200 OK

```
{
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "dailyLimits": {
    "nonExpiring": false,
    "limitExpirationDate": "2024-12-31",
    "limitType": "OVERRIDE",
    "aggregateOfflineAmount": "0",
    "aggregateTotalAmount": "0",
    "atmOfflineAmount": "200",
    "atmTotalAmount": "2000",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "100",
    "cashEquivTotalAmount": "500",
    "customerNPOfflineAmount": "0",
    "customerNPTotalAmount": "0",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "400",
    "posTotalAmount": "3000",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  }
}
```

### Debit Limits v2: Update open to buy limits using card number

Update the open to buy limits for the selected cardholder record.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/openToBuy

```
{
  "cardNumber": "4000200030004000",
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "123",
    "accountOpenToBuyTotalAmount": "9999",
    "cardOpenToBuyOfflineAmount": "123",
    "cardOpenToBuyTotalAmount": "9999"
  }
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "400020XXXXXX4000",
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "123",
    "accountOpenToBuyTotalAmount": "9999",
    "cardOpenToBuyOfflineAmount": "123",
    "cardOpenToBuyTotalAmount": "9999"
  }
}
```

### Debit Limits v2: Update open to buy limits using NTT

Update the open to buy limits for the selected cardholder record

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/openToBuy

```
{
  "nonTransToken": "piUVBJKZGfks4000",
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "123",
    "accountOpenToBuyTotalAmount": "9999",
    "cardOpenToBuyOfflineAmount": "123",
    "cardOpenToBuyTotalAmount": "9999"
  }
}
```

#### Response

**HTTP Code:** 200 OK

```{
  "cardNumber": "400020XXXXXX4000",
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "123",
    "accountOpenToBuyTotalAmount": "9999",
    "cardOpenToBuyOfflineAmount": "123",
    "cardOpenToBuyTotalAmount": "9999"
  }
}
```

### Debit Limits v2: Update open to buy limits using card number, token only response format

Update the open to buy limits for the selected cardholder record.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/openToBuy

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "TOKEN_ONLY",
  "memberNumber": "0",
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "123",
    "accountOpenToBuyTotalAmount": "9999",
    "cardOpenToBuyOfflineAmount": "123",
    "cardOpenToBuyTotalAmount": "9999"
  }
}
```

#### Response

**HTTP Code**: 200 OK

```{
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "123",
    "accountOpenToBuyTotalAmount": "9999",
    "cardOpenToBuyOfflineAmount": "123",
    "cardOpenToBuyTotalAmount": "9999"
  }
}
```

### Debit Limits v2: Update open to buy limits using card number, full card only response format

Update the open to buy limits for the selected cardholder record.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/openToBuy

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "FULL_CARD_ONLY",
  "memberNumber": "0",
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "123",
    "accountOpenToBuyTotalAmount": "9999",
    "cardOpenToBuyOfflineAmount": "123",
    "cardOpenToBuyTotalAmount": "9999"
  }
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "4000200030004000",
  "memberNumber": "0",
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "123",
    "accountOpenToBuyTotalAmount": "9999",
    "cardOpenToBuyOfflineAmount": "123",
    "cardOpenToBuyTotalAmount": "9999"
  }
}
```

### Debit Limits v2: Update open to buy limits using card number, full card and token response format

Update the open to buy limits for the selected cardholder record

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/openToBuy

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "FULL_CARD_AND_TOKEN",
  "memberNumber": "0",
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "123",
    "accountOpenToBuyTotalAmount": "9999",
    "cardOpenToBuyOfflineAmount": "123",
    "cardOpenToBuyTotalAmount": "9999"
  }
}
```

#### Response

**HTTP Code:** 200 OK

```{
  "cardNumber": "4000200030004000",
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "123",
    "accountOpenToBuyTotalAmount": "9999",
    "cardOpenToBuyOfflineAmount": "123",
    "cardOpenToBuyTotalAmount": "9999"
  }
}
```

### Debit Limits v2: Update open to buy limits using card number, masked card only response format

Update the open to buy limits for the selected cardholder record

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/openToBuy

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "MASKED_CARD_ONLY",
  "memberNumber": "0"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "cardNumber": "400020XXXXXX4000",
   "memberNumber": "0",
   "dailyLimits": {
      "limitType": "CARD_CLASS",
      "aggregateOfflineAmount": "500",
      "aggregateTotalAmount": "2500",
      "atmOfflineAmount": "300",
      "atmTotalAmount": "600",
      "cashAdvanceOfflineAmount": "0",
      "cashAdvanceTotalAmount": "0",
      "cashEquivOfflineAmount": "5",
      "cashEquivTotalAmount": "10",
      "customerNPOfflineAmount": "500",
      "customerNPTotalAmount": "1500",
      "dayOfDepositAvailabilityTotalAmount": "0",
      "mtCreditDlyCntOffline": "0",
      "mtCreditDlyCntTotal": "0",
      "mtCreditDlyOfflineAmount": "0",
      "mtCreditDlyTotalAmount": "0",
      "mtCreditPerTranOfflineAmount": "0",
      "mtCreditPerTranTotalAmount": "0",
      "mtFundingAmtPerTranOfflineAmount": "0",
      "mtFundingAmtPerTranTotalAmount": "0",
      "mtFundingDlyCntOffline": "0",
      "mtFundingDlyCntTotal": "0",
      "mtFundingDlyOfflineAmount": "0",
      "mtFundingDlyTotalAmount": "0",
      "posOfflineAmount": "500",
      "posTotalAmount": "2500",
      "signatureDebitPOSOfflineAmount": "0",
      "signatureDebitPOSTotalAmount": "0"
   },
   "openToBuyLimits": {
      "accountOpenToBuyOfflineAmount": "0",
      "accountOpenToBuyTotalAmount": "0",
      "cardOpenToBuyOfflineAmount": "123",
      "cardOpenToBuyTotalAmount": "9999"
   },
   "velocityLimits": {
      "aggMaxCardUsage": "0",
      "aggTimeInterval": "00:00",
      "atmMaxCardUsage": "0",
      "atmTimeInterval": "00:00",
      "cashEquivMaxCardUsage": "0",
      "cashEquivTimeInterval": "00:00",
      "posMaxCardUsage": "0",
      "posTimeInterval": "00:00"
   }
}
```

### Debit Limits v2: Update open to buy limits using card number, masked card and token response format

Update the open to buy limits for the selected cardholder record.

#### Request

**HTTP Method**: PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/openToBuy

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "MASKED_CARD_AND_TOKEN",
  "memberNumber": "0",
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "cardNumber": "400020XXXXXX4000",
   "nonTransToken": "piUVBJKZGfks4000",
   "memberNumber": "0",
   "dailyLimits": {
      "limitType": "CARD_CLASS",
      "aggregateOfflineAmount": "500",
      "aggregateTotalAmount": "2500",
      "atmOfflineAmount": "300",
      "atmTotalAmount": "600",
      "cashAdvanceOfflineAmount": "0",
      "cashAdvanceTotalAmount": "0",
      "cashEquivOfflineAmount": "5",
      "cashEquivTotalAmount": "10",
      "customerNPOfflineAmount": "500",
      "customerNPTotalAmount": "1500",
      "dayOfDepositAvailabilityTotalAmount": "0",
      "mtCreditDlyCntOffline": "0",
      "mtCreditDlyCntTotal": "0",
      "mtCreditDlyOfflineAmount": "0",
      "mtCreditDlyTotalAmount": "0",
      "mtCreditPerTranOfflineAmount": "0",
      "mtCreditPerTranTotalAmount": "0",
      "mtFundingAmtPerTranOfflineAmount": "0",
      "mtFundingAmtPerTranTotalAmount": "0",
      "mtFundingDlyCntOffline": "0",
      "mtFundingDlyCntTotal": "0",
      "mtFundingDlyOfflineAmount": "0",
      "mtFundingDlyTotalAmount": "0",
      "posOfflineAmount": "500",
      "posTotalAmount": "2500",
      "signatureDebitPOSOfflineAmount": "0",
      "signatureDebitPOSTotalAmount": "0"
   },
   "openToBuyLimits": {
      "accountOpenToBuyOfflineAmount": "0",
      "accountOpenToBuyTotalAmount": "0",
      "cardOpenToBuyOfflineAmount": "123",
      "cardOpenToBuyTotalAmount": "9999"
   },
   "velocityLimits": {
      "aggMaxCardUsage": "0",
      "aggTimeInterval": "00:00",
      "atmMaxCardUsage": "0",
      "atmTimeInterval": "00:00",
      "cashEquivMaxCardUsage": "0",
      "cashEquivTimeInterval": "00:00",
      "posMaxCardUsage": "0",
      "posTimeInterval": "00:00"
   }
}
```

### Debit Limits v2: Update velocity limits using NTT

Updates the velocity limits for the selected cardholder record.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/velocity

```
{
  "nonTransToken": "piUVBJKZGfks4000",
  "velocityLimits": {
    "aggMaxCardUsage": "20",
    "aggTimeInterval": "10:10",
    "atmMaxCardUsage": "20",
    "atmTimeInterval": "10:10",
    "cashEquivMaxCardUsage": "4",
    "cashEquivTimeInterval": "10:10",
    "posMaxCardUsage": "4",
    "posTimeInterval": "10:10"
  }
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "400020XXXXXX4000",
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "velocityLimits": {
    "aggMaxCardUsage": "20",
    "aggTimeInterval": "10:10",
    "atmMaxCardUsage": "20",
    "atmTimeInterval": "10:10",
    "cashEquivMaxCardUsage": "4",
    "cashEquivTimeInterval": "10:10",
    "posMaxCardUsage": "4",
    "posTimeInterval": "10:10"
  }
}
```

### Debit Limits v2: Update velocity limits using card number, token only response format

Updates the velocity limits for the selected cardholder record.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/velocity

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "TOKEN_ONLY",
  "memberNumber": "0",
  "velocityLimits": {
    "aggMaxCardUsage": "20",
    "aggTimeInterval": "10:10",
    "atmMaxCardUsage": "20",
    "atmTimeInterval": "10:10",
    "cashEquivMaxCardUsage": "4",
    "cashEquivTimeInterval": "10:10",
    "posMaxCardUsage": "4",
    "posTimeInterval": "10:10"
  }
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "velocityLimits": {
    "aggMaxCardUsage": "20",
    "aggTimeInterval": "10:10",
    "atmMaxCardUsage": "20",
    "atmTimeInterval": "10:10",
    "cashEquivMaxCardUsage": "4",
    "cashEquivTimeInterval": "10:10",
    "posMaxCardUsage": "4",
    "posTimeInterval": "10:10"
  }
}
```

### Debit Limits v2: Update velocity limits using card number, full card only response format

Updates the velocity limits for the selected cardholder record.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/velocity

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "FULL_CARD_ONLY",
  "memberNumber": "0",
  "velocityLimits": {
    "aggMaxCardUsage": "20",
    "aggTimeInterval": "10:10",
    "atmMaxCardUsage": "20",
    "atmTimeInterval": "10:10",
    "cashEquivMaxCardUsage": "4",
    "cashEquivTimeInterval": "10:10",
    "posMaxCardUsage": "4",
    "posTimeInterval": "10:10"
  }
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "4000200030004000",
  "memberNumber": "0",
  "velocityLimits": {
    "aggMaxCardUsage": "20",
    "aggTimeInterval": "10:10",
    "atmMaxCardUsage": "20",
    "atmTimeInterval": "10:10",
    "cashEquivMaxCardUsage": "4",
    "cashEquivTimeInterval": "10:10",
    "posMaxCardUsage": "4",
    "posTimeInterval": "10:10"
  }
}
```

### Debit Limits v2: Update velocity limits using card number, full card and token response format

Updates the velocity limits for the selected cardholder record.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/velocity

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "FULL_CARD_AND_TOKEN",
  "memberNumber": "0",
  "velocityLimits": {
    "aggMaxCardUsage": "20",
    "aggTimeInterval": "10:10",
    "atmMaxCardUsage": "20",
    "atmTimeInterval": "10:10",
    "cashEquivMaxCardUsage": "4",
    "cashEquivTimeInterval": "10:10",
    "posMaxCardUsage": "4",
    "posTimeInterval": "10:10"
  }
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "4000200030004000",
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "velocityLimits": {
    "aggMaxCardUsage": "20",
    "aggTimeInterval": "10:10",
    "atmMaxCardUsage": "20",
    "atmTimeInterval": "10:10",
    "cashEquivMaxCardUsage": "4",
    "cashEquivTimeInterval": "10:10",
    "posMaxCardUsage": "4",
    "posTimeInterval": "10:10"
  }
}
```

### Debit Limits v2: Update velocity limits using card number, masked card only response format

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/velocity

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "MASKED_CARD_ONLY",
  "memberNumber": "0",
 }
```

#### Response

**HTTP Code:** 200 OK

```
{
   "cardNumber": "400020XXXXXX4000",
   "memberNumber": "0",
   "dailyLimits": {
      "nonExpiring": false,
      "limitExpirationDate": "2024-12-31",
      "limitType": "OVERRIDE",
      "aggregateOfflineAmount": "500",
      "aggregateTotalAmount": "2500",
      "atmOfflineAmount": "300",
      "atmTotalAmount": "600",
      "cashAdvanceOfflineAmount": "0",
      "cashAdvanceTotalAmount": "0",
      "cashEquivOfflineAmount": "2",
      "cashEquivTotalAmount": "10",
      "customerNPOfflineAmount": "500",
      "customerNPTotalAmount": "1500",
      "dayOfDepositAvailabilityTotalAmount": "0",
      "mtCreditDlyCntOffline": "0",
      "mtCreditDlyCntTotal": "0",
      "mtCreditDlyOfflineAmount": "0",
      "mtCreditDlyTotalAmount": "0",
      "mtCreditPerTranOfflineAmount": "0",
      "mtCreditPerTranTotalAmount": "0",
      "mtFundingAmtPerTranOfflineAmount": "0",
      "mtFundingAmtPerTranTotalAmount": "0",
      "mtFundingDlyCntOffline": "0",
      "mtFundingDlyCntTotal": "0",
      "mtFundingDlyOfflineAmount": "0",
      "mtFundingDlyTotalAmount": "0",
      "posOfflineAmount": "500",
      "posTotalAmount": "2500",
      "signatureDebitPOSOfflineAmount": "0",
      "signatureDebitPOSTotalAmount": "0"
   },
   "openToBuyLimits": {
      "accountOpenToBuyOfflineAmount": "0",
      "accountOpenToBuyTotalAmount": "0",
      "cardOpenToBuyOfflineAmount": "0",
      "cardOpenToBuyTotalAmount": "0"
   },
   "velocityLimits": {
      "aggMaxCardUsage": "0",
      "aggTimeInterval": "00:00",
      "atmMaxCardUsage": "0",
      "atmTimeInterval": "00:00",
      "cashEquivMaxCardUsage": "0",
      "cashEquivTimeInterval": "00:00",
      "posMaxCardUsage": "0",
      "posTimeInterval": "00:00"
   }
}
```

### Debit Limits v2: Update velocity limits using card number, masked card and token response format

Updates the velocity limits for the selected cardholder record.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/velocity

```
{
   "cardNumber": "4000200030004000",
   "responseFormat": "MASKED_CARD_AND_TOKEN",
   "memberNumber": "0"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "400020XXXXXX4000",
   "nonTransToken": "piUVBJKZGfks4000",
   "memberNumber": "0",
   "dailyLimits": {
      "nonExpiring": false,
      "limitExpirationDate": "2024-12-31",
      "limitType": "OVERRIDE",
      "aggregateOfflineAmount": "500",
      "aggregateTotalAmount": "2500",
      "atmOfflineAmount": "300",
      "atmTotalAmount": "600",
      "cashAdvanceOfflineAmount": "0",
      "cashAdvanceTotalAmount": "0",
      "cashEquivOfflineAmount": "2",
      "cashEquivTotalAmount": "10",
      "customerNPOfflineAmount": "500",
      "customerNPTotalAmount": "1500",
      "dayOfDepositAvailabilityTotalAmount": "0",
      "mtCreditDlyCntOffline": "0",
      "mtCreditDlyCntTotal": "0",
      "mtCreditDlyOfflineAmount": "0",
      "mtCreditDlyTotalAmount": "0",
      "mtCreditPerTranOfflineAmount": "0",
      "mtCreditPerTranTotalAmount": "0",
      "mtFundingAmtPerTranOfflineAmount": "0",
      "mtFundingAmtPerTranTotalAmount": "0",
      "mtFundingDlyCntOffline": "0",
      "mtFundingDlyCntTotal": "0",
      "mtFundingDlyOfflineAmount": "0",
      "mtFundingDlyTotalAmount": "0",
      "posOfflineAmount": "500",
      "posTotalAmount": "2500",
      "signatureDebitPOSOfflineAmount": "0",
      "signatureDebitPOSTotalAmount": "0"
   },
   "openToBuyLimits": {
      "accountOpenToBuyOfflineAmount": "0",
      "accountOpenToBuyTotalAmount": "0",
      "cardOpenToBuyOfflineAmount": "0",
      "cardOpenToBuyTotalAmount": "0"
   },
   "velocityLimits": {
      "aggMaxCardUsage": "0",
      "aggTimeInterval": "00:00",
      "atmMaxCardUsage": "0",
      "atmTimeInterval": "00:00",
      "cashEquivMaxCardUsage": "0",
      "cashEquivTimeInterval": "00:00",
      "posMaxCardUsage": "0",
      "posTimeInterval": "00:00"
   }
}
```

### Debit Limits v2: Set to default limits using card number

Sets the cardholder limits to default values per card class.

#### Request

**HTTP Method:** PUT

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/default

```
{
  "cardNumber": "4000200030004000"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "400020XXXXXX4000",
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "dailyLimits": {
    "limitType": "CARD_CLASS",
    "aggregateOfflineAmount": "500",
    "aggregateTotalAmount": "2500",
    "atmOfflineAmount": "300",
    "atmTotalAmount": "600",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "5",
    "cashEquivTotalAmount": "10",
    "customerNPOfflineAmount": "500",
    "customerNPTotalAmount": "1500",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "500",
    "posTotalAmount": "2500",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  },
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "0",
    "accountOpenToBuyTotalAmount": "0",
    "cardOpenToBuyOfflineAmount": "123",
    "cardOpenToBuyTotalAmount": "9999"
  },
  "velocityLimits": {
    "aggMaxCardUsage": "0",
    "aggTimeInterval": "00:00",
    "atmMaxCardUsage": "0",
    "atmTimeInterval": "00:00",
    "cashEquivMaxCardUsage": "0",
    "cashEquivTimeInterval": "00:00",
    "posMaxCardUsage": "0",
    "posTimeInterval": "00:00"
  }
}
```

### Debit Limits v2: Set to default limits using NTT

Sets the cardholder limits to default values per card class.

#### Request

**HTTP Method:** PUT

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/default

```
{
  "nonTransToken": "piUVBJKZGfks4000"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "400020XXXXXX4000",
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "dailyLimits": {
    "limitType": "CARD_CLASS",
    "aggregateOfflineAmount": "500",
    "aggregateTotalAmount": "2500",
    "atmOfflineAmount": "300",
    "atmTotalAmount": "600",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "5",
    "cashEquivTotalAmount": "10",
    "customerNPOfflineAmount": "500",
    "customerNPTotalAmount": "1500",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "500",
    "posTotalAmount": "2500",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  },
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "0",
    "accountOpenToBuyTotalAmount": "0",
    "cardOpenToBuyOfflineAmount": "123",
    "cardOpenToBuyTotalAmount": "9999"
  },
  "velocityLimits": {
    "aggMaxCardUsage": "0",
    "aggTimeInterval": "00:00",
    "atmMaxCardUsage": "0",
    "atmTimeInterval": "00:00",
    "cashEquivMaxCardUsage": "0",
    "cashEquivTimeInterval": "00:00",
    "posMaxCardUsage": "0",
    "posTimeInterval": "00:00"
  }
}
```

### Debit Limits v2: Set to default limits using card number, token only response format

Sets the cardholder limits to default values per card class.

#### Request

**HTTP Method:** PUT

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/default

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "TOKEN_ONLY",
  "memberNumber": "0"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "dailyLimits": {
    "limitType": "CARD_CLASS",
    "aggregateOfflineAmount": "500",
    "aggregateTotalAmount": "2500",
    "atmOfflineAmount": "300",
    "atmTotalAmount": "600",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "5",
    "cashEquivTotalAmount": "10",
    "customerNPOfflineAmount": "500",
    "customerNPTotalAmount": "1500",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "500",
    "posTotalAmount": "2500",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  },
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "0",
    "accountOpenToBuyTotalAmount": "0",
    "cardOpenToBuyOfflineAmount": "123",
    "cardOpenToBuyTotalAmount": "9999"
  },
  "velocityLimits": {
    "aggMaxCardUsage": "0",
    "aggTimeInterval": "00:00",
    "atmMaxCardUsage": "0",
    "atmTimeInterval": "00:00",
    "cashEquivMaxCardUsage": "0",
    "cashEquivTimeInterval": "00:00",
    "posMaxCardUsage": "0",
    "posTimeInterval": "00:00"
  }
}
```

### Debit Limits v2: Set to default limits card number, full card only response format

Sets the cardholder limits to default values per card class.

#### Request

**HTTP Method:** PUT

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/default

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "FULL_CARD_ONLY",
  "memberNumber": "0"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "4000200030004000",
  "memberNumber": "0",
  "dailyLimits": {
    "limitType": "CARD_CLASS",
    "aggregateOfflineAmount": "500",
    "aggregateTotalAmount": "2500",
    "atmOfflineAmount": "300",
    "atmTotalAmount": "600",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "5",
    "cashEquivTotalAmount": "10",
    "customerNPOfflineAmount": "500",
    "customerNPTotalAmount": "1500",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "500",
    "posTotalAmount": "2500",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  },
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "0",
    "accountOpenToBuyTotalAmount": "0",
    "cardOpenToBuyOfflineAmount": "123",
    "cardOpenToBuyTotalAmount": "9999"
  },
  "velocityLimits": {
    "aggMaxCardUsage": "0",
    "aggTimeInterval": "00:00",
    "atmMaxCardUsage": "0",
    "atmTimeInterval": "00:00",
    "cashEquivMaxCardUsage": "0",
    "cashEquivTimeInterval": "00:00",
    "posMaxCardUsage": "0",
    "posTimeInterval": "00:00"
  }
}
```

### Debit Limits v2: Set to default limits using card number, full card and token response format

Sets the cardholder limits to default values per card class.

#### Request

**HTTP Method:** PUT

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/default

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "FULL_CARD_AND_TOKEN",
  "memberNumber": "0"
}
```

#### Response

**HTTP Code:** 200 OK

```{
  "cardNumber": "4000200030004000",
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "dailyLimits": {
    "limitType": "CARD_CLASS",
    "aggregateOfflineAmount": "500",
    "aggregateTotalAmount": "2500",
    "atmOfflineAmount": "300",
    "atmTotalAmount": "600",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "5",
    "cashEquivTotalAmount": "10",
    "customerNPOfflineAmount": "500",
    "customerNPTotalAmount": "1500",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "500",
    "posTotalAmount": "2500",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  },
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "0",
    "accountOpenToBuyTotalAmount": "0",
    "cardOpenToBuyOfflineAmount": "123",
    "cardOpenToBuyTotalAmount": "9999"
  },
  "velocityLimits": {
    "aggMaxCardUsage": "0",
    "aggTimeInterval": "00:00",
    "atmMaxCardUsage": "0",
    "atmTimeInterval": "00:00",
    "cashEquivMaxCardUsage": "0",
    "cashEquivTimeInterval": "00:00",
    "posMaxCardUsage": "0",
    "posTimeInterval": "00:00"
  }
}
```

### Debit Limits v2: Set to default limits using card number, masked card only response format

Sets the cardholder limits to default values per card class.

#### Request

**HTTP Method:** PUT

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/default

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "MASKED_CARD_ONLY",
  "memberNumber": "0"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "400020XXXXXX4000",
  "memberNumber": "0",
  "dailyLimits": {
    "limitType": "CARD_CLASS",
    "aggregateOfflineAmount": "500",
    "aggregateTotalAmount": "2500",
    "atmOfflineAmount": "300",
    "atmTotalAmount": "600",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "5",
    "cashEquivTotalAmount": "10",
    "customerNPOfflineAmount": "500",
    "customerNPTotalAmount": "1500",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "500",
    "posTotalAmount": "2500",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  },
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "0",
    "accountOpenToBuyTotalAmount": "0",
    "cardOpenToBuyOfflineAmount": "123",
    "cardOpenToBuyTotalAmount": "9999"
  },
  "velocityLimits": {
    "aggMaxCardUsage": "0",
    "aggTimeInterval": "00:00",
    "atmMaxCardUsage": "0",
    "atmTimeInterval": "00:00",
    "cashEquivMaxCardUsage": "0",
    "cashEquivTimeInterval": "00:00",
    "posMaxCardUsage": "0",
    "posTimeInterval": "00:00"
  }
}
```

### Debit Limits v2: Set to default limits using card number, masked card and token response format

Sets the cardholder limits to default values per card class.

#### Request

**HTTP Method:** PUT

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/limits/default

```
{
  "cardNumber": "4000200030004000",
  "responseFormat": "MASKED_CARD_AND_TOKEN",
  "memberNumber": "0"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "400020XXXXXX4000",
  "nonTransToken": "piUVBJKZGfks4000",
  "memberNumber": "0",
  "dailyLimits": {
    "limitType": "CARD_CLASS",
    "aggregateOfflineAmount": "500",
    "aggregateTotalAmount": "2500",
    "atmOfflineAmount": "300",
    "atmTotalAmount": "600",
    "cashAdvanceOfflineAmount": "0",
    "cashAdvanceTotalAmount": "0",
    "cashEquivOfflineAmount": "5",
    "cashEquivTotalAmount": "10",
    "customerNPOfflineAmount": "500",
    "customerNPTotalAmount": "1500",
    "dayOfDepositAvailabilityTotalAmount": "0",
    "mtCreditDlyCntOffline": "0",
    "mtCreditDlyCntTotal": "0",
    "mtCreditDlyOfflineAmount": "0",
    "mtCreditDlyTotalAmount": "0",
    "mtCreditPerTranOfflineAmount": "0",
    "mtCreditPerTranTotalAmount": "0",
    "mtFundingAmtPerTranOfflineAmount": "0",
    "mtFundingAmtPerTranTotalAmount": "0",
    "mtFundingDlyCntOffline": "0",
    "mtFundingDlyCntTotal": "0",
    "mtFundingDlyOfflineAmount": "0",
    "mtFundingDlyTotalAmount": "0",
    "posOfflineAmount": "500",
    "posTotalAmount": "2500",
    "signatureDebitPOSOfflineAmount": "0",
    "signatureDebitPOSTotalAmount": "0"
  },
  "openToBuyLimits": {
    "accountOpenToBuyOfflineAmount": "0",
    "accountOpenToBuyTotalAmount": "0",
    "cardOpenToBuyOfflineAmount": "123",
    "cardOpenToBuyTotalAmount": "9999"
  },
  "velocityLimits": {
    "aggMaxCardUsage": "0",
    "aggTimeInterval": "00:00",
    "atmMaxCardUsage": "0",
    "atmTimeInterval": "00:00",
    "cashEquivMaxCardUsage": "0",
    "cashEquivTimeInterval": "00:00",
    "posMaxCardUsage": "0",
    "posTimeInterval": "00:00"
  }
}
```
