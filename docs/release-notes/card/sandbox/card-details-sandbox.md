# Test Cases

<span style="color:#ff6600;">**Card API Endpoints**</span>

When testing these endpoints, please use the test cases and test data from the Sandbox.

## Details

### Credit Details v3: Update additional information using card number

This case updates the additional information using card number.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cardholders/additionalInfo

```
{
        "cardNumber": "4000200030004001",
        "creditAdditionalInfo": {
            "prefix": "DR.",
            "cardholderName": "Doe, John H",
            "association": "PRIMARY",
            "vip": true,
            "gender": "MALE",
            "dateOfBirth": "1990-08-24",
            "employeeCode": true,
            "motherMaidenName": "Smith",
            "taxIdOrSsn": "123005678",
            "ein": "123005678",
            "dnaPersonId": "123005678",
            "isDeceased": false,
            "memoLine1": "This is an example added to a cardholder record.",
            "memoLine2": "Customer requested name change, updating contact information on account",
            "employerName": "Fiserv",
            "personalizedEmbossingText": "Home Team",
            "duplicateStatementsSecondary": false,
            "duplicateLettersSecondary": false,
            "specialHandling": "NONE",
            "memberSinceDate": "03/22"
        }
  }
```

#### Response

**HTTP Code:** 204 No Content

### Credit Details v1: Search additional information using card number

This case retrieves the additional information using card number.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cardholders/additionalInfo/search

```
{
      "cardNumber": "4000200030004001"
 }
```

#### Response

**HTTP Code:** 200 OK

```
{

      "cardNumber": "400020XXXXXX4001",
      "cardClass": "AAA00",
      "creditAdditionalInfo": {
          "accountNumber": "123456789",
          "externalCustomerId": "XXXXX6789",
          "prefix": "DR",
          "cardholderName": "Doe, John H",
          "association": "PRIMARY",
          "vip": true,
          "gender": "NOT_SPECIFIED",
          "dateOfBirth": "1990-08-24",
          "employeeCode": true,
          "motherMaidenName": "Smith",
          "empId": "123005678",
          "taxIdOrSsn": "XXXXX5678",
          "ein": "XXXXX5678",
          "dnaPersonId": "123005678",
          "isDeceased": false,
          "memoLine1": "This is an example added to a cardholder record.",
          "memoLine2": "Customer requested name change, updating contact information on account.",
          "employerName": "Fiserv",
          "personalizedEmbossingText": "Home Team",
          "duplicateStatementsSecondary": false,
          "duplicateLettersSecondary": false,
          "specialHandling": "NONE",
          "memberSinceDate": "03/22"
      }
}
```

### Debit Details v3: Update additional information using card number

This case updated the additional information using card number.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cardholders/additionalInfo

```
{

      "cardNumber": "4000200030004000",
      "debitAdditionalInfo": {
          "memberNumber": "0",
          "memberSinceDate": "03/22",
          "dateOfBirth": "1990-08-24",
          "motherMaidenName": "Smith",
          "taxIdOrSsn": "123005678",
          "verificationText": "My name is John",
          "callerId": "1005550001",
          "updateNameDetails": [
              {
                  "cardholderName": "Doe, John H",
                  "priorCardholderName": "Doe, Alex M",
                  "nameSuffix": "MD",
                  "additionalEmbossLine": "Home Team",
                  "photoId": "EFGH",
                  "plasticId": "PM001"
              }
          ]
      }
  }
```

#### Response

**HTTP Code:** 204 No Content

### Debit Details v3: Update additional information using NTT

This case updated the additional information using NTT.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cardholders/additionalInfo

```
{
      "nonTransToken": "piUVBJKZGfks4000",
      "debitAdditionalInfo": {
          "memberNumber": "0",
          "memberSinceDate": "03/22",
          "dateOfBirth": "1990-08-24",
          "motherMaidenName": "Smith",
          "taxIdOrSsn": "123005678",
          "verificationText": "My name is John",
          "callerId": "1005550001",
          "updateNameDetails": [
              {
                  "cardholderName": "Doe, John H",
                  "priorCardholderName": "Doe, Alex M",
                  "nameSuffix": "MD",
                  "additionalEmbossLine": "Home Team",
                  "photoId": "EFGH",
                  "plasticId": "PM001"
              }
          ]
      }
  }
```

#### Response

**HTTP Code**: 204 No Content

### Debit Details v1: Search additional information using card number

This case retrieves the additional information using card number.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cardholders/additionalInfo/search

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
      "cardNumber": "400020XXXXXX4000",
      "nonTransToken": "piUVBJKZGfks4000",
      "cardClass": "AAA00",
      "debitAdditionalInfo": {
          "accountNumber": "123456789",
          "memberNumber": "0",
          "memberSinceDate": "03/22",
          "dateOfBirth": "1990-08-24",
          "motherMaidenName": "Smith",
          "taxIdOrSsn": "XXXXX5678",
          "verificationText": "Driver's license",
          "callerId": "1005550001",
          "updateNameDetails": [
              {
                  "cardholderName": "Doe, John H",
                  "priorCardholderName": "Doe, Alex M",
                  "nameSuffix": "MD",
                  "additionalEmbossLine": "Home Team",
                  "photoId": "EFGH",
                  "plasticId": "PM001"
              }
          ]
      }
  }
```

### Debit Details v1: Search additional information using NTT

This case retrieves the additional information using NTT.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cardholders/additionalInfo/search

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
    "cardClass": "AAA00",
    "debitAdditionalInfo": {
        "accountNumber": "123456789",
        "memberNumber": "0",
        "memberSinceDate": "03/22",
        "dateOfBirth": "1990-08-24",
        "motherMaidenName": "Smith",
        "taxIdOrSsn": "XXXXX5678",
        "verificationText": "Driver's license",
        "callerId": "1005550001",
        "updateNameDetails": [
            {
                "cardholderName": "Doe, John H",
                "priorCardholderName": "Doe, Alex M",
                "nameSuffix": "MD",
                "additionalEmbossLine": "Home Team",
                "photoId": "EFGH",
                "plasticId": "PM001"
            }
        ]
  }
```

### Debit Details v3: Update ATM preferences using NTT

This case updates the ATM Preferences using a NTT.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cards/atmPreferences

```
{
      "cardNumber": "4000200030004000",
      "atmPreferences": {
          "languageCode": "ENGLISH",
          "amount": 240,
          "accountType": "SAVINGS",
          "receiptOption": "ASK_ME"
      }
  }
```

#### Response

**HTTP Code:** 204 No Content

### Debit Details v3: Update ATM preferences using NTT

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v3/cards/atmPreferences

```
{
      "nonTransToken": "piUVBJKZGfks4000",
      "atmPreferences": {
          "languageCode": "ENGLISH",
          "amount": 240,
          "accountType": "SAVINGS",
          "receiptOption": "ASK_ME"
      }
  }
```

#### Response

**HTTP Code:** 204 No Content

### Debit Details v1: Search ATM preferences using card number

This case retrieves the ATM Preferences using a card number.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/atmPreferences/search

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
      "cardNumber": "400020XXXXXX4000",
      "nonTransToken": "piUVBJKZGfks4000",
      "memberNumber": "0",
      "atmPreferences": [
          {
              "language": "ENGLISH",
              "amount": "240",
              "accountType": "CHECKING",
              "receiptOption": "ASK_ME",
              "terminalOwnerId": "USER01",
              "sourceType": "A",
              "action": "UPDATE",
              "actionDateTime": "2014-10-02T15:01:23.045Z",
              "updatedBy": "USER01"
          }
      ]
  }
```

### Debit Details v1: Search ATM preferences using NTT

This case retrieves the ATM preferences using NTT.

#### Request

H**TTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/atmPreferences/search

```
{
      "nonTransToken": "piUVBJKZGfks4000",
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
      "cardNumber": "400020XXXXXX4000",
      "nonTransToken": "piUVBJKZGfks4000",
      "memberNumber": "0",
      "atmPreferences": [
          {
              "language": "ENGLISH",
              "amount": "240",
              "accountType": "CHECKING",
              "receiptOption": "ASK_ME",
              "terminalOwnerId": "USER01",
              "sourceType": "A",
              "action": "UPDATE",
              "actionDateTime": "2014-10-02T15:01:23.045Z",
              "updatedBy": "USER01"
          }
      ]
  }
```

### Debit Details v2: Cardholder search using full card record

This case retrieves the cardholder information using other commonly known information.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cardholders/search

```
{
      "cardNumber": "4000100020003000",
      "taxIdOrSsn": "123005678",
      "accountNumber": "987654321",
      "phone": "0005550000",
      "emailAddress": "jdoe@example.com",
      "dateOfBirth": "1990-08-24",
      "zipCode": "12345",
      "lastFourCardNumber": "4000",
      "lastFourAccountNumber": "6789",
      "lastName": "Doe",
      "lastFourTaxIdOrSsn": "5678"
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
      "cardholderCardsDetails": [
          {
              "cardholderDetails": {
                  "cardholderName": "Doe, Jessie H"
              },
              "cards": [
                  {
                      "cardNumber": "4000100020003000",
                      "accountNumbers": [
                          "123456789",
                          "987654321"
                      ],
                      "memberNumber": "0",
                      "cardStatus": "NORMAL",
                      "statusReasonCode": "LOST",
                      "cardActivationStatus": "NOT_ACTIVATED",
                      "cardType": "DEBIT",
                      "association": "PRIMARY",
                      "zipCode": "12345",
                      "phone": "0005550000",
                      "cellPhone": "1005550001",
                      "homePhone": "1005550001",
                      "workPhone": "1005550001",
                      "textAddress": "0005550000",
                      "dateOfBirth": "1990-08-24",
                      "expirationDate": "10/28",
                      "emailAddress": "jdoe@example.com",
                      "cardClass": "VSCK"
                  }
              ]
          }
      ]
  }
```

### Debit Details v2: Cardholder search using card number

This case retrieves the cardholder information using a card number.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cardholders/search

```
{
      "cardNumber": "4000100020003000"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
      "cardholderCardsDetails": [
          {
              "cardholderDetails": {
                  "cardholderName": "Doe, Jessie H"
              },
              "cards": [
                  {
                      "cardNumber": "4000100020003000",
                      "accountNumbers": [
                          "123456789",
                          "987654321"
                      ],
                      "memberNumber": "0",
                      "cardStatus": "NORMAL",
                      "statusReasonCode": "LOST",
                      "cardActivationStatus": "NOT_ACTIVATED",
                      "cardType": "DEBIT",
                      "association": "PRIMARY",
                      "zipCode": "12345",
                      "phone": "0005550001",
                      "cellPhone": "1005550001",
                      "homePhone": "1005550001",
                      "workPhone": "1005550001",
                      "textAddress": "0005550000",
                      "dateOfBirth": "1990-08-24",
                      "expirationDate": "10/28",
                      "emailAddress": "jdoeh@example.com",
                      "cardClass": "VSCK"
                  }
              ]
          }
      ]
  }
```

### Debit Details v2: Cardholder search using NTT

This case retrieves the cardholder information using NTT.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cardholders/search

```
{
      "nonTransToken": "piUVBJKZGfks4000"
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
      "cardholderCardsDetails": [
          {
              "cardholderDetails": {
                  "cardholderName": "Doe, John H"
              },
              "cards": [
                  {
                      "cardNumber": "4000200030004000",
                      "nonTransToken": "piUVBJKZGfks4000",
                      "accountNumbers": [
                          "123456789",
                          "987654321"
                      ],
                      "memberNumber": "0",
                      "cardStatus": "NORMAL",
                      "statusReasonCode": "LOST",
                      "cardActivationStatus": "NOT_ACTIVATED",
                      "cardType": "DEBIT",
                      "association": "PRIMARY",
                      "zipCode": "12345",
                      "phone": "1005550001",
                      "cellPhone": "1005550001",
                      "homePhone": "1005550001",
                      "workPhone": "1005550001",
                      "textAddress": "1005550001",
                      "dateOfBirth": "1990-08-24",
                      "expirationDate": "10/28",
                      "emailAddress": "jessedoe@example.com",
                      "cardClass": "VSCK"
                  }
              ]
          }
      ]
  }
```

### Debit Details v2: Cardholder search using SSN or tax ID and last name

This case retrieves the cardholder information using SSN or tax id and last name.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cardholders/search

```
{
      "taxIdOrSsn": "123005678",
      "lastName": "Doe"
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
      "cardholderCardsDetails": [
          {
              "cardholderDetails": {
                  "cardholderName": "Doe, Jessie H"
              },
              "cards": [
                  {
                      "cardNumber": "4000100020003000",
                      "accountNumbers": [
                          "123456789",
                          "987654321"
                      ],
                      "memberNumber": "0",
                      "cardStatus": "NORMAL",
                      "statusReasonCode": "LOST",
                      "cardActivationStatus": "NOT_ACTIVATED",
                      "cardType": "DEBIT",
                      "association": "PRIMARY",
                      "zipCode": "12345",
                      "phone": "0005550000",
                      "cellPhone": "1005550001",
                      "homePhone": "1005550001",
                      "workPhone": "1005550001",
                      "textAddress": "0005550000",
                      "dateOfBirth": "1990-08-24",
                      "expirationDate": "10/23",
                      "emailAddress": "jdoe@example.com",
                      "cardClass": "VSCK"
                  }
              ]
          }
      ]
  }
```

### Debit Details v2: Cardholder search using email

This case retrieves the cardholder information using and email address.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cardholders/search

```
{
      "emailAddress": "jdoe@example.com"
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
      "cardholderCardsDetails": [
          {
              "cardholderDetails": {
                  "cardholderName": "Doe, Jessie H"
              },
              "cards": [
                  {
                      "cardNumber": "4000100020003000",
                      "accountNumbers": [
                          "123456789",
                          "987654321"
                      ],
                      "memberNumber": "0",
                      "cardStatus": "NORMAL",
                      "statusReasonCode": "LOST",
                      "cardActivationStatus": "NOT_ACTIVATED",
                      "cardType": "DEBIT",
                      "association": "PRIMARY",
                      "zipCode": "12345",
                      "phone": "0005550000",
                      "cellPhone": "1005550001",
                      "homePhone": "1005550001",
                      "workPhone": "1005550001",
                      "textAddress": "0005550000",
                      "dateOfBirth": "1990-08-24",
                      "expirationDate": "10/28",
                      "emailAddress": "jdoe@example.com",
                      "cardClass": "VSCK"
                  }
              ]
          }
      ]
  }
```

### Debit Details v2: Cardholder search using account and phone numbers

This case retrieves the cardholder information using account number and phone number.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cardholders/search

```
{
      "accountNumber": "987654321",
      "phone": "0005550000"
  }
```

#### Response

**HTTP Code**: 200 OK

```
{
      "cardholderCardsDetails": [
          {
              "cardholderDetails": {
                  "cardholderName": "Doe, Jessie H"
              },
              "cards": [
                  {
                      "cardNumber": "4000100020003000",
                      "accountNumbers": [
                          "987654321"
                      ],
                      "memberNumber": "0",
                      "cardStatus": "NORMAL",
                      "statusReasonCode": "LOST",
                      "cardActivationStatus": "NOT_ACTIVATED",
                      "cardType": "DEBIT",
                      "association": "PRIMARY",
                      "zipCode": "12345",
                      "phone": "0005550000",
                      "cellPhone": "1005550001",
                      "homePhone": "1005550001",
                      "workPhone": "1005550001",
                      "textAddress": "0005550000",
                      "dateOfBirth": "1990-08-24",
                      "expirationDate": "10/23",
                      "emailAddress": "jdoe@example.com",
                      "cardClass": "VSCK"
                  }
              ]
          }
      ]
  }
```

### Debit Details v2: Cardholder search using card number, full card and token format

This case retrieves the cardholder information using card number.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cardholders/search

```
{
      "cardNumber": "4000200030004000",
      "responseFormat": "FULL_CARD_AND_TOKEN"
  }
```

#### Response

**HTTP Code:** 204 No Content

### Debit Details v2: Cardholder search using card number, token only format

This case retrieves the cardholder information using card number.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cardholders/search

```
{
      "cardNumber": "4000200030004000",
      "responseFormat": "TOKEN_ONLY"
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
      "cardholderCardsDetails": [
          {
              "cardholderDetails": {
                  "cardholderName": "Doe, John H"
              },
              "cards": [
                  {
                      "nonTransToken": "piUVBJKZGfks4000",
                      "accountNumbers": [
                          "123456789",
                          "987654321"
                      ],
                      "memberNumber": "0",
                      "cardStatus": "NORMAL",
                      "statusReasonCode": "LOST",
                      "cardActivationStatus": "NOT_ACTIVATED",
                      "cardType": "DEBIT",
                      "association": "PRIMARY",
                      "zipCode": "12345",
                      "phone": "1005550001",
                      "cellPhone": "1005550001",
                      "homePhone": "1005550001",
                      "workPhone": "1005550001",
                      "textAddress": "1005550001",
                      "dateOfBirth": "1990-08-24",
                      "expirationDate": "10/28",
                      "emailAddress": "jessedoe@example.com",
                      "cardClass": "VSCK"
                  }
              ]
          }
      ]
  }
```

### Debit Details v2: Cardholder search using NTT, masked card only format

This case retrieves the cardholder information using card number.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cardholders/search

```
{
      "nonTransToken": "piUVBJKZGfks4000",
      "responseFormat": "MASKED_CARD_ONLY"
 }
```

#### Response

**HTTP Code:** 200 OK

```
{
      "cardholderCardsDetails": [
          {
              "cardholderDetails": {
                  "cardholderName": "Doe, John H"
              },
              "cards": [
                  {
                      "cardNumber": "400020XXXXXX4000",
                      "accountNumbers": [
                          "123456789",
                          "987654321"
                      ],
                      "memberNumber": "0",
                      "cardStatus": "NORMAL",
                      "statusReasonCode": "LOST",
                      "cardActivationStatus": "NOT_ACTIVATED",
                      "cardType": "DEBIT",
                      "association": "PRIMARY",
                      "zipCode": "12345",
                      "phone": "1005550001",
                      "cellPhone": "1005550001",
                      "homePhone": "1005550001",
                      "workPhone": "1005550001",
                      "textAddress": "1005550001",
                      "dateOfBirth": "1990-08-24",
                      "expirationDate": "10/28",
                      "emailAddress": "jessedoe@example.com",
                      "cardClass": "VSCK"
                  }
              ]
          }
      ]
  }
```
