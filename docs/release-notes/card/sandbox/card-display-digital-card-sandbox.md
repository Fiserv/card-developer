# Test Cases

<span style="color:#ff6600;">**Card API Endpoints**</span>

When testing these endpoints, please use the test cases and test data from the Sandbox.

## Display Digital Card

### Debit Digital Card Display v2: Search auth details using card number

Retrieve card expiration date and CV2.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/authDetails

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
    "cv2": "282",
    "expirationDate": "10/28"
  }
```

### Debit Digital Card Display v2: Search auth details using NTT

Retrieve card expiration date and CV2.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v2/cards/authDetails

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
    "cv2": "282",
    "expirationDate": "10/28"
  }
```
