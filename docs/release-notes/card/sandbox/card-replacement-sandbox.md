# Test Cases

<span style="color:#ff6600;">**Card API Endpoints**</span>

When testing these endpoints, please use the test cases and test data from the Sandbox.

## Replacement

### Credit Replacement v3: Replace card using card number

Change the expiration date and create a replacement order for an existing cardholder record.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com /cs/v3/cards/replacement

```
{
      "cardNumber": "4000200030004001",
   "cardholderName": "Doe, John H",
   "creditOnly": {
      "cardStock": "00",
      "specialHandling": "NONE",
      "waiveReplacementFee": "Y",
      "cardholder": {
         "personalizedEmbossingText": "Home Team",
         "customerRoleTypeCode": "01"
      }
   }
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
  "cardNumber": "400020XXXXXX4001",
   "nonTransToken": "pSAZIXCAXrAo4001",
   "cardholderName": "Doe, John H",
   "creditOnly": {
      "cardStock": "00",
      "specialHandling": "NONE",
      "waiveReplacementFee": "Y",
      "cardholder": {
         "personalizedEmbossingText": "Home Team",
         "customerRoleTypeCode": "01"
          }
      }
  }
```

### Credit Replacement v1: Instant Issuance using card number, full card only format

Change the expiration date on the selected cardholder record for an instant issue plastic.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/instantIssuance

```
{
   "cardNumber": "4000200030004001",
   "nonTransToken": "pSAZIXCAXrAo4001",
   "responseFormat": "FULL_CARD_ONLY",
   "cardholderName": "Doe, John H",
   "creditOnly": {
      "cardholder": {
         "personalizedEmbossingText": "Home Team",
         "customerRoleTypeCode": "01"
      }
   }
 }
```

#### Response

**HTTP Code**: 200 OK

```
{
  "cardNumber": "4000200030004001",
   "cardholderName": "Doe, John H",
   "creditOnly": {
      "cardholder": {
         "personalizedEmbossingText": "Home Team",
         "customerRoleTypeCode": "01"
      }
   }
 }
```

### Debit Replacement v3: Replace card using NTT

Change the expiration date and create a replacement order for an existing cardholder record.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com /cs/v3/cards/replacement

```
{
   "nonTransToken": "piUVBJKZGfks4000",
   "cardholderName": "Doe, John H",
   "debitOnly": {
      "order": {
         "addressType": "PRIMARY",
         "orderType": "CARD",
         "rushType": "NONE"
      },
      "cardholder": {
         "expirationDate": "10/28",
         "nameSuffix": "MD",
         "photoId": "EFGH",
         "plasticId": "PM001",
         "additionalEmbossLine": "Home Team"
      }
   }
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "cardNumber": "400020XXXXXX4000",
   "nonTransToken": "piUVBJKZGfks4000",
   "cardholderName": "Doe, John H",
   "debitOnly": {
      "memberNumber": "0",
      "order": {
         "addressType": "PRIMARY",
         "rushType": "NONE",
         "orderType": "CARD"
      },
      "cardholder": {
         "expirationDate": "10/28",
         "nameSuffix": "MD",
         "photoId": "EFGH",
         "plasticId": "PM001",
         "additionalEmbossLine": "Home Team"
      }
   }
}
```

### Debit Replacement v3: Replace card using card number

Change the expiration date and create a replacement order for an existing cardholder record.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/v3/cards/replacement

```
{
   "cardNumber": "4000200030004000",
   "cardholderName": "Doe, John H",
   "debitOnly": {
      "memberNumber": "0",
      "order": {
         "addressType": "PRIMARY",
         "orderType": "CARD",
         "rushType": "NONE"
      },
      "cardholder": {
         "expirationDate": "10/28",
         "nameSuffix": "MD",
         "photoId": "EFGH",
         "plasticId": "PM001",
         "additionalEmbossLine": "Home Team"
      }
   }
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
   "cardNumber": "400020XXXXXX4000",
   "cardholderName": "Doe, John H",
   "debitOnly": {
      "memberNumber": "0",
      "order": {
         "addressType": "PRIMARY",
         "rushType": "NONE",
         "orderType": "CARD"
      },
      "cardholder": {
         "expirationDate": "10/28",
         "nameSuffix": "MD",
         "photoId": "EFGH",
         "plasticId": "PM001",
         "additionalEmbossLine": "Home Team"
      }
   }
  }
```

### Debit Replacement v1: Instant Issuance using NTT, no response format

Change the expiration date on the selected cardholder record for an instant issue plastic.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/instantIssuance

```{
  "nonTransToken": "piUVBJKZGfks4000",
   "cardholderName": "Doe, John H",
   "debitOnly": {
      "cardholder": {
         "expirationDate": "10/28",
         "nameSuffix": "MD",
         "additionalEmbossLine": "Home Team"
      }
   }
 }
```

#### Response

**HTTP Code:** 200 OK

```
{
   "cardNumber": "400020XXXXXX4000",
   "nonTransToken": "piUVBJKZGfks4000",
   "cardholderName": "Doe, John H",
   "debitOnly": {
      "memberNumber": "0",
      "cardholder": {
         "expirationDate": "10/28",
         "nameSuffix": "MD",
         "additionalEmbossLine": "Home Team"
      }
   }
 }
```

### Debit Replacement v1: Instant Issuance using card number, full card only format

Change the expiration date on the selected cardholder record for an instant issue plastic.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/instantIssuance

```
{
  "cardNumber": "4000200030004000",
   "responseFormat": "FULL_CARD_ONLY",
   "cardholderName": "Doe, John H",
   "debitOnly": {
      "memberNumber": "0",
      "cardholder": {
         "expirationDate": "10/28",
         "nameSuffix": "MD",
         "additionalEmbossLine": "Home Team"
      }
   }
 }
```

#### Response

**HTTP Code:** 200 OK

```
{
   "cardNumber": "4000200030004000",
   "cardholderName": "Doe, John H",
   "debitOnly": {
      "memberNumber": "0",
      "cardholder": {
         "expirationDate": "10/28",
         "nameSuffix": "MD",
         "additionalEmbossLine": "Home Team"
      }
   }
}
```
