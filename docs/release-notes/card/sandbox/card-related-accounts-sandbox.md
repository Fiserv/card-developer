# Test Cases

<span style="color:#ff6600;">**Card API Endpoints**</span>

When testing these endpoints, please use the test cases and test data from the Sandbox.

## Related Accounts

### Debit Related Account v2: Add account using NTT

Add accounts to the selected cardholder record.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/accounts/associations

```
{
    "nonTransToken": "piUVBJKZGfks4000"
    "associations": [
        {
            "accountNumber": "123456789",
            "accountType": "CHECKING",
            "accountDescription": "Main",
            "accountStatus": "ACTIVE",
            "primaryAccount": "YES",
            "restrictedTransactions": "NO_RESTRICTIONS",
            "transactionsAllowed": {
                "balanceInquiries": true,
                "deposits": true,
                "paymentFrom": true,
                "paymentTo": true,
                "posPurchasesReturns": true,
                "transferFrom": true,
                "transferTo": true,
                "withdrawalsCashAdvance": true
            }
        }
    ]
}
```

#### Response

**HTTP Code:** 201 Created

### Debit Related Account v2: Add account using card number

Add accounts to the selected cardholder record.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/accounts/associations

```{
  "cardNumber": "4000200030004000",
  "memberNumber": "0",
  "associations": [
    {
      "accountNumber": "123456789",
      "accountType": "CHECKING",
      "accountDescription": "Main",
      "accountStatus": "ACTIVE",
      "primaryAccount": "YES",
      "restrictedTransactions": "NO_RESTRICTIONS",
      "transactionsAllowed": {
        "balanceInquiries": true,
        "deposits": true,
        "paymentFrom": true,
        "paymentTo": true,
        "posPurchasesReturns": true,
        "transferFrom": true,
        "transferTo": true,
        "withdrawalsCashAdvance": true
      }
    }
  ]
}
```

#### Response

**HTTP Code:** 201 Created

### Debit Related Account v2: Remove account using NTT

Delete accounts associated with the selected cardholder record.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/accounts/associations/unassociate

```
{
      "nonTransToken": "piUVBJKZGfks4000",
      "accountNumber": "123456789",
      "accountType": "SAVINGS"
  }
```

#### Response

**HTTP Code:** 204 No Content

### Debit Related Account v2: Remove account using card number

Delete accounts associated with the selected cardholder record,

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/accounts/associations/unassociate

```
{
      "cardNumber": "4000200030004000",
      "memberNumber": "0",
      "accountNumber": "123456789",
      "accountType": "SAVINGS"
  }
```

#### Response

**HTTP Code:** 204 No Content

### Debit Related Account v2: Search account using NTT

Retrieves the details of all accounts associated with the selected cardholder record.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/accounts/search

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
    "associations": [
        {
            "accountNumber": "123456789",
            "accountType": "CHECKING",
            "accountDescription": "Main",
            "accountStatus": "ACTIVE",
            "primaryAccount": "YES",
            "restrictedTransactions": "NO_RESTRICTIONS",
            "transactionsAllowed": {
                "balanceInquiries": true,
                "deposits"
: true,
                "paymentFrom": true,
                "paymentTo": true,
                "posPurchasesReturns": true,
                "transferFrom": true,
                "transferTo": true,
                "withdrawalsCashAdvance": true
            }
        }
    ]
}
```

### Debit Related Account v2: Search account using card number

Retrieves the details of all accounts associated with the selected cardholder record.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/accounts/search

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
    "associations": [
        {
            "accountNumber": "123456789",
            "accountType": "CHECKING",
            "accountDescription": "Main",
            "accountStatus": "ACTIVE",
            "primaryAccount": "YES",
            "restrictedTransactions": "NO_RESTRICTIONS",
            "transactionsAllowed": {
                "balanceInquiries": true,
                "deposits": true,
                "paymentFrom": true,
                "paymentTo": true,
                "posPurchasesReturns": true,
                "transferFrom": true,
                "transferTo": true,
                "withdrawalsCashAdvance": true
            }
        }
    ]
}
```

### Debit Related Account v2: Update account using NTT

Update the details of accounts associated with the selected cardholder record.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/accounts/associations

```

  "nonTransToken": "piUVBJKZGfks4000"
  "associations": [
    {
      "accountNumber": "123456789",
      "accountType": "CHECKING",
      "accountDescription": "Main",
      "accountStatus": "ACTIVE",
      "primaryAccount": "YES",
      "restrictedTransactions": "NO_RESTRICTIONS",
      "transactionsAllowed": {
        "balanceInquiries": true,
        "deposits": true,
        "paymentFrom": true,
        "paymentTo": true,
        "posPurchasesReturns": true,
        "transferFrom": true,
        "transferTo": true,
        "withdrawalsCashAdvance": true
      }
    }
  ]
}
```

#### Response

**HTTP Code:** 204 No Content

### Debit Related Account v2: Update account using card number

Update the details of accounts associated with the selected cardholder record.

#### Request

**HTTP Method:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/accounts/associations

```
{
  "cardNumber": "4000200030004000",
  "memberNumber": "0",
  "associations": [
    {
      "accountNumber": "123456789",
      "accountType": "CHECKING",
      "accountDescription": "Main",
      "accountStatus": "ACTIVE",
      "primaryAccount": true,
      "restrictedTransactions": "NO_RESTRICTIONS",
      "transactionsAllowed": {
        "balanceInquiries": true,
        "deposits": true,
        "paymentFrom": true,
        "paymentTo": true,
        "posPurchasesReturns": true,
        "transferFrom": true,
        "transferTo": true,
        "withdrawalsCashAdvance": true
      }
    }
  ]
}
```

#### Response

**HTTP Code:** 204 No Content
