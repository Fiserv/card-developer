## Activations

### Credit Activate v1: Activate inactive card

This case activates a card.

#### Request

**HTTP Method:** PUT

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations

```
{
      "cardNumber": "4000100020003001"
  }
```

##### Response

**HTTP Code:** 200 OK

```
{
      "cardType": "CREDIT",
      "cardActivationStatus": "ACTIVATED"
  }
```

### Credit Activate v1: Search for inactive card

This case demonstrates when the card is inactive.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations/search

```
{
      "cardNumber": "4000100020003001"
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
      "cardType": "CREDIT",
      "cardActivationStatus": "ACTIVATION_REQUIRED"
  }
```

### Credit Activate v1: Search for active card

This case demonstrates when the card is active.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations/search

```
{
      "cardNumber": "4000200030004001"
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
      "cardType": "CREDIT",
      "cardActivationStatus": "NO_ACTIVATION_REQUIRED"
  }
```

### Debit Activate v1: Activate inactive card using card number

This case activates a debit card.

#### Request

**HTTP Method:** PUT

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations

```
{
      "cardNumber": "4000100020003000"
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
      "cardNumber": "400010XXXXXX3000",
      "cardType": "DEBIT",
      "activationRequiredByDate": "2021-10-31",
      "availableForUseDate": "2021-07-26",
      "cardActivationDate": "2021-09-23",
      "cardActivationStatus": "ACTIVATED",
      "lastActivationAttemptDate": "2021-09-23",
      "activationMethod": "OPERATOR_ACTIVATE",
      "numberOfAttempts": "0",
      "verificationCallerID": "9900020"
  }
```

### Debit Activate v1: Activate inactive card using NTT

This case activates a card using NTT.

#### Request

**HTTP Method:** PUT

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations

```
{
      "nonTransToken": "hggLkjgJGSwh3000"
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
      "nonTransToken": "hggLkjgJGSwh3000",
      "cardType": "DEBIT",
      "activationRequiredByDate": "2021-10-31",
      "availableForUseDate": "2021-07-26",
      "cardActivationDate": "2021-09-23",
      "cardActivationStatus": "ACTIVATED",
      "lastActivationAttemptDate": "2021-09-23",
      "activationMethod": "OPERATOR_ACTIVATE",
      "numberOfAttempts": "0",
      "verificationCallerID": "9900020"
  }
```

### Debit Activate v1: Search for inactive card using card number

This case demonstrates when the debit card is inactive.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations/search

```
{
      "cardNumber": "4000100020003000"
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
      "cardNumber": "400010XXXXXX3000",
      "cardType": "DEBIT",
      "activationRequiredByDate": "2021-10-31",
      "availableForUseDate": "2021-07-26",
      "cardActivationStatus": "NOT_ACTIVATED",
      "numberOfAttempts": "0"
  }
```

### Debit Activate v1: Search for inactive card using NTT

This case demonstrates when the debit card is inactive.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations/search

```
{
      "nonTransToken": "hggLkjgJGSwh3000"
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
      "nonTransToken": "hggLkjgJGSwh3000",
      "cardType": "DEBIT",
      "activationRequiredByDate": "2021-10-31",
      "availableForUseDate": "2021-07-26",
      "cardActivationStatus": "NOT_ACTIVATED",
      "numberOfAttempts": "0"
  }
```

### Debit Activate v1: Search for active card using card number

This case demonstrates when the debit card is activated.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations/search

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
      "cardType": "DEBIT",
      "activationRequiredByDate": "2022-12-31",
      "cardActivationDate": "2021-09-21",
      "cardActivationStatus": "ACTIVATED",
      "lastActivationAttemptDate": "2021-09-21",
      "activationMethod": "OPERATOR_ACTIVATE",
      "numberOfAttempts": "1"
  }
```

### Debit Activate v1: Search for active card using NTT

This case demonstrates when the debit card is activated.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/cards/activations/search

```
{
      "nonTransToken": "piUVBJKZGfks4000"
  }
```

#### Response

**HTTP Code:** 200 OK

```
{
      "nonTransToken": "piUVBJKZGfks4000",
      "cardType": "DEBIT",
      "activationRequiredByDate": "2022-12-31",
      "cardActivationDate": "2021-09-21",
      "cardActivationStatus": "ACTIVATED",
      "lastActivationAttemptDate": "2021-09-21",
      "activationMethod": "OPERATOR_ACTIVATE",
      "numberOfAttempts": "1"
  }
```
