# Test Cases

<span style="color:#ff6600;">**Card API Endpoints**</span>

When testing these endpoints, please use the test cases and test data from the Sandbox.

## Update Status

### Credit Card Status v2: Update card status

Update the status of a card, including deactivation.

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/status

#### Request

```
{
  "cardNumber": "4000200030004001",
  "cardStatus": "CAPTURE",
  "statusReasonCode": "LOST",
  "fraudActivity": "POSSIBLE_FRAUD",
  "securityMemo": "memo"
  }
```

#### Response

**HTTP Code:** 204 No Content

### Credit card Status v1: Search card status, full card only format

Retrieve status of Credit Card,

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/status/search

#### Request

```
{
      "cardNumber": "4000200030004001",
      "responseFormat": "FULL_CARD_ONLY"
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
      "cardNumber": "400020xxxxxx4001",
      "cardStatus": "LOST_OR_STOLEN",
      "statusReasonCode": "LOST"
  }
```

### Debit Card Status v2: Update card status

Update the status of a card, including deactivation.

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/status

#### Request

```
{
      "cardNumber": "4000200030004000",
      "memberNumber": "0",
      "cardStatus": "ACTIVE",
      "statusReasonCode": "NONE",
      "fraudActivity": "NONE_SUSPECTED",
      "securityMemo": "memo"
  }
```

#### Response

**HTTP Code:** 204 No Content

### Debit Card Status v2: Update using card number, full card only format

Update the status of a card, including deactivation.

**HTTP Method:** PUT

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/status

#### Request

```
{
      "cardNumber": "4000200030004000",
      "responseFormat": "FULL_CARD_ONLY",
      "memberNumber": "0",
      "cardStatus": "CAPTURE",
      "statusReasonCode": "LOST"
  }
```

#### Response

**HTTP Code:** 204 No Content

### Debit Card Status v1: Search using card number, token only format

Retrieve the status of debit card.

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/status/search

#### Request

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
      "cardStatus": "CAPTURE",
      "statusReasonCode": "LOST"
  }
```

### Debit Card Status v1: Search using card number, full card only format

Retrieve the status of debit card.

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/status/search

#### Request

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
      "cardStatus": "CAPTURE",
      "statusReasonCode": "LOST"
  }
```

### Debit Card Status v1: Search using NTT, masked card only format

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/status/search

#### Request

```
{
      "nonTransToken": "piUVBJKZGfks4000",
      "responseFormat": "MASKED_CARD_ONLY",
      "memberNumber": "0"
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
      "cardNumber": "400020xxxxxx4000",
      "cardStatus": "CAPTURE",
      "statusReasonCode": "LOST"
  }
```
