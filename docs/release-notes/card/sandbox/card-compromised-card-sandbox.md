# Test Cases

<span style="color:#ff6600;">**Card API Endpoints**</span>

When testing these endpoints, please use the test cases and test data from the Sandbox.

## Compromised Card

### Compromised Card v1: Get compromised cards list

This API returns a list of compromised cards for both debit and credit. The request has one of the following required parameters; cardnumber, networkalert or fromdate and todate.

#### Request

**HTTP Method:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/compromised/search

```
{
  "cardNumber": "400020003000400",
  "memberNumber": "0",
  "fromDateTime": "2021-07-20T07:00:00Z",
  "toDateTime": "2021-08-20T07:00:00Z"
}
```

##### Response

**HTTP Code:** 200 OK

```
{
  "compromisedCards": [
    {
      "cardNumber": "400020XXXXXX4000",
      "clientId": "12345678",
      "networkAlert": "CompCard1234",
      "networkAlertDate": "2021-12-30",
      "severityLevel": "A",
      "compromiseSource": "FALCOMPCARD TEST 1",
      "sourceAlertDescription": "NO ACTION TAKEN"
    }
  ]
  }
```

### Credit Compromised Card v1: Get details of compromised card

Returns details of compromised cards of type credit for the provided card number.

#### Request

**HTTP Method:** POST
**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/compromised/details/search

```
{
  "cardNumber": "4000200030004000",
  "networkAlert": "CompCard1234"
}
```

##### Response

**HTTP Code:** 200 OK

```
{
  "debitOnly": null,
  "creditOnly": {
    "system": "0000",
    "principal": "0000",
    "agent": "0000",
    "cardStatus": "L–Lost/Stolen",
    "accountStatus": "A–Authorization prohibited",
    "previousAction": "NO ACTION TAKEN",
    "dateLastMaintainance": "2021-07-20",
    "expiryDate": "2025-07-20",
    "cardStatusReasonCode": "88–Fraud",
    "compromisedDate": "2021-07-20",
    "account": "1451550129",
    "transferredAccount": "Yes",
    "transferredCard": "Yes"
  }
}
```

### Debit Compromised Card v1: Get details of compromised card

Returns details of compromised cards of type debit for the provided card number.

#### Request

**HTTP Method:** POST
**Target URL:** https://card-sandbox.api.fiservapps.com/cs/cards/v1/compromised/details/search

```
{
  "cardNumber": "4000200030004001",
  "networkAlert": "CompCard123456"
}
```

##### Response

**HTTP Code:** 200 OK

```
{
  "debitOnly": {
    "eftRiskAlertNumber": "62800",
    "dateLastMaintainance": "2021-07-20"
  },
  "creditOnly": null
}
```
